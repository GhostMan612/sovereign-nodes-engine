# SNE-WO-000C — Compatibility-first architectural boundary

## Principle

Do not rewrite Doom simulation to achieve modern visuals. The source game depends on GZDoom-family MAPINFO, ZScript actors/HUD, GLDEFS and map state. Rendering upgrades must be behind optional profiles with a sprite fallback and explicit versioned extension boundary.

## Recommended separation

| Plane | Owner | Allowed in initial roadmap | Not implied |
|---|---|---|---|
| FPS content | Sovereign-Nodes game repo | existing PK3, actors, maps, verified fixture-only tests | wholesale rewrite |
| Compatibility kernel | chosen Doom-family fork *after ADR* | resource loading, ZScript, gameplay, save and level change | source parity without test |
| Visual assets | future optional feature modules | voxel props/actors, conditional glTF for audited engine | geometry model = new game object semantics |
| Lighting | inherited GLDEFS and hardware renderer | bounded dynamic lights, off/fallback control | GPU-specific minimum frame rate |
| Zone transition | existing GZDoom/UZDoom map/hub paths | logical continuity W1/W2 | simultaneous physical zones |
| Mantle adapter | out-of-process future bridge | consented, game-safe, read-only, synthetic test snapshots | private graph access by game scripts |
| Trusted automation | dev/operator tooling | plans and curated static evidence | scripts from arbitrary loaded PK3s |

## Compatibility layer contract

The interface boundary is observable at **resources, actor state, rendering, persistence and external handoff**. A model swap may change only rendering presentation unless an independent gameplay proposal is authorized. Engine-native save format is not assumed cross-fork compatible. Any external bridge uses a bounded versioned document and fail-closed handling for missing/untrusted required fields.

## Two-phase decision loop

1. Choose an unmodified benchmark reference for each candidate, prove Tier-A content on the same game package, then decide whether its changes are compatible enough.
2. Only after operator selects foundation and separately authorizes Phase 01, create fork patch series. Establish upstream merge strategy and test suite first; add new graphics one feature at a time.

## Anti-patterns

- Calling a fade between separately loaded maps seamless streaming.
- Treating a compiled ZScript fragment or a visible vanilla MAP01 as custom-content success.
- Launching unsandboxed embedded CPython for unknown third-party mods.
- Publishing licensed commercial IWAD bytes in test fixtures.
- Concluding an Intel UHD 620 benchmark from a laptop spec sheet.
