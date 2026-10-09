# WO-000D — Scene and workload equivalence design

**Precondition:** C-001…C-008 from WO-000C passed on the same binary/content identities. All listed scenes are plans, not generated WADs.

| Scene ID | Maps/assets | Purpose | Controls |
|---|---|---|---|
| SC-00 | custom MAP01 GapNode, engine-native original sprite actors | minimal gameplay/logic baseline | fixed viewpoint, no dynamic lights, no mods other than game PK3 |
| SC-01 | GapNode inventory, altar and locator present | confirm HUD and actor draw correctness | fixed actor count, custom identifiers and sprite frames verified |
| SC-02 | same geometry, 0/2/8/16 visible GLDEFS lights | dynamic-light increment test | same colors/radii, shadow mode, screen resolution |
| SC-03 | same geometry with opt-in voxel replacement | model pipeline and draw-call cost | same ZScript actor physics/state/collision, independent rendered visibility proof |
| SC-04 | glTF/glb synthetic model fixture where engine supports it | geometry, skeleton and texture comparison | external textures vs embedded texture separate; feature flags recorded |
| SC-05 | MAP01 → MAP02 Breach → MAP03 Warren | loading/transitions + save state | separate transition latency from gameplay frametime |
| SC-06 | one extended deterministic loop | thermal drift/stability | sample temps/clocks and first/last window separately |

## Fixture provenance

Test fixture changes only in a separately authorized copy of the game, not SNE or original game repo. Store source SHA, fixture recipe and hash. Never silently patch gameplay scripts in order to make a candidate appear compatible. Reuse same map/PK3 hash when possible; if a candidate requires an adapter, create separate configuration with a documented compatibility cost and exclude from direct A/B without normalization.

## Metrics needed

Per scene: correct map/actors/lights, selected renderer, artifacts (if any), mean FPS, 1% low, frame-time p50/p95/p99, thermal/RAM, cold/warm load durations, crashes/recovery, video frame or screenshot evidence and tester. `SC-04` cannot be scored for a candidate that lacks glTF without recording that feature as unsupported/unimplemented rather than silently omitting the trial.
