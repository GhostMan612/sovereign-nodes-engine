# SNE-WO-000C — Target-device graphics profiles and measurement method

**Target (reported):** Dell Latitude 5400, i5-8365U, 16GB, Intel UHD 620; **no current benchmark captured**. Graphics profiles are speculative design starting points and may need dramatic reduction after actual measurement.

## Profile ladder

| Profile | Resolution start | Sprites/models | Lights | Renderer/PostFX | Purpose |
|---|---|---|---|---|---|
| P0 legacy | 1280×720 | original sprites | dynamic off | lowest reliable compatibility settings | startup/logic correctness and baseline |
| P1 hybrid-lite | 1280×720 | one/few voxel actors | 0–2 visible for initial tests | basic hardware renderer, shadows off | minimal visual upgrade viability |
| P2 hybrid | 1280×720 | 8 candidate voxel actors, optional static glTF | 2–8 in controlled sweep | measured effects only | candidate balanced profile, NOT guarantee |
| P3 experimental | 1280×720 then optional 1080p | more model/animation loads | 8–16 stress sweep | selective shadows/PBR/postFX | diagnostics, never default from docs alone |

The light/model counts above are **experimental starting counts**, not a policy for a shipped engine. Profiles should be adapted after measured resource budgets. Validate actual OpenGL/Vulkan availability on the machine and capture the backend in logs.

## Measurement discipline

- Fixed camera or deterministic path; identical map geometry and actor states.
- Three runs per profile/backend (plus warmup), consistent capture duration, randomized test order if thermals skew sequential runs.
- Report mean FPS, 1% low, p50/p95/p99 frame-time, thermal and memory peaks, crash count, cold/warm startup and render artifacts.
- Record any VSync, FPS cap, texture filtering, antialiasing, external driver override or battery/AC change.
- Percentiles derive from individual frame times and must be based on an actual timestamp trace, not estimated from FPS screenshots.
- Do not use published benchmarks from a different GPU/laptop to claim UHD 620 results.

## Selection gate

Any chosen candidate must pass Tier-A gameplay and the operator-agreed P0 baseline; enhanced profiles are optional capabilities. Performance is not a proxy for ZScript script correctness or legal redistributability. Separate build and runtime authorization required.

Plan of record: `blueprints/research/HARDWARE-BENCHMARK-PLAN.md`.
