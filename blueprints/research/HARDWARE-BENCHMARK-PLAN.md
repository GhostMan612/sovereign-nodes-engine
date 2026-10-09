# Intel UHD 620 comparison plan — WO-000C v0.5.0

**Status:** PLANNED / NO DEVICE BENCHMARKS. Operator-reported target Dell Latitude 5400, i5-8365U, 16 GB RAM, Intel UHD 620, Windows 11 Pro. No inference from nominal GPU specifications substitutes for measured data.

## Environment capture (mandatory)

Record Windows build, graphics-driver version, CPU/GPU clocks if observable, memory configuration, AC/battery power, Windows power mode, temperature/throttling observations, renderer actually selected, engine revision/binary/hash, compiled feature flags, IWAD provenance, PK3 hash, map ID, difficulty, exact graphics settings. Use same environment across engine lanes wherever feasible.

## Controlled run plan (not performed)

1. Owner approves and prepares **synthetic-only** lawful scene and fixed camera or deterministic route. No private genealogy exports.
2. Use same 1280×720 output, VSync state, display mode, FOV, dynamic resolution state, capped/uncapped frame setting, content version and seeded gameplay.
3. Warm shaders once, then capture a minimum of **three** timed runs per case with duration and order noted; record cold-load/shader stutter separately.
4. Compare profiles P0 Legacy, P1 Hybrid-Lite, P2 Hybrid, P3 Experimental in order without changing another variable; use fixed actor and light counts.
5. Capture frametime trace, average FPS, 1% low FPS, p50/p95/p99 frame time, peak RAM, startup/transition time and crashes. Record CPU/GPU utilization and temperatures where available.
6. Repeat the light sweep L0=0, L1=2, L2=8, L3=16 visible lights while holding view/actors constant. Counts are probes, **not** predetermined shipping caps.
7. Run 1920×1080 only if 720p baseline is stable and decision-relevant. Re-run after any engine-source or GPU-driver change.
8. Analyze 95th/99th percentile and observed scene artifacts, not just FPS mean. Raw logs remain outside committed repo if they contain machine-specific paths or sensitive data; curated metrics are okay.

## Proposed human-review thresholds, not achieved results

- Performance is a gate only once a concrete **minimum acceptable profile** is agreed by operator. Prior Phase 00 proposed 30 FPS minimum and 60 FPS preference; keep as **provisional design targets**, not measured acceptance.
- Hard stops: reproducible crash, stall, corrupted save, absent/custom map fallback, missing actor, unsafe resource load.
- If renderer/backends differ across candidates, document fairness limits; do not compare incompatible frame capture pipelines as identical.

## Measurement worksheet (leave empty until operator tests)

| Engine SHA | Binary hash | GPU driver | Map/scene | Profile | Backend | Resolution | FPS mean | 1% low | p95 ms | p99 ms | RAM peak | 3-run spread | Result |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| NOT RUN | — | — | — | — | — | — | — | — | — | — | — | — | PENDING |

Supporting specs: `blueprints/research/SNE-000C-PERFORMANCE-PROFILES.md` and `SNE-000C-LIGHTING-BUDGET.md`. No builds or tests are authorized by this document.
