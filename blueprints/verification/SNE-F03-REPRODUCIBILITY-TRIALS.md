# F-03 — Two-attempt native build reproducibility protocol

**Future authorized procedure ONLY. No trial attempted.** G4 requires actual compiler evidence and independent review.

1. Freeze a single candidate source SHA, submodule and dependency SHAs, toolchain, CMake flags, backend features, generator and build environment. Lock source as read-only.
2. Authorize two distinct clean build trees; do not reuse the prior CMakeCache or incrementally rebuild a dirty tree to claim reproducibility.
3. Capture a complete configure/build attempt A with redacted log SHA-256, exit statuses, environment/toolchain records, binary/resource manifest and timestamps.
4. Repeat attempt B under the **same effective input identity**, not a changed compiler, package release, branch or source tree; capture separately.
5. Compare resulting executable/DLL/resource hash and size; if identical, report matching binaries **for the tested profile only**. If different, investigate PDB/embed paths, timestamps, archive ordering, link metadata and generated assets, then record justified non-determinism with a reproducible build trace.
6. Independent reviewer examines both logs, identities, unresolved discrepancies and any material source differences. Operator may accept only the specific measured G4 scope, not gameplay/performance/distribution.

## Limits

Two attempts in one machine do not prove cross-machine portability. An executable starting is another separately approved `AUTH-T` case. Runtime frame times require `AUTH-P`, and code/asset licenses G2 remain open. Use `templates/SNE-F03-REPRO-RECORD.json` with both attempt references initially null.
