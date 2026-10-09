# Pinned upstream engine source map — 000A seed for 000B

**Date:** 2026-10-09
**Status:** MULTIPLE SELECTED FILES READ, NO FULL SOURCE AUDIT, NO BUILD.
**Exact revisions:** `evidence/sources/SNE-REVISION-LEDGER.md`.

| Candidate | Verified subsystem location | Architecture note | Deeper inspection needed |
|---|---|---|---|
| GZDoom | `src/common/models/voxels.cpp`, `models_voxel.cpp`, `src/r_data/voxeldef.cpp` | Existing voxel sprite/model pipeline | Format support, mesh budget, profile/render costs |
| GZDoom | `src/r_data/gldefs.cpp` | Lighting definition parser | Binding semantics, shadows, material pipeline |
| GZDoom | `src/scripting/zscript/zcc_compile_doom.cpp` | ZScript compiler | Game v4.14 grammar and API parity |
| GZDoom | `src/g_hub.cpp` | Hub state/transition source area | Not evidence of seamless dual-zone rendering |
| UZDoom | `src/scripting/zscript/zcc_compile_doom.cpp` | ZScript compile subsystem retained | Version/API differences from GZDoom |
| UZDoom | `src/d_main.cpp` | Resource/definition setup | MAPINFO/GLDEFS exact loader behavior |
| UZDoom | `src/common/models/voxels.cpp` | Voxel source | Diff from GZDoom |
| BiasedDoom | `src/common/models/model_gltf.cpp/.h` | `fastgltf`, conditional `NEODOOM_GLTF_SUPPORT` | Mesh/material/animation proof on supported GPU |
| BiasedDoom | `CMakeLists.txt` | Conditional Python/glTF build config | build and security defaults |
| Chocolate Doom | `src/doom/p_setup.c`, `p_maputl.c` | WAD/BSP/collision baseline | Reference, not modernization starting point |
| Original Doom | `linuxdoom-1.10/p_setup.c` | Classic BSP/BLOCKMAP/REJECT | Reference only |

## Verified language/build configuration

- GZDoom: CMake minimum 3.16, C++17 (`CMakeLists.txt`).
- UZDoom: CMake minimum 3.16, C++20 and `find_package(Python3 3.6 REQUIRED)` for project configuration; this does **not** mean Python mod scripting.
- BiasedDoom: CMake minimum 3.16 and optional embedded Python/glTF feature toggles; glTF source compiled conditionally.
- Chocolate Doom: CMake minimum 3.7.2, C99, SDL2 dependency checks.
- Original Doom: historical Linux source, unsuitable as a modern source-port build baseline without extensive platform work.

## Maintainer and licensing caveat

UZDoom's `CONTRIBUTING.md` expressly disallows AI-assisted upstream PRs (even AI-assisted comments). This is distinct from GPL permissions for SNE's independent derivative. Root license and per-directory asset exceptions remain in scope for `SNE-WO-000B`.

## Next mapping tasks (work order 000B)

Pin actual renderer/backend selection logic and interfaces; map-level transition and save serialization paths; diff fork architecture and dependency graph; inspect relevant CMake subdirectories and third-party notices. Only then propose source modifications.

See `evidence/sources/SNE-SRC-{GZDOOM,UZDOOM,BIASEDDOOM,CLASSIC}-001.md` for links and exact SHA references.
