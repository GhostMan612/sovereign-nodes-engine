# SRC-GZDOOM-001 — GZDoom source-reference lane

**Pin:** `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`
**Status:** SELECTED FILES VERIFIED / NO BUILD.

- [`CMakeLists.txt`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt) — Requires at least CMake 3.16, sets C++17, includes Windows vcpkg configurations; actual installed dependency set not enumerated.
- [`src/common/models/voxels.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/voxels.cpp) — Voxel asset internals exist in upstream source.
- [`src/common/models/models_voxel.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/models_voxel.cpp) — Voxel-to-model renderer implementation exists.
- [`src/r_data/voxeldef.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/voxeldef.cpp) — Voxel definition ingestion/parser is source-visible.
- [`src/r_data/gldefs.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/gldefs.cpp) — GLDEFS parser/lighting definitions source path.
- [`src/scripting/zscript/zcc_compile_doom.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/scripting/zscript/zcc_compile_doom.cpp) — ZScript compiler path in engine.
- [`src/g_hub.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_hub.cpp) — Hub/transition research starting point, not proof of seamless streaming.
- [`LICENSE`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/LICENSE) — Root GNU GPL version 3 terms; review file-level exceptions before redistribution.

### Extension strategy

Use existing voxel loader and actor binding logic before inventing new voxel-meshing infrastructure. For modern glTF, compare experimental BiasedDoom's implementation and upstream interfaces under a legally reviewed patch plan. Keep ZScript core untouched during initial probes.

### Open verification

Compare renderer-specific voxel paths, dynamic lights/shadow limits, generated asset format compatibility, Windows build dependencies, save compatibility, and submodule licenses. CMake presence alone does not establish that local compile succeeds.
