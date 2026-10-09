# Upstream code map — v0.4.0 selected-source audit

**Status:** PATH/SYMBOL-VERIFIED IN SELECTED FILES; complete source tree not cloned, call graph not exhaustive; compile/runtime still NOT RUN.

Detailed immutable URLs live in `evidence/sources/SNE-SOURCE-PINS-000B.md`. The technical assessment lives in `SNE-000B-ENGINE-CODE-MAP.md`.

## GZDoom

- CMake >=3.16, C++17 confirmed in root `CMakeLists.txt`.
- Voxel load: `src/common/models/voxels.cpp`; sprite associations and `VOXELDEF`: `src/r_data/voxeldef.cpp`; model implementation: `src/common/models/models_voxel.cpp`.
- Actor lights: `src/r_data/gldefs.cpp`, `AddLightDefaults`/`AddLightAssociation` calls/declarations.
- Actor scripting: `src/scripting/thingdef.cpp`; scripting compiler family in `src/scripting/zscript/`.
- Hub/intermission state: `src/g_hub.cpp` (`G_LeavingHub`, `CLUSTER_HUB`) is **not** a simultaneous world streaming engine.

## UZDoom

- CMake >=3.16 and C++20, optional release LTO, `find_package(Python3 3.6 REQUIRED)` as BUILD dependency.
- Actor and ZScript compiler paths: `src/scripting/thingdef.cpp`, `src/scripting/zscript/zcc_compile_doom.cpp`.
- Voxel and lights: `src/common/models/voxels.cpp`, `src/r_data/gldefs.cpp`.
- Hub/intermission: `src/g_hub.cpp`.
- `CONTRIBUTING.md` bans AI-assisted/generated upstream PR code and AI-generated art; does not itself cancel the GPL fork license.

## BiasedDoom

- CMake >=3.16, C++17; opt-in/conditional CPython and fastgltf options.
- `src/common/models/model_gltf.h/.cpp` has type definitions and `fastgltf` parser source behind `NEODOOM_GLTF_SUPPORT`; exact enablement/registration must be traced to build.
- `vcpkg.json` declares optional features including `gltf-support` and `vcpkg-python`.
- Documentation recommends external-texture `.gltf` workflow due to partial `.glb` embedded image limitations; test rather than assume.
- ZScript deprecation is a stated future intent, NOT a verified current removal.

## Classic references

- Chocolate Doom: `src/doom/p_setup.c` and C99/SDL2 CMake configuration; appropriate for concept study, not a drop-in ZScript host.
- Original Doom: `linuxdoom-1.10/p_setup.c`; note historical source header uses original license language even though root README later mentions GPL-2.0 licensing; exact code provenance matters.

## Unresolved before foundation decision

Whole-tree dependency manifest, source-to-runtime registration, glTF memory hardening, ZScript game boot, Windows build, GPU performance, release asset rights, maintainer update strategy. All require Phase 00 follow-up and/or Phase 01 authorization.
