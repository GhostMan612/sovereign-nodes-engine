# SNE-WO-000B — Future compatibility, renderer and threat-model gates

**All runtime results: NOT RUN.** These cases are specifications, not reported accomplishments.

| Test ID | Case | Observable pass criterion |
|---|---|---|
| T-A01 | Correct custom MAP01 on GZDoom | GapNode unique marker, not IWAD Entryway; no missing assets |
| T-A02 | MAPINFO grammar and fragments | all three ZScript fragments load, custom HUD/actors instantiate |
| T-A03 | Three-map chain | MAP01 → MAP02 → MAP03 with correct names and mission/inventory state |
| T-A04 | GLDEFS | ELECA0, ORESHAA0 and TOOLAA0 emit intended actor-bound light; compare renderers |
| T-A05 | DoomEdNums/sprites | all custom thing IDs resolve, no invisible altar or missing frames |
| T-A06 | Synthetic handoff | schema 1, seed, runId, name displayed correctly in HUD; missing/corrupt file safe |
| T-A07 | Handoff boolean parse | hasParadox JSON true/false maps to expected on-screen state; **source concern** about `ScanInt` must be tested |
| T-A08 | ZDaemon separate lane | establish what is actually supported without assuming modern ZScript/light parity |
| T-R01 | VOXELDEF prop | same collision/health/damage as original sprite actor, visible model |
| T-R02 | Dynamic lights | 0/2/8/16 actor lights each at fixed view; frame-time and visible binding captured |
| T-R03 | glTF format | external-texture `.gltf` geometry/animation passes; `.glb` embedded textures separately evaluated |
| T-R04 | Loading robustness | malformed KVX/VOX/glTF rejected safely, finite allocation and deterministic warning |
| T-W01 | Logical map continuity | hub/next map state persists correctly, no synchronous multiple-map assumption |
| T-S01 | Mantle data separation | only fake fixture accepted; no direct private ledger or network access |
| T-S02 | Python trust | disabled by default unless explicitly authorized; untrusted script must not run as game code |

## Required test metadata

Engine and game commit SHA, build type, Windows edition, GPU driver, full command and IWAD provenance (never copied into repo), screen resolution, renderer, graphics preset, FPS average, 1% lows, median/95th/99th frame time, reproducible demo path or step list, logs/screenshots and tester sign-off.

## Stop conditions

Any ZScript compilation error, IWAD fallback, missing handoff, invalid license dependency, FPS below agreed threshold, or misleading PASS blocks the decision. **No local execution commands are authorized by this documentation.**
