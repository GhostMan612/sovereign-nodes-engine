# SNE-WO-000C — Cross-process handoff parity and threat review

## Source observation

- Godot `FpsLauncher.write_handoff()` in `games/SovereignNodes/src/world/fps_launcher.gd` writes `schema: 1`, `version: 1`, `runId`, `seed`, `map`, `nodeId`, `ancestorId`, `ancestorName`, `relationship`, `hasParadox` (a **boolean**), `paradoxType`, `requiredRecords`, `integrityPct`, `issuedAt`.
- Godot writes both `user://fps_handoff.json` and `%TEMP%/SovereignNodes/fps_handoff.json` on Windows; standalone FPS relies on the latter; environment lookup TEMP/TMP/TMPDIR.
- Doom `zscript/sn_handoff.zs` has `HANDOFF_SCHEMA_VERSION = 1` and hand-written `ScanRaw`/`ScanInt`/`ScanString`; extracts named scalars. It currently uses `ScanInt(text, KEY_PARADOX, paradoxFlag)` for `hasParadox`, which was emitted by Godot as `true`/`false`.
- Doom handoff reader warns on missing/newer schema but **continues reading**; it does not strictly reject such input. Godot's own readback path warns and returns unverified data when stamp missing.
- There is no cryptographic signature or freshness guarantee in the observed v1 schema. An untrusted process that can write the shared temp path could tamper with content.

## Synthetic-only test matrix

| ID | Input | Expected observation to record (not predetermined PASS) |
|---|---|---|
| H-01 | valid v1, synthetic name `SAMPLE ANCESTOR A`, seed 42, unique runId | consumer HUD and state match producer |
| H-02 | valid v1 `hasParadox: true` | whether reader's integer scanner yields a true flag |
| H-03 | valid v1 `hasParadox: false` | whether reader's integer scanner yields a false flag |
| H-04 | schema field missing | warning and tolerant read as source suggests; capture actual behavior |
| H-05 | schema=999 | warning and tolerant read as source suggests; capture actual behavior |
| H-06 | invalid JSON/unclosed quotes | parsing returns safe/no-crash, record partial-read behavior |
| H-07 | stale runId with prior valid content | identify stale content; source currently has no robust reject guarantee |
| H-08 | absent temp file or unavailable temp env | standalone gameplay unaffected; no user data logged |
| H-09 | oversized scalar and file | bounded reading/resource limits required as proposed hardening |
| H-10 | duplicate keys/escaped quote | manually scanned string ambiguity surfaced; no unsafe trust upgrade |

## Future hardened v2 contract (design proposal only)

- Explicit schema/version compatibility table with **fail-closed** behavior for unsupported required fields; optional fields may be forward compatible only when policy says so.
- `hasParadox` parsed strictly as JSON boolean (not integer coercion); optional `paradoxType` only meaningful if true.
- Producer emits random one-use handoff nonce, issue/expiry bound, expected runId, atomic write and file permissions where possible; consumer validates and prevents stale replay.
- Prefer a dedicated narrow IPC/contract adapter if the engine's script API cannot enforce bounded JSON parse/validation. Never expose live Mantle filesystem, Neo4j graph, vault, private person names or dynamic code execution.
- Preserve backward compatibility policy explicitly. Do not silently reject all old v1 files without a migration decision and tests.

## Security classification

A common temp file is **not a trust boundary**. This research does not prove exploitability but shows that format validation and integrity are currently limited. Python execution through BiasedDoom is out of scope and must remain opt-in/trusted-only.

Source Godot: https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd
Source Doom: https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs
