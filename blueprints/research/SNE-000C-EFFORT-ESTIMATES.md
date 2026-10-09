# SNE-WO-000C — Relative feasibility sizing (non-committal)

**Method:** T-shirt ranges represent *architecture coupling and risk*, not days, costs, lines of code, staffing estimates or completed work. Actual estimate requires a chosen pinned upstream, measured builds and confirmed source seams.

| Capability | Likely path | Relative complexity | Dominant unknown |
|---|---|---|---|
| Preserve current MAPINFO and ZScript | adapt/preserve inherited engine | M | current custom sprite/handoff parser issues |
| Preserve authored GLDEFS pointlights | inherited parser and renderer | S–M | binding correctness and UHD 620 cost |
| Static KVX actor visual replacement | inherited VOXELDEF | S–M | content naming, rotation/frames and state invariance |
| Rich model+animation in BiasedDoom | conditional glTF + fastgltf | M–L | texture, GPU support, skeletal animation, fork maintenance |
| Port glTF into selected GZDoom/UZDoom | isolate model loader/render path | L–XL | license/dependencies/backend registration, LTS merges |
| Add read-only synthetic Mantle snapshot adapter | separate authorized process boundary | M–L | schema, trust, consent, data minimization |
| Conventional map transition with state | reuse level/hub systems | M | save compatibility, source game's cluster configuration |
| Perceptually seamless prefetch | new asset streaming presentation | L–XL | engine renderer/resource lifecycle, thermal/memory |
| Truly continuous mega-world | new multi-zone simulation renderer/physics | XL/research | BSP/map namespace, lighting, AI, save consistency |

Do not start implementation based on this rough sorting. Unknowns and independent review take precedence over attractive product descriptions.
