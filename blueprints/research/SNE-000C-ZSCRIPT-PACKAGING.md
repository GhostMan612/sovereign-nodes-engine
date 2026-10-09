# SNE-WO-000C — ZScript, MAPINFO, GLDEFS and PK3 feasibility

## Observed game contract at exact game SHA `44034e97fd22129f919a18cadceb84466ef1bcd3`

- `games/SovereignNodesFPS/game/MAPINFO.txt`: order `version "4.14"`, then `addfragments` for `zscript/core.zs`, `sn_handoff.zs`, `hud.zs`, then MAP01/02/03 definitions.
- `games/SovereignNodesFPS/game/GLDEFS.txt`: ELEC pointlight attached to `ELECA0`; ORESHA to `ORESHAA0`; TOOLA to `TOOLAA0`; fog stanza present.
- `games/SovereignNodesFPS/zscript/core.zs`: SNConst frames `ELECA0`, `ORESHAA0`, `TOOLAA0`; actor and inventory/weapon behaviors.
- `games/SovereignNodesFPS/zscript/doomednum.txt`: editor IDs 9033–9036 and 9040–9041 mapped to custom classes.
- `games/SovereignNodesFPS/tools/build_pk3.py`: checks MAPINFO/fragment references, file existence and handoff keys. A source-level check does not prove parser acceptance or rendered frame selection.

## Crucial sprite decoder discrepancy — suspected, test required

In pinned GZDoom `src/r_data/sprites.cpp`, `R_InitSpriteDefs()` obtains the first **four** characters of sprite names to identify sprite families and uses `GetName()[4]` as frame and `GetName()[5]` as rotation. Conventional example `ELECA0` = `ELEC` + `A` + `0` (six characters). The game uses `ORESHAA0` and `TOOLAA0` (eight and seven characters respectively), so naive file-presence checks may pass while renderer uses unexpected 4-letter families (`ORES`, `TOOL`) and frame characters.

This is a **high-priority source mismatch hypothesis**, not a demonstrated failure of the current game. Validate the resource manager's actual canonical name and sprite-state reference under the selected engine, including the GLDEFS attachment. Names in native GLDEFS parser can be up to 8 characters in one context, which does not override actor sprite-frame parsing rules. Avoid editing the game until a reviewed fix work order.

## Packaging proof requirements

| Gate | Static proof | Runtime proof |
|---|---|---|
| root resources | MAPINFO/GLDEFS at engine-recognized archive location | correct custom map/lighting, not vanilla IWAD |
| fragments | exact canonical `zscript/` includes, no dead parallel path | all gameplay and HUD classes load and execute |
| sprite names | every declared filename physically exists | actual actor frame mapping and light emission |
| DoomEdNums | IDs and tags crosschecked by builder | placed objects instantiate and interact |
| WAD geometry | valid project-generator byte layout and semantics | 3 maps playable, correct doors/walls/exits |
| next-map chain | no dangling MAPINFO target | MAP01→MAP02→MAP03 and end behavior |

**Important scope correction:** `validate_wads.py` insists its *project-generated* WAD directory offset equals 12. That is a generator-specific convention, **not** a universal WAD-format requirement; valid WADs can position their directory elsewhere. Do not hardcode its constraint into a general engine parser.

## Tests and sources

- Test C-001, C-002, C-003, C-004, C-005, C-007, C-008.
- Game MAPINFO https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt
- Game core https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs
- GZDoom sprite parser https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp
- GZDoom GLDEFS parser https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/gldefs.cpp

**No ZScript compile or PK3 runtime was performed.**
