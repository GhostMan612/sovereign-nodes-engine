# F-03 — Failures must identify the stage, not prejudge engine suitability

| Class | Observable evidence | Next action after a *future approved* attempt |
|---|---|---|
| `NOT AUTHORIZED` | no valid AUTH-H/AUTH-B/signature, expired or wrong candidate | `BLOCKED`, do not execute |
| `HOST BLOCKED` | missing verified MSVC/SDK/disk/permissions | inventory missing; request new scope rather than install |
| `DEPENDENCY BLOCKED` | legal/provenance, unavailable or unapproved network package | hold G2/G4; revise dependencies with approval |
| `CONFIGURE FAIL` | CMake exit nonzero, wrong generator, missing Python/fastgltf | retain CMake log/hash; diagnose compiler/deps/config |
| `COMPILE FAIL` | compiler syntax/type error, C++ standard incompatibility | retain minimal error context and exact source revision |
| `LINK FAIL` | unresolved symbols, CRT ABI/arch mismatch, missing libraries | inspect link log, input libs and runtime policy |
| `RESOURCE FAIL` | executable builds but engine resource PK3/DLL unavailable | build result partial; no runtime admission |
| `REPRO MISMATCH` | same intended inputs yield differing artifact hashes | investigate timestamps/debug paths/build environment; not automatic feature FAIL |
| `SOURCE DIRTY` | source checkout modified/untracked conflict | stop; do not reset or discard work |
| `GAME FAIL` | custom GapNode/actors/parity discrepancy | only under separate AUTH-T; never diagnosed from compile output |
| `PERFORMANCE FAIL` | real UHD 620 trace violates predeclared criteria | only under separate AUTH-P after G3 acceptance |

Record `attempted=true` only when an approved action actually occurred. A speculative failure scenario is `TEST-SPECIFIED/NOT RUN`, not a logged FAIL. Reviewer differentiates environment defects from candidate source and game content defects.
