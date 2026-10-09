# SNE-EVD-000B — Candidate engine source inspection

**Date:** 2026-10-09
**Evidence status:** SOURCE INSPECTION PERFORMED; RUNTIME NOT RUN
**Source pins:** `evidence/sources/SNE-SOURCE-PINS-000B.md`

## Collected

- GZDoom source paths for voxel resource loading, VOXELDEF parser, model conversion, GLDEFS light associations, ZScript actor definitions, hub state and root CMake.
- UZDoom source paths for same core systems, C++20 build declaration, GPL/license exceptions, contributor policy.
- BiasedDoom source paths for fastgltf parser, mesh/PBR structures, CMake flags, vcpkg feature dependencies and glTF documentation.
- Existing game's pinned MAPINFO, GLDEFS, ZScript, Godot producer/Doom consumer, build and WAD validator.

## Evidence classification

- `SOURCE-PATH VERIFIED`: file fetched at pinned revision and relevant symbols/types observed.
- `DOCUMENTATION CLAIM`: official README/docs; requires source and runtime corroboration.
- `RUNTIME NOT RUN`: no claim of GPU, rendering correctness, compile success or compatibility.
- `NOT LEGALLY CLEARED`: root license notices observed; full redistribution inventory pending.

## Findings with caution

1. Candidate engine code already provides most inherited systems needed for a compatibility-first SNE. This supports an incremental extension hypothesis, not a performance claim.
2. BiasedDoom's `.glb` embedded-image documentation warns about partial support even while the code includes a memory-image decoding path; treat as an unresolved test case, not a contradiction arbitrated by assumption.
3. UZDoom's upstream AI PR restrictions must be respected separately from GPL redistribution rights.
4. The game's own JSON handoff includes boolean `hasParadox` whereas the receiver reads through `ScanInt`; this is a potential test-critical mismatch, not yet reproduced.
5. The game's WAD generator validates an `dirofs=12` layout; do not convert that generator-specific check into a universal WAD format claim.

## Chain

Work order → source records → source code map and matrices → reviewer findings → `SNE-VER-000B` → `SNE-ACC-000B` → `SNE-REC-000B`.
