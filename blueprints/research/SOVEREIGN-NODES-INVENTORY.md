# Existing Sovereign Nodes implementation — read-only source inventory

**Source:** https://github.com/GhostMan612/Sovereign-Nodes  
**Inspection:** GitHub connector file reads, 2026-10-09. **Commit SHA not pinned; content may change.**  
**State:** PARTIALLY VERIFIED SOURCE; RUNTIME NOT TESTED.

## Game split

The upstream game README and AGENTS distinguish two separate products:

- `games/SovereignNodes/`: Godot 4 isometric hub/minigames.
- `games/SovereignNodesFPS/`: standalone ZDoom/GZDoom-family FPS distributed as `.pk3`, separate from the Godot runtime, with a stated ZDaemon target. Do not assume features available in one runtime work in the other.

## Confirmed files and observed contracts

| File | Read-only observation | Required parity check |
|---|---|---|
| `games/SovereignNodesFPS/game/MAPINFO.txt` | Declares `version "4.14"`, fragments `zscript/core.zs`, `zscript/sn_handoff.zs`, `zscript/hud.zs`; defines MAP01 GapNode → MAP02 Breach → MAP03 Warren; clusters 1/2/3. | All fragments load and exactly those maps boot/transition, no IWAD fallback |
| `games/SovereignNodesFPS/game/GLDEFS.txt` | Defines ELEC, ORESHA, TOOLA pointlights with sprite-frame bindings `ELECA0`, `ORESHAA0`, `TOOLAA0`, and `globalfog`. | Correct packaging path, bind and observed emitted light in scene |
| `games/SovereignNodesFPS/zscript/core.zs` | Declares `SNConst` sprite/frame symbols and gameplay classes. Source comments document historical failures with invalid fields and IWAD fallback. | Compile/load custom classes and sprites, prove functional interaction |
| `games/SovereignNodesFPS/zscript/sn_handoff.zs` | Implements a declared Godot→Doom handoff protocol with `HANDOFF_SCHEMA_VERSION = 1`; comments discuss OS temp path and scalar parsing. | Handoff consumer actually receives fresh validated synthetic payload, rejects invalid schema |
| `games/SovereignNodesFPS/zscript/hud.zs` | File referenced by MAPINFO; contents not reviewed in this pass. | HUD appears, state values tested |
| `games/SovereignNodesFPS/maps/SovereignNodes_MAP01_GapNode.wad` | Existing named map file (listing); binary internals not reviewed. | Package loads MAP01, custom markers confirm identity |
| `games/SovereignNodesFPS/maps/SovereignNodes_MAP02_Breach.wad` | Existing named map file (listing); binary internals not reviewed. | MAP01→MAP02 transition |
| `games/SovereignNodesFPS/maps/SovereignNodes_MAP03_Warren.wad` | Existing named map file (listing); binary internals not reviewed. | MAP02→MAP03 transition and endpoint handling |

## Warnings from project documentation (not validated runtime conclusions)

- `SESSION_HANDOFF.md` describes previous missing reads, map generator width errors, definitions packaged below `game/`, and ZScript compile errors. These are **historical project-reported findings**, not proof that current revision passes.
- `MAPINFO.txt` and GLDEFS comments describe load-order and light-binding pitfalls; the package's verification cases must catch them.
- The Doom-side handoff reader exists as source, but the behavior is not declared PASS until an actual Godot→Doom end-to-end proof is captured.
- The game repository's shell/verification discipline is operator policy; preserve local change-control requirements during audit.

## Unresolved

Pin source commit; review build scripts/PK3 manifests; inspect handoff producer and spec, data generator, HUD and WAD binary metadata; confirm ZDaemon-specific limitations; benchmark. No original game file is embedded in this package.
