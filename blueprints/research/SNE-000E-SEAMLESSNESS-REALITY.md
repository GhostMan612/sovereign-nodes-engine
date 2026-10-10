# WO-E — Seamless-world terminology and cost realism

## Four levels of continuity

| Stage | Meaning | Source-backed current relevance | Unknown proof |
|---|---|---|---|
| W1 | map-to-map exits with explicit next target | existing MAPINFO MAP01→MAP02→MAP03 | transitions/identity and runtime error handling |
| W2 | logical world state persisted across zones/revisits | source hub/level machinery exists GZDoom/UZDoom | save/reload, snapshots, cluster semantics and state conflict |
| W3 | player-perceived smooth transition (preload/fade/transport) | presentation idea only | loading time, synchronization, camera/audio continuity |
| W4 | simultaneous physically connected world with true streaming and no map swap | **NOT PROVEN** by map hub mechanisms | architecture study of BSP/collision, renderer portals, sound/nav/AI, memory, save and multiplayer |

'One huge Doom world' may be approximated with zone links, but conventional map changes do not constitute a single streaming game space. Physical seamless world demands major engine architecture and low-end memory/GPU work; do not let the planned feature determine fork selection before W1/W2 and Tier-A pass.

## Decision strategy

Treat W1/W2 as foundation compatibility requirements; W3 as an optional future enhancement; W4 as separate high-risk architecture research, never a presumed Phase 01 checkbox. Preserve rollback to conventional MAPINFO exits.
