# SNE-SRC-GAME-003 — Pinned game-path compatibility inspection

**Repository:** `GhostMan612/Sovereign-Nodes`
**Commit:** `44034e97fd22129f919a18cadceb84466ef1bcd3`
**Date:** 2026-10-09
**Status:** selected files inspected (SOURCE); engine NOT RUN.

## Direct observations

1. `game/MAPINFO.txt` begins its meaningful directives with `version "4.14"`; declares three `addfragments` and MAP01→MAP02→MAP03 with titles GapNode, Breach, Warren. Three different cluster IDs are declared, but no shared hub is thereby guaranteed.
2. `game/GLDEFS.txt` declares bound lights for `ELECA0`, `ORESHAA0`, `TOOLAA0` and globalfog. Light visibility is unobserved.
3. `zscript/core.zs` includes frame constants `ORE_FRAME="ORESHAA0"`, `LOCATOR_FRAME="TOOLAA0"`, `ALTAR_FRAME="ELECA0"`; unusual lengths raise a high-priority question compared with pinned engine parser.
4. `zscript/doomednum.txt` maps 9033, 9034, 9035, 9036, 9040, 9041 to named custom things. No real placement/interactivity test.
5. `zscript/hud.zs` defines `SNStatusBar`, `DrawHUD` and `DrawScoreBoard`; source contract only.
6. `FpsLauncher.write_handoff()` emits JSON values including `hasParadox: bool(...)`; Doom `sn_handoff.zs` uses `ScanInt` for same key. Missing/newer schema is warning-tolerant; source does not support strict rejection claim.
7. `tools/build_pk3.py` checks source naming/fragments/keys but does not substitute for a real renderer load. `tools/validate_wads.py` has a project-generator-specific WAD-directory-at-12 invariant, not a general WAD-format law.

## File links

- [MAPINFO](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt)
- [GLDEFS](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt)
- [core.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs)
- [hud.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/hud.zs)
- [sn_handoff.zs](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/sn_handoff.zs)
- [doomednum.txt](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/doomednum.txt)
- [fps_launcher.gd](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodes/src/world/fps_launcher.gd)
- [build_pk3.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/build_pk3.py)
- [validate_wads.py](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/tools/validate_wads.py)

**Inferences not proved:** Whether long sprite names render or fail, whether `hasParadox` is wrong at runtime, whether maps transition as intended. These are *tests to perform*, not verdicts.
