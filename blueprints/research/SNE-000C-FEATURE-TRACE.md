# SNE-WO-000C — Feature/source-to-test trace ledger

Each line anchors a **source observation**, not a running-engine assertion. Pinned source records use date 2026-10-09.

| Trace | Game path / symbol | Candidate seam | Test(s) | Known uncertainty |
|---|---|---|---|---|
| FT-01 | `game/MAPINFO.txt` (`version 4.14`, `addfragments`) | GZDoom/UZDoom `src/scripting/thingdef.cpp`, front-end compiler | C-001/C-002 | parser and PK3 actual load |
| FT-02 | `MAPINFO` Map01/02/03 `next` | `src/g_level.cpp`, `src/g_hub.cpp` | C-003/C-009 | map output and state carry |
| FT-03 | `game/GLDEFS.txt` ELEC/ORESHA/TOOLA | `src/r_data/gldefs.cpp`, actor light association | C-005/C-012 | actual attachment, sprite name |
| FT-04 | `zscript/core.zs` OreShard, actor tags, sprites | `src/r_data/sprites.cpp`, scripting actor finalization | C-004/C-011 | long sprite names suspect |
| FT-05 | `zscript/doomednum.txt` numbers 9033-36, 9040-41 | actor/editor ID lookup | C-004/C-008 | startup/gameplay proof |
| FT-06 | `zscript/hud.zs` SNStatusBar | ZScript StatusBar and scoreboards | C-007 | actual UI draw calls |
| FT-07 | `fps_launcher.gd` FpsLauncher.write_handoff | separate process + temp JSON | C-006/C-015 | stale path, schema and boolean |
| FT-08 | `zscript/sn_handoff.zs` ScanInt/ScanRaw | ZScript File I/O + HUD event state | C-006/C-015 | `hasParadox` bool and tolerances |
| FT-09 | `tools/build_pk3.py` check_fragments/check_handoff_contract/check_sprites | project packaging/validation | C-001/C-002/C-004/C-008 | existence != runtime decode |
| FT-10 | `tools/build_maps.py`, `tools/validate_wads.py` | map lump parser/semantics | C-008 | generator-specific header layout |
| FT-11 | no game VOXELDEF in this review | GZ/UZ `src/r_data/voxeldef.cpp`, `src/common/models/models_voxel.cpp` | C-011 | proposed fixture not current feature |
| FT-12 | optional model replacement only | BiasedDoom `model_gltf.cpp`, `fastgltf` option | C-011b | glTF texture & compile proof |
| FT-13 | optional advanced lighting | GLDEFS + renderer light queues | C-012 | specific backend/driver profile |
| FT-14 | hub handoff is **cross-process**, not world stream | `g_level.cpp`, `g_hub.cpp` | C-003/C-009/W-001..004 | active multi-zone execution not implemented |
| FT-15 | ZDaemon notes in game repository | ZDaemon separate engine family | C-014 | DO NOT assume ZScript/GLDEFS parity |

## Source pin references

- Game: https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt
- GZDoom sprite: https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp
- UZDoom hub: https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_hub.cpp
- BiasedDoom model: https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp

## Reviewer instructions

For each future candidate build, walk the trace top to bottom, capture one test verdict per item and do not silently leave untestable features out. `NOT APPLICABLE` requires an explained scope decision, not simply an absent engine feature.
