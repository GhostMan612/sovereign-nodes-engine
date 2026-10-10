# F-01 — Native build (`AUTH-B`) vs gameplay (`AUTH-T`) admission contracts

**Both categories remain UNAPPROVED.** Do not execute the example commands in WO-D by virtue of reading this document.

## Build-only `AUTH-B`

- Candidate exact immutable commit: GZDoom `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`, UZDoom `dbedcc894fb6866c48520cf27ae773f9957024b9`, BiasedDoom `6147e0670458e48e63d1a40750f36dfc68b00f7f` (historical research pins; fresh approval may choose a new pinned SHA).
- Freeze native Windows compiler+SDK+CMake generator/build flags, vcpkg/dependency snapshot and exact allowed source/build/cache/output directories outside the SNE planning and original game repos.
- Separately decide network allowed vs deny, permissible dependency archives and hash provenance; no silent unreviewed install, source patch, symlink traversal, `git pull`, automatic updater, LTO flag adjustment or global environment mutation.
- Record configure/build exit codes, redacted errors, binary/resource SHA-256 and compiler environment into future WO-D build template. A failed configure is `FAIL` for that attempt, not automatic disqualification of an entire engine; unauthorized attempt stays `BLOCKED`.

## Game-only `AUTH-T`

- Requires known legal IWAD provenance external to repo, exact engine binary/resources/unchanged B0 PK3 hashes, pinned MAP01 marker and test case list C-001…C-008 with negative controls.
- `AUTH-T` specifically names data/log paths, game session limit, rendered backend, executable args and stop on ZScript error, missing GapNode, fallback Entryway, untrusted Python mods or altered original source.
- A baseline control does not automatically authorize UZDoom/BiasedDoom on the same machine; candidate identity must be explicit in scope. Capture candidate-specific evidence and don't merge incompatible runtime cases.

## Scope crossover prohibited

A compiled binary cannot be run or stress-tested under build permission alone. A known prebuilt executable cannot be modified/recompiled under gameplay-only permission. Passing an optional voxel/glTF demo does not repair C-001…C-008. UZDoom upstream AI PR policy remains distinct from licensed downstream private work; `AUTH-D` always separate.
