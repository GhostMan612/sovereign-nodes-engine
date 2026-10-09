# SNE-WO-000C — World-zone continuity without misleading 'seamless' claims

## Starting fact

Current `MAPINFO.txt` defines **three sequential maps**, MAP01→MAP02→MAP03; it does not declare all maps as one loaded geometry space. GZDoom and UZDoom have `g_level.cpp` transition logic and `g_hub.cpp` hub handling. This is an inheritance seam for **logical** persistence, not proof that both worlds execute or render simultaneously.

## Four staged requirements

| Stage | Implementation concept | Observable acceptance | Blocker |
|---|---|---|---|
| W1 | Honor MAPINFO exit sequence | three distinct named maps and valid exit events | fallback to IWAD or dangling target |
| W2 | Persist explicitly selected mission/actor flags with schema | save/reload/revisit and no state duplication | opaque runtime state lost or corrupt |
| W3 | Optional inter-map visual masking/prefetch | no perceptual flicker; truthful progress; rollback to W1 | excessive memory load / unsupported API |
| W4 | One active seamless mega-world with multiple concurrent zones | uninterrupted camera/collision/AI/audio + deterministic saves | requires dedicated ADR and new engine work |

## Proposed core objects (documentation only)

`ZoneId`, `MapId`, `PortalLink`, `TransitionSnapshot`, `ZoneRegistry`, `WorldSession`, `StateMergePolicy`. Separate **authoritative logical data** from level-local render/geometric data. No implied direct access to Mantle graph; bridge is synthetic read-only later.

## Big Doom world concept

For an E1M1→E1M2 seamless-transition experiment, first test *logical continuity* using the engine's native map-change/save systems. It is more feasible to preserve player state and hide a load than to render both maps and stream BSP nodes while keeping Doom collision/AI semantics. Genuine W4 may require cell-based spatial structures or a different rendering/simulation architecture, independent of the chosen fork. This is not an estimate of ease or a claim a candidate supports it.

## Missing source/data

Actual persisted variables, save serialization guarantees, hub cluster flags in custom MAPINFO, exit semantics, world session authority, and map asset-space conversion all require tests/source audit. Do not presume that separate `cluster = 1,2,3` entries are configured as a shared hub.

Source game: https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt
GZDoom: https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_level.cpp, https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/g_hub.cpp
UZDoom: https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_level.cpp, https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/g_hub.cpp
