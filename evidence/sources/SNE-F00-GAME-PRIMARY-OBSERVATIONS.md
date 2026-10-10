# F-00 — Original-game selected source observations (AUTHOR SOURCE REVIEW ONLY)

Source repository: `https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/`; commit `44034e97fd22129f919a18cadceb84466ef1bcd3`. Lines below are from retrieved source at the pinned revision; an independent reviewer has **not** signed off.

| ID | Pinned source location | What is actually visible | What is NOT established |
|---|---|---|---|
| F00-C01/02 | `game/MAPINFO.txt` lines 25–29, 36–56 | `version "4.14"`, 3 fragments and three named maps | custom maps actually loaded or transitions succeed |
| F00-C03 | `zscript/core.zs` lines 63–74 | `ORE_FRAME="ORESHAA0"`, `LOCATOR_FRAME="TOOLAA0"` | that sprites render, or fail |
| F00-C04 | `game/GLDEFS.txt` lines 21–59 | three pointlight/light definitions with named texture strings | engine emits intended actor lights |
| F00-C06 | `src/world/fps_launcher.gd` lines 190–210 | JSON dictionary has `"hasParadox": bool(...)` | final ZScript value after runtime conversion |
| F00-C07/08 | `zscript/sn_handoff.zs` lines 158–248 | warning-tolerant schema, `ScanInt` on `KEY_PARADOX`, `ToInt` parsing | exact engine conversion outcome, absence of malformed-input problems |
| F00-C09 | `zscript/core.zs` lines 30–36 and 63–66 | comments claim `validate_pk3.py` exists | literal tool existence (direct file fetch returned 404) |
| F00-C10 | `tools/build_pk3.py` lines 60–91 and 345–352 | fragment checks and import/use of `validate_wads` | whether local script was executed successfully |
| F00-C16 | `tools/validate_wads.py` | validator source file exists in pinned Git | generated WADs are valid/playable |

## Highest-risk source limitation

Long names can conflict with GZDoom's conventional four-character sprite-family parser. Do not infer an actual run result without the unchanged original PK3 and lawful game-resource metadata. Similarly, ZScript `ScanInt` receives a boolean token from Godot's JSON producer in the source design, but **the effect of `.ToInt` on JSON tokens has not been proven by executing the engine**.

## Correct reviewer disposition

For each row inspect surrounding logic and alternate interpretations, then record `SUPPORTED-SOURCE`, `CORRECTION-REQUIRED`, `DISPUTED` or `RUNTIME-DEPENDENT`. No `PASS C-001…C-015` may be entered from this source memo. Game source and game repo were not edited by the author.
