# F-02 — Author recheck of pinned game-source packaging and handoff paths

- Checked: `2026-10-09`; mode: selected read-only GitHub source fetch.
- Game source commit: `44034e97fd22129f919a18cadceb84466ef1bcd3`; planning parent: `725fded39c0d50139ab76182211e32375bc2764e`.
- Source-only, independently reviewed? **NO**. Build/packager/validator actually run? **NO**. B0 PK3 and IWAD hash? **UNKNOWN**.

| Observation ID | Pinned source path and Git blob from prior selected review | Exact source-level claim | Runtime implication unverified |
|---|---|---|---|
| F02-S01 | `tools/build_pk3.py` `547c1f552de2e60373c112d7fd3a8717a72ae4db` | `collect()` adds root `MAPINFO`, `GLDEFS`, referenced `zscript/*.zs`, optional doomednum, `maps/*.wad` and `sprites/*` | package run and gameplay untested |
| F02-S02 | same `build_pk3.py` lines ~389–418 | comments explicitly explain **excluding SNDINFO** due to unsupported aliases on earlier non-stock IWAD | absence of SNDINFO is expected for this pinned builder, not a universal rule |
| F02-S03 | `game/MAPINFO.txt` `c26536e370e70376d47c35d9c984ef7db6d0215e` | `version "4.14"`, three `addfragments`, MAP01 GapNode→MAP02 Breach→MAP03 Warren | actual custom maps cannot be assumed loaded |
| F02-S04 | `game/GLDEFS.txt` `b98abc8de454617fc5681fb585ac8d41cee71bc9` | binding names include `ELECA0`, `ORESHAA0`, `TOOLAA0` | emitted lights UNKNOWN |
| F02-S05 | `zscript/core.zs` `61fb41c797d909404153d77bab894704637ceba4` | ore/locator frame strings longer than conventional 4-letter family+frame notation | visible actor UNKNOWN |
| F02-S06 | `src/world/fps_launcher.gd` `7bbd446af0fb3e9c7f8e2646863101e06fc23f3a` | Godot serializes `hasParadox` boolean via `bool()` and `JSON.stringify` | receive semantics UNKNOWN |
| F02-S07 | `zscript/sn_handoff.zs` `c83a8058d602ee6d1c6a7aca2792a5d408db2ebb` | `ScanInt` on JSON boolean, `ToInt(0,out)` followed by `paradoxFlag != 0`; missing/newer schema warned yet parsed | literal true/false effect UNKNOWN |
| F02-S08 | `tools/validate_wads.py` `cff34dc0934568ab7311b9cdc062a92743e78a77` | WAD validator code exists | validator execution NOT RUN |
| F02-S09 | absent `tools/validate_pk3.py` exact path at above pin | prior direct lookup 404, but source mentions file and `build_pk3.py` now provides checks | complete source tree/rename investigation PENDING |

## Primary links

- [Build PK3](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py#L380)
- [MAPINFO](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt#L25)
- [Core ZScript](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs#L62)
- [GLDEFS](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt#L21)
- [Godot writer](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd#L190)
- [Doom reader](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs#L178)

Author recheck is not independent reviewer G7. Some earlier source comments are historically self-descriptive or speculative; treat them as text, not verified engine behavior. No original game source was changed.
