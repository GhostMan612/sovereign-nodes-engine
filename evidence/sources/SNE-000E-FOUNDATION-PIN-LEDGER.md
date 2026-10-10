# WO-E — Immutable source and research baseline ledger

**Review:** 2026-10-09. Claims are selected upstream source observations from A–D and targeted connector inspections, not compiled binaries. All links intentionally point at immutable Git commits. License, behavior and README are separate proof classes.

| ID | Repository / exact SHA | Key source files and purpose |
|---|---|---|
| SNE | [GhostMan612/sovereign-nodes-engine](https://github.com/GhostMan612/sovereign-nodes-engine/tree/1f21e4c99da50c83ac0c90d14b2f14a752ae89f4) `1f21e4c99da50c83ac0c90d14b2f14a752ae89f4` | WO-A/B/C/D research and source evidence; WO-E preimage guard |
| GAME | [GhostMan612/Sovereign-Nodes](https://github.com/GhostMan612/Sovereign-Nodes/tree/44034e97fd22129f919a18cadceb84466ef1bcd3) `44034e97fd22129f919a18cadceb84466ef1bcd3` | `games/SovereignNodesFPS/game/MAPINFO.txt`, `GLDEFS.txt`, `zscript/core.zs`, `zscript/hud.zs`, `zscript/sn_handoff.zs`; game content from WO-C |
| GZ | [ZDoom/gzdoom](https://github.com/ZDoom/gzdoom/tree/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7) `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | `CMakeLists.txt`, `src/r_data/sprites.cpp`, `src/r_data/voxeldef.cpp`, `src/r_data/gldefs.cpp`, `src/g_level.cpp`; ZScript path from WO-B |
| UZ | [UZDoom/UZDoom](https://github.com/UZDoom/UZDoom/tree/dbedcc894fb6866c48520cf27ae773f9957024b9) `dbedcc894fb6866c48520cf27ae773f9957024b9` | `CMakeLists.txt`, `CONTRIBUTING.md`, `src/r_data/gldefs.cpp`, `src/g_hub.cpp`, `src/g_level.cpp`, `src/r_data/voxeldef.cpp`; policy, inheritance, toolchain |
| BD | [EricsonWillians/BiasedDoom](https://github.com/EricsonWillians/BiasedDoom/tree/6147e0670458e48e63d1a40750f36dfc68b00f7f) `6147e0670458e48e63d1a40750f36dfc68b00f7f` | `CMakeLists.txt`, `vcpkg.json`, `src/common/models/model_gltf.cpp`, `docs/gltf/README.md`, `docs/scripting/python.md`; conditional model/Python claims |

## Select immutable links

- [Game MAPINFO](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt)
- [Game GLDEFS](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt)
- [Game handoff](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs)
- [GZDoom sprite frame code](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp)
- [GZDoom voxel definition](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/voxeldef.cpp)
- [GZDoom level transition](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_level.cpp)
- [UZDoom CMake](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt)
- [UZDoom contribution rules](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md)
- [BiasedDoom model loader](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp)
- [BiasedDoom Python security documentation](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/scripting/python.md)

## Provenance limits

Earlier source records A–D contain the source observations; this summary does not mean all dependencies, symbols or asset copyrights were exhaustively reviewed. Before implementing, compile or benchmark, recheck current release/test pin, preserve this old immutable research record, and record exact binary/fixture hashes. No claim of a latest upstream release or measured status is made here.
