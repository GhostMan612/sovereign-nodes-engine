# WO-F — Synthetic handoff truth table, schema and threat controls

**State: TEST-SPECIFIED / NOT RUN.** Source `fps_launcher.gd` emits `"hasParadox": bool(...)`; ZScript `sn_handoff.zs` reads `ScanInt(text, KEY_PARADOX, paradoxFlag)` then compares to zero. Handout is not a claimed runtime failure. Shared `%TEMP%/SovereignNodes/fps_handoff.json` is an interprocess convenience, not an authenticated trust boundary.

## Truth table (observe actual results; do not fill in outcomes)

| Case | Synthetic input variation | Expected contract test | Risk to record |
|---|---|---|---|
| H-01 | schema=1, runId=`SAMPLE-RUN-A`, seed=42, `SAMPLE ANCESTOR A` | HUD/scoreboard matches producer | no direct real names |
| H-02 | JSON `hasParadox: true` | consumer reports true | possible integer scanner mismatch |
| H-03 | JSON `hasParadox: false` | consumer reports false | false-negative indistinguishable from default |
| H-04 | integer `hasParadox: 1` **fixture only** | discriminate scanner ability | cannot claim unchanged producer parity |
| H-05 | missing schema | capture warning, reject/tolerate exactly as code does | observed tolerant codepath requires review |
| H-06 | schema=999 | capture warning/behavior, no crash | future schema trust |
| H-07 | missing file / empty TEMP | standalone game safe/no leaked content | environment handling |
| H-08 | stale previous runId and old issuedAt | record stale acceptance and harm | replay/freshness |
| H-09 | oversized, malformed, duplicate JSON key, escaped quotes | bounded safe read, no code execution | hand-written parser ambiguity |
| H-10 | altered path / simulated untrusted writer | detect path confusion, never access Mantle | temporary-file tampering |

## Two baseline lanes

- **Unmodified game**: Godot authentic producer writes a new synthetic handoff file and Doom consumer reads it. This is the actual parity test for C-006/C-015.
- **Disposable mutation**: JSON `true/false` versus numeric `1/0` isolates parser behavior but cannot be relabeled an unchanged game pass. Original and fixture hashes must be different and documented.

## Evidence and stop criteria

Record Godot source SHA, engine binary and game PK3 SHA, exact synthetic input SHA-256, timestamps/runId, expected/observed HUD/paradox/seed/integrity, logs after path redaction, schema version, independent reviewer. Never publish a real name, genealogy/person graph, vault file, private nodeId or raw local temp path. Invalid input must not execute Python/native code. Fail/hold when state doesn't match; don't silently change producer/consumer source during baseline tests.

## Post-test disposition (not approved repair)

If v1 behavior differs from contract, propose a separate handoff v2 or fixture repair work order with strict boolean parsing, bounded size, schema policy, freshness/nonce and atomic write. Do not deploy protocol changes until a versioned compatibility decision is signed.

Sources: [Godot producer](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd), [Doom consumer](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs).
