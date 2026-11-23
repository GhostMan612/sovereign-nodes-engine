# SNE-F03 — AUTH-H host inventory, redacted public summary

- Capture state: **PARTIAL — core host data captured; compiler lane NOT captured.**
- Work order: `SNE-WO-F03`; device alias: `SNE-REF-LAPTOP` (private device id held by operator only).
- Captured at UTC: 2026-11-22T21:11:53Z – 21:12:01Z. Executor: Hermes Agent.
- Authorization basis: `AUTH-H-SNE-F03-001`, granted via the operator's explicit
  instruction on 2026-11-21 (chat channel). This deviates from the contract's
  "individually dated signed private record"; the deviation and full provenance
  are recorded in the private run manifest, not hidden here.
- Scope digest (`scope_sha256`, method of `templates/SNE-F03-AUTHORIZATION.schema.json`):
  `1fc8fec09a9a7f622c3952487d742212e0e7847ad1436457188710f1293ed8c6`
- Scoped planning revision: `ef32a03…`; execution HEAD `e378716…` (delta = this
  AUTH-H request package itself; no silent re-pin).
- Execution discipline: read-only queries only; no network; no installs; no writes
  outside the private capture root. Private raw captures and their SHA-256 ledger
  stay off-repo.

## Observed values (per approved allowlist)

| Category | Observed |
|---|---|
| OS | Microsoft Windows 11 Pro, build 26300, x64 |
| CPU | Intel Core i5-8365U @ 1.60 GHz, 4 cores / 8 logical processors |
| GPU | Intel UHD Graphics 620; driver 31.0.101.2137 (2025-08-27); AdapterRAM 1 GiB driver-reported (UMA reporting may be inaccurate) |
| Memory | 16,981,467,136 bytes (~15.8 GiB) |
| CMake | 4.4.4 present (user-scope WinGet shim) |
| Git | 2.53.0.windows.3 present |
| Python | 3.14.9 present (agent-managed virtual environment) |
| Ninja | NOT DETECTED ON PATH |
| Visual Studio / MSVC / Windows SDK | NOT CAPTURED — `vswhere` query requires explicit method approval that was not granted; absence of `cl` on PATH proves nothing and no inference is drawn |
| Planning repo at capture | `main` @ `e378716f8ae4c2cc7a736de52e143f7f49b7258a`, clean |

The CPU/GPU/memory class matches the reported Latitude 5400 / UHD 620 reference
profile. This is inventory only — not a benchmark, not a compatibility result,
and not a PASS for P00-G4 or any other gate.

## Limitations carried forward

- Compiler lane open: VS instance, MSVC version/target, Windows SDK unknown until an
  approved read method runs.
- GPU API capability (OpenGL/Vulkan) not probed; AdapterRAM is driver-reported.
- CMake 4.x is newer than the candidates' historical minimums; implications are a
  build-lane question, not an inventory finding.
- `ninja` absence blocks Ninja-generator plans only if that generator is chosen.

## Next step

Compiler lane needs an operator-approved read method (e.g., sanctioned
`vswhere`/VS-installer query). Until then every build gate stays BLOCKED, not FAIL.
This summary accepts nothing and supersedes nothing;
`templates/SNE-F03-AUTHORIZATION-H.json` remains the historical PROPOSED record.
