# Sovereign Nodes FPS — source inventory (SNE-WO-000A)

**Pinned game SHA:** `44034e97fd22129f919a18cadceb84466ef1bcd3`
**Review:** 2026-10-09 · GitHub source inspection only · **NOT RUNTIME TESTED**
**Full file evidence:** `evidence/sources/SNE-SRC-GAME-001.md`

## Product boundary

- `games/SovereignNodes/` is the **Godot 4** hub and game suite.
- `games/SovereignNodesFPS/` is a **separate ZDoom/GZDoom-based FPS**, packaged as a `.pk3`. Launch is an external process, not an embedded Godot scene.
- Shared lore/data lives separately. Do not copy identifiable family data or licensed IWADs into this project.

## Existing FPS contract inventory

| ID | Observed source | Compatibility contract (runtime pending) |
|---|---|---|
| G01 | `game/MAPINFO.txt` version `4.14` | Engine accepts version directive and map/fragments declarations |
| G02 | `MAPINFO.txt` fragments | `zscript/core.zs`, `zscript/sn_handoff.zs`, `zscript/hud.zs` all load |
| G03 | MAPINFO map chain | MAP01 GapNode → MAP02 Breach → MAP03 Warren, with correct level identity |
| G04 | `game/GLDEFS.txt` | Lights ELEC/ ORESHA/ TOOLA bound to frames `ELECA0`, `ORESHAA0`, `TOOLAA0`; `globalfog` recognized |
| G05 | `zscript/core.zs` | Gameplay actors, inventory, altar, threats, weapon functionality |
| G06 | `zscript/hud.zs` | `SNStatusBar`, custom counters, scoreboard, handoff text |
| G07 | `zscript/doomednum.txt` | Custom DoomEdNum 9033–9036, 9040–9041 actors resolvable |
| G08 | `tools/build_pk3.py` | Definitions placed where loader reads them, validated sprite frames/fragment coverage |
| G09 | `tools/build_maps.py`, `tools/validate_wads.py` | Generated WAD valid under project's map generator/validator constraints |
| G10 | `src/world/fps_launcher.gd` (Godot side) | External executable discovery, IWAD/PK3 selection, launch failure reports |
| G11 | `src/world/fps_launcher.gd` + `sn_handoff.zs` | Shared OS temp-path protocol, v1 JSON schema, run context visible in HUD |
| G12 | `RULES.md` | No secrets, sensitive genealogy, licensed IWADs; explicit paths and project boundaries |

The three map files appear as `maps/SovereignNodes_MAP01_GapNode.wad`, `maps/SovereignNodes_MAP02_Breach.wad`, and `maps/SovereignNodes_MAP03_Warren.wad`. Their *contents were not inspected* in this pass.

## Source-reviewed functional details

- `FpsLauncher` resolves `SOVEREIGN_GZDOOM` / `GZDOOM_EXE`, `DOOM2_WAD` / `DOOMWAD`, and a locally built PK3. Process startup uses an external executable rather than Godot scene loading.
- Schema constants agree in source (`HANDOFF_SCHEMA := 1`; `HANDOFF_SCHEMA_VERSION = 1`). Both sides consult TEMP/TMP/TMPDIR and `SovereignNodes/fps_handoff.json`. Sender also writes a Godot user path.
- Consumer `ScanRaw` is custom scalar scanning rather than a general JSON parser. It deliberately tolerates some missing/version-skew fields. This is **not** a cryptographically authenticated or safely bounded Mantle Bridge.
- The build script contains static cross-language contract checks; the checks have **not been run** by this research.
- `validate_wads.py`'s `dirofs == 12` invariant applies to this generator layout only, not the universal WAD format.

## Test obligation

Every G01–G12 item needs source-specific checks, a packaging validation and/or a live runtime test. Test cases should catch the dangerous **vanilla IWAD fallback** (engine starts but ignores all custom content). No results are declared PASS.

## Remaining file enumeration

Before accepting 000A, inspect map binaries or recorded WAD manifests, the complete class/call graph, script compilation and asset archives. Review target engine ZDaemon limitations as a separate lane. See `blueprints/research/SNE-000A-TIER-A-COMPAT.md`.
