# WO-F — Sprite families, GLDEFS and DoomEdNum discriminating test plan

**State: TEST-SPECIFIED / NOT RUN.** Source observation only at game revision `44034e97fd22129f919a18cadceb84466ef1bcd3` and engine pins in snapshot.

## Finding under examination

Game `zscript/core.zs` declares `ORE_FRAME = "ORESHAA0"`, `LOCATOR_FRAME = "TOOLAA0"` and `ALTAR_FRAME = "ELECA0"`. `game/GLDEFS.txt` names `ORESHAA0` and `TOOLAA0`. GZDoom `src/r_data/sprites.cpp` indexes four-character sprite-family prefixes with frame/rotation suffixes. **This is a plausible mismatch, not proven missing rendering**: packed resource aliases and other loading code must be checked.

## Cases

| ID | Setup/controlled variable | PASS oracle | Negative control / failure |
|---|---|---|---|
| SPR-01 | unchanged PK3 + official resource ref + actor for `OreShard` | correct visible ore sprite and pickup/inventory | intentionally unknown frame in disposable copy is detected |
| SPR-02 | unchanged locator actor | correct visible locator, expected DoomEdNum and HUD | absent class/frame in disposable copy is caught |
| SPR-03 | unchanged `ELECA0` altar | intended frame and altar interaction | remove frame *only from fixture*; missing asset detectable |
| SPR-04 | unchanged GLDEFS in identical scene | ELEC/ORESHA/TOOLA lights associated with their actors, lights-off comparison changes scene | omit fixture-only binding with definition retained |
| SPR-05 | one-variable alternate sprite-family alias in temporary fixture | isolating alias changes rendering while logic/collision/hitpoints remain equal | if logic changes, fixture invalid |
| SPR-06 | same unchanged PK3 on GZ then UZ | per-engine identical actor identities or exact documented deviations | any vanilla-map fallback invalidates result |

## Capture checklist

Record build/engine SHA, original PK3 SHA, fixture hash if changed, IWAD provenance, exact actor/ZScript class, map, DoomEdNum, sprite resource name inside PK3 (never include copyrighted resource bytes), renderer/backend, light binding/log, screenshots of both on/off control, interaction/HUD behavior, tester and reviewer. Don't use the presence of a filename or `pointlight` block as proof an actor has emitted the light.

## Disposition

- Both engines fail B0 and one-variable fixture repairs → investigate original packaging/name scheme in **separate approved game repair work order**.
- Only one engine fails B0 under identical resources → candidate compatibility investigation.
- Missing map identity, missing negative control or undocumented fixture changes → INCONCLUSIVE/NOT RUN, never PASS.

Sources: [game sprite definitions](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/zscript/core.zs), [game light definitions](https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt), [GZDoom sprite loader](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp).
