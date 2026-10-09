# SRC-GZ-002 — GZDoom implementation observations

**Pin:** `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`
**Evidence class:** Direct selected source inspection; no compilation/runtime test.
**Reviewed:** 2026-10-09

| Concern | Direct source evidence | SNE interpretation |
|---|---|---|
| Build | [CMakeLists.txt](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt) | CMake minimum 3.16; C++17; not proof of successful Windows build |
| Voxel import | [voxels.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/voxels.cpp) | Existing voxel palette remap and loader path; do not reinvent for model replacements |
| Sprite association | [voxeldef.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/voxeldef.cpp) | `VOXELDEF` maps sprite/frame names to voxel definitions; proposed first voxel tests can use this seam |
| Renderable voxel | [models_voxel.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/models_voxel.cpp) | Model interface and texture conversion exists; renderer-path-specific costs need profiling |
| Lighting | [gldefs.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/gldefs.cpp) | Explicit `AddLightDefaults` / `AddLightAssociation` references; engine has actor/frame attachment workflow |
| Actor definitions | [thingdef.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/scripting/thingdef.cpp) | Inherited ZScript/actor class compiler integration; exact SNE custom classes require runtime proof |
| Hub mechanics | [g_hub.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_hub.cpp) | Stores per-level/intermission hub information when `CLUSTER_HUB`; not proof of seamless physically concurrent maps |
| Licensing | [LICENSE](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/LICENSE) plus individual notices | Main GPL-3 license; `voxels.cpp` is BSD-style notice, `models_voxel.cpp` is LGPL-style. Preserve notices in derivatives |

## Architectural recommendation

Start with VOXELDEF actor-frame replacement and existing light associations. An SNE-specific interface should wrap asset registration and rendering-profile settings **without** rewriting the engine model manager or actor VM. For world continuity, study inherited level transition and serialisation before proposing preloaded zones.

## Blockers

- Full compiler+dependency configuration on Windows and DLL/asset distribution not reproduced.
- No testing with Sovereign Nodes `MAPINFO version "4.14"` and ZScript.
- No profiling for voxel material upload, light count, shadows or drivers.
- Engine sources have per-file license variations; all NOTICE files and packaging require further audit.
