# SNE-WO-000C — Immutable source revisions and file references

- Review: 2026-10-09; pinned GitHub file reads of selected files only.
- Evidence classification: SOURCE-OBSERVED, DOC-CLAIM, ARCHITECTURAL INFERENCE, or NOT RUN.
- Not a clone/full audit, no source modifications or build/launch.

| Repository | Branch at lookup | Pinned review SHA |
|---|---|---|
| `GhostMan612/Sovereign-Nodes` | `main` | [`44034e97fd22129f919a18cadceb84466ef1bcd3`](https://github.com/GhostMan612/Sovereign-Nodes/commit/44034e97fd22129f919a18cadceb84466ef1bcd3) |
| `ZDoom/gzdoom` | `master` | [`c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`](https://github.com/ZDoom/gzdoom/commit/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7) |
| `UZDoom/UZDoom` | `trunk` | [`dbedcc894fb6866c48520cf27ae773f9957024b9`](https://github.com/UZDoom/UZDoom/commit/dbedcc894fb6866c48520cf27ae773f9957024b9) |
| `EricsonWillians/BiasedDoom` | `master` | [`6147e0670458e48e63d1a40750f36dfc68b00f7f`](https://github.com/EricsonWillians/BiasedDoom/commit/6147e0670458e48e63d1a40750f36dfc68b00f7f) |

## Reviewed links by repository

Use these immutable links in defect reports; `main`, `master`, `trunk` alone is not sufficient provenance. `Read` means content was inspected; not every line in each file was audited.

### GhostMan612/Sovereign-Nodes

- [`games/SovereignNodesFPS/game/MAPINFO.txt`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt)
- [`games/SovereignNodesFPS/game/GLDEFS.txt`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt)
- [`games/SovereignNodesFPS/zscript/core.zs`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs)
- [`games/SovereignNodesFPS/zscript/hud.zs`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/hud.zs)
- [`games/SovereignNodesFPS/zscript/sn_handoff.zs`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs)
- [`games/SovereignNodesFPS/zscript/doomednum.txt`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/doomednum.txt)
- [`games/SovereignNodesFPS/tools/build_pk3.py`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py)
- [`games/SovereignNodesFPS/tools/build_maps.py`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_maps.py)
- [`games/SovereignNodesFPS/tools/validate_wads.py`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py)
- [`games/SovereignNodes/src/world/fps_launcher.gd`](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd)

### ZDoom/gzdoom

- [`src/r_data/sprites.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp)
- [`src/r_data/gldefs.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/gldefs.cpp)
- [`src/r_data/voxeldef.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/voxeldef.cpp)
- [`src/common/models/voxels.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/voxels.cpp)
- [`src/common/models/models_voxel.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/common/models/models_voxel.cpp)
- [`src/g_level.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_level.cpp)
- [`src/g_hub.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_hub.cpp)
- [`src/scripting/thingdef.cpp`](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/scripting/thingdef.cpp)

### UZDoom/UZDoom

- [`src/r_data/gldefs.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/gldefs.cpp)
- [`src/r_data/voxeldef.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/voxeldef.cpp)
- [`src/common/models/voxels.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/common/models/voxels.cpp)
- [`src/g_level.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_level.cpp)
- [`src/g_hub.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_hub.cpp)
- [`src/scripting/thingdef.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/thingdef.cpp)
- [`CONTRIBUTING.md`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md)

### EricsonWillians/BiasedDoom

- [`src/common/models/model_gltf.cpp`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp)
- [`src/common/models/model_gltf.h`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.h)
- [`CMakeLists.txt`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt)
- [`vcpkg.json`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json)
- [`README.md`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/README.md)
- [`docs/gltf/README.md`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/gltf/README.md)
- [`docs/scripting/python.md`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/scripting/python.md)
- [`docs/engine/procedural-map-generation.md`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/engine/procedural-map-generation.md)

## Uninspected links and reference class

- Doom/ZDoom documentation on sprite namespace: https://zdoom.org/w/index.php?title=Sprite (supporting documentation, not pinned to Git commit).
- Mainstream VOXELDEF guide: https://zdoom.org/wiki/VOXELDEF (reference only; source parser above is authoritative for pinned candidate).
- UZDoom AI-assisted PR policy: pinned `CONTRIBUTING.md` above; does not itself determine GPL fork obligations.

## Provenance limitations

`SNE-WO-000C` describes a compatibility experiment *proposal*. It does not assert output from any engine binary. Source code might differ at future revisions, with warnings about sprite prefixes and handoff decoding requiring runtime checks. The user's installed GZDoom 4.14.2 binary is not identified as either of the checked upstream commits. No game repo file or upstream source is copied into the ZIP.
