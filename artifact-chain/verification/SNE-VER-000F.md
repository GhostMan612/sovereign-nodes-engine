# SNE-VER-000F — Documentation/ZIP validation, separate from runtime

## Required package gates

- `V-F01` ZIP CRC test across every member; no duplicate names, path traversal, casefold collisions or absolute paths.
- `V-F02` every member under exact `sovereign-nodes-engine/` root, only Markdown/JSON; no engine source, scripts, executables, `.git`, WAD/IWAD, private data or secrets.
- `V-F03` exact ADD and REPLACE list matches manifest; all REPLACE Git blob SHA-1 values refer to the pinned SNE baseline.
- `V-F04` all content UTF-8 with LF newlines and terminal newline, no trailing whitespace or forbidden control bytes.
- `V-F05` all JSON parse; SHA-256 ledger covers all members except the ledger itself without circular hash.
- `V-F06` internal links and IDs are locally plausible; no claim of completed independent review or device tests.

## Explicitly NOT verified by ZIP integrity

Native Windows x64 CMake configure/build, candidate binaries, proprietary IWAD ownership, existing game packaging/execution, C-001…C-015 PASS, real source-game defect repair, UHD 620 frame time, security controls, license clearance, G7 reviewer signature, operator foundation adoption or Phase 01 authorization.

## Operator verification after extraction

Check exact HEAD and clean working tree **before** unzipping, then examine 6 expected REPLACE and 43 expected ADD paths as written in the manifest; `git diff --check` ignores untracked files. Stage only explicit paths, then use `git diff --cached --check`, `git diff --cached --stat` and `git diff --cached --name-only`. Any local conflict requires manual review, never forced replacement or blanket staging.
