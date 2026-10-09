# SNE-WO-000C — Dynamic-light budget design

## Baseline

The existing GLDEFS declares pointlights `ELEC`, `ORESHA`, `TOOLA` and `light` associations referencing `ELECA0`, `ORESHAA0`, `TOOLAA0`. The engine GLDEFS parser and actor light association paths exist in GZDoom and UZDoom. A configured light is not proof that the intended actor emitted it.

## Proposed deterministic scene (not shipped)

- Same MAP01 static camera, same actor instances, same screen dimensions, FOV and renderer settings.
- Count sweep: **0 / 2 / 8 / 16** visible dynamic lights. This tests the renderer; no fixed shipping cap decided.
- Per-case three warm captures; separately record cold shader compilation and CPU stalls.
- Lighting controls: shadow mode off/on (if backend supports), number of visible lights, radius, falloff, translucent surfaces and number of overlapping lights.
- Distinguish definition/binding/parser errors from performance shortcomings.

## Proposed graphics profiles

| Profile | Light behavior | Shadows | Model effect | Fallback |
|---|---|---|---|---|
| P0 LEGACY | authored sector/static lighting, dynamic effects off | off | native sprites | guaranteed first test lane |
| P1 HYBRID-LITE | limited visible actor lights, profile-budget-controlled | off | selective KVX | revert to P0 on measured failure |
| P2 HYBRID | measured light count and optional model features | optional selectively | more KVX/glTF only where proven | downgrade independent features |
| P3 EXPERIMENTAL | stress counts and enhanced postFX/shadows | controlled on | animation/PBR options | NOT default on UHD 620 |

## Quality oracle

Correct per-actor light color/position and scene change, no missing attachment, no bogus all-white scene; capture the light-on/off control and engine renderer identity. Performance oracle includes frame-time percentiles, not merely average FPS. No per-profile FPS is asserted here.

## Candidate extension rule

Change authored GLDEFS/model presentation first, not generalized engine lighting pipeline. Any new renderer path must be optional, bounded, and backwards compatible with P0. If source game sprite frame names do not bind, fix/verify that first under a separate approved work order.

Sources: https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/GLDEFS.txt; https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/gldefs.cpp; https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/r_data/gldefs.cpp.
