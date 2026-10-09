# SNE-WO-000B — Pinned source revision ledger

**Inspection:** 2026-10-09, GitHub repository connector. All references are immutable commit-based links. A pinned commit identifies reviewed code, **not** a successful build or an endorsement of latest stable releases.

| ID | Repository | Pin | Role |
|---|---|---|---|
| B00 | [SNE](https://github.com/GhostMan612/sovereign-nodes-engine) | `369722fcd0839447cd5ecf5b78aa1ca7d8e2645c` | Baseline scaffold after WO-000A |
| B01 | [Sovereign-Nodes](https://github.com/GhostMan612/Sovereign-Nodes) | `44034e97fd22129f919a18cadceb84466ef1bcd3` | Current game producer/consumer |
| B02 | [GZDoom](https://github.com/ZDoom/gzdoom) | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | Stable engine candidate |
| B03 | [UZDoom](https://github.com/UZDoom/UZDoom) | `dbedcc894fb6866c48520cf27ae773f9957024b9` | Fork candidate |
| B04 | [BiasedDoom](https://github.com/EricsonWillians/BiasedDoom) | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | Experimental glTF/Python candidate |
| B05 | [Chocolate Doom](https://github.com/chocolate-doom/chocolate-doom) | `895f581c5d91497bdda0516612da803fe5843e28` | Historic compatibility reference |
| B06 | [id Software DOOM](https://github.com/id-Software/DOOM) | `a77dfb96cb91780ca334d0d4cfd86957558007e0` | Historic reference |

## Direct observed source links

### GZDoom

- [CMakeLists.txt](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt) — CMake >=3.16; C++17.
- [src/common/models/voxels.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/voxels.cpp) — voxel resource loader.
- [src/r_data/voxeldef.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/voxeldef.cpp) — `VOXELDEF` parser.
- [src/common/models/models_voxel.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/models_voxel.cpp) — voxel model representation.
- [src/r_data/gldefs.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/gldefs.cpp) — dynamic-light association parser.
- [src/scripting/thingdef.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/scripting/thingdef.cpp) — actor/ZScript integration.
- [src/g_hub.cpp](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_hub.cpp) — hub/intermission state, not simultaneous world streaming.
- [vcpkg.json](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/vcpkg.json) and [LICENSE](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/LICENSE) — preliminary dependency and GPL text.

### UZDoom

- [CMakeLists.txt](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt) — C++20, CMake >=3.16, optional LTO, Python3 build-tool dependency.
- [src/scripting/thingdef.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/thingdef.cpp) and [src/scripting/zscript/zcc_compile_doom.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/zscript/zcc_compile_doom.cpp) — actor/ZScript source.
- [src/common/models/voxels.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/common/models/voxels.cpp) — inherited voxel handling.
- [src/r_data/gldefs.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/gldefs.cpp) — light parser.
- [src/g_hub.cpp](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_hub.cpp) — hub state.
- [CONTRIBUTING.md](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md) — upstream submission restrictions for AI-assisted contributions.
- [LICENSE](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/LICENSE) and [branding/BRANDING-LICENSE.md](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/branding/BRANDING-LICENSE.md) — GPL + separately licensed branding.

### BiasedDoom

- [CMakeLists.txt](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt) — C++17, guarded glTF & Python configuration options.
- [vcpkg.json](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json) — fastgltf / CPython dependencies and version overrides.
- [src/common/models/model_gltf.h](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.h) and [model_gltf.cpp](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp) — glTF model parser, materials, animation, feature macro guard.
- [README.md](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/README.md) — declared feature set and ZScript roadmap.
- [docs/README.md](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/README.md) — explicit external-texture glTF authoring caution.
- [docs/gltf/quick-start.md](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/gltf/quick-start.md) — model replacement workflow using ZScript.

### Existing Sovereign Nodes game

- [MAPINFO](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt), [GLDEFS](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt), [core.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs), [hud.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/hud.zs), [sn_handoff.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs).
- [fps_launcher.gd](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd) — Godot producer.
- [build_pk3.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py), [build_maps.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_maps.py), [validate_wads.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py), [RULES.md](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/RULES.md).

## Provenance limits

The listed files and selected excerpts were read directly; **this is a targeted audit, not a complete indexed clone**. Exact function signatures, all dependencies, update frequency, binary distribution conditions, current system/compiler compatibility, and measured performance remain open unless explicitly documented in source record.
