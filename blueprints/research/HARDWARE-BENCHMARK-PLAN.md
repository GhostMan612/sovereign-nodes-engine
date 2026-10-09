# SNE-P00 — Intel UHD 620 benchmarking protocol v0.6.0

**Status: PLAN ONLY / NOT RUN.** Target device reported: Dell Latitude 5400, i5-8365U, 16 GiB RAM, Intel UHD 620, Windows 11 Pro. Unknowns: exact driver, memory arrangement, BIOS, cooling, power state, supported renderer and observed FPS.

## Measurement definition

Capture **frame timestamps or per-frame durations** in milliseconds, not screenshots of an FPS overlay alone. Report mean FPS as `1000 / mean(frame_time_ms)` when frame capture represents rendered frames; report 1% low FPS using the 99th percentile of *per-frame durations* (document estimator and FPS-equivalent convention). Record p50/p95/p99 frame-time percentiles, full trace length, stutter counts and the duration of the test. Percentile method must be the same for all engines.

Do **not** compute mean FPS from `mean(1000 / each_frame_ms)` without stating the weighting difference. Present median frame-time and 1% low alongside averages because shader compilation stalls distort user experience. Explicitly distinguish cold startup/loading from steady-state gameplay and frame interpolation.

## Comparable test ordering

1. Operator separately authorizes device tests; choose lawful IWAD and synthetic-only Sovereign Nodes game fixture; record hashes and immutable engine source pins.
2. Inventory driver/BIOS/OS/MSVC, Windows power mode (AC power; stable cooling), RAM usage/background tasks, GPU API/backend, resolution, display refresh, VSync, frame cap, renderer, FOV and graphics settings; hold constant where supported.
3. Test **P0** custom-game correctness before FPS scoring: GapNode MAP01 and complete C-001…C-008. Falling back to DOOM2 Entryway is a FAIL even with excellent FPS.
4. Establish fixed camera or deterministic route with stable actor states, warm-up and capture windows; retain raw frame times off-repo and a redacted CSV/JSON summary.
5. Minimum 3 measured repetitions for each candidate × scene × profile, following one warm-up. Use comparable 60-second steady-state windows *if operator accepts that duration*; otherwise record adopted duration. Randomize or rotate test order to account for throttling.
6. At 1280×720 measure P0 LEGACY, P1 HYBRID-LITE, P2 HYBRID, P3 EXPERIMENTAL only as separately supported. Run light sweep L0=0, L1=2, L2=8, L3=16 in one fixed scene; values are *test counts*, not shipping budgets.
7. Additional conditions: warm/cold loading and save/load transitions, observed stability, shader compilation, GPU/CPU load and peak process RAM; record thermal/power changes and battery vs AC. Optional 1920×1080 only after a usable 720p baseline.
8. Compare only like-for-like game PK3 hash, content, route, resolution and backend **or declare the difference**. Never let BiasedDoom's richer defaults silently bias a comparison.

## Quantitative quality checks before analysis

- Each measured run has timestamps, duration, number of valid frames, valid data fraction, driver, source/build hash and SHA-256 of raw trace.
- Reject empty, zero/negative/nonfinite frame times, unknown frame cap, missing renderer identity, mixed resolutions, mislabeled map identities and start/stop pauses in the measured window.
- Publish per-case median across at least three runs with range and worst-run p99; report variance and software/driver limitations.
- Stability is independent of FPS: any hard crash, repeated hangs, corrupt save, script error or missing custom map blocks candidate acceptance.

## Proposed targets, **not results**

Operator to approve before testing: 30 FPS minimum (provisional), 60 FPS preferred, p95/p99 and 1%-low values review-required; no fictional hard frame-time SLA. On UHD 620 P0 must be viable before dynamic lights/voxels/glTF are enabled by default. Feature downgrade P3→P2→P1→P0 must be supported and documented. No sampled number is available in this package.

## Output contract

Capture one `templates/SNE-000D-HARDWARE-RECORD.json` per device configuration, one build record per binary and one `SNE-000D-RUN-RECORD.json` per trial; aggregate in `SNE-000D-RESULT-REVIEW.md` during a **future authorized execution**. Link to `SNE-000D-MEASUREMENT-SOP.md`, `SNE-000D-TEST-SCENES.md` and `SNE-000D-PERFORMANCE-DECISION-GATES.md`.
