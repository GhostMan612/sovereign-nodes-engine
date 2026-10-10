# WO-E — Prefer compatibility adapters before engine fork modifications

## Hypothesis hierarchy (least invasive first)

1. **Stock engine + correctly authored game content** for MAPINFO/ZScript/GLDEFS and existing map identity.
2. **Game-side fixture-only corrections** to diagnose intrinsic game mistakes without editing the authoritative game repository; a permanent fix would need its own authorization.
3. **Data-defined actor visuals** using the inherited voxel/VOXELDEF and/or compatible model configuration; preserve actor physics and simulation.
4. **Optional isolated extension module/bridge** for synthetic handoff and world metadata, bounded import/export. Check engine API and save semantics.
5. **Pinned downstream engine fork** only for genuinely unavailable safe seams (glTF integration, advanced rendering or stream-loading), with documented patch budget and GPL/license lineage.
6. **Rewrite** only after objective engineering case. A glossy screenshot cannot justify replacing the simulation or ZScript compiler.

## Fork admissibility requirements

- Define one upstream base/tag, patch directory ownership, comparison tests and reproducible binary identity.
- Preserve source license notices; verify all linked/embedded dependencies and binary distribution obligations.
- Set merge cadence, conflict budget, long-term maintainer and rollback to stock baseline.
- Avoid binding trusted private Mantle data to game runtime or Python mod API.
- Do not confuse UZDoom code PR policy with its underlying license terms; upstream contribution restrictions still matter for maintenance strategy.

## Open tests

VOXELDEF lookup/rotation naming, GLDEFS frame association, `MODELDEF` vs glTF conditional registry, savegame/reserialization, rendering backend fallback, physics and memory safety. This file grants zero implementation authority.
