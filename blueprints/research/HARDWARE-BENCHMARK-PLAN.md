# Intel UHD 620 hardware and engine profiling plan

**Target machine (operator-reported):** Dell Latitude 5400, Intel Core i5-8365U, 16 GB RAM, Intel UHD 620, Windows 11 Pro. **Measurements:** NONE — target metadata is not an actual benchmark.

## Objective

Measure suitability of stock and experimental engines for Sovereign Nodes FPS without inventing FPS numbers. Comparable data is mandatory before choosing an upstream foundation or enabling expensive effects by default.

## Controlled runs

1. Confirm BIOS/OS/GPU driver version, available memory and power mode; record GPU shared-memory behavior.
2. Pin the engine binary (Git revision and build options) and Sovereign Nodes PK3 hash.
3. Use one map and a reproducible scripted movement route (or fixed camera capture), 1280×720 to start.
4. Warm run, repeated runs, identical window/fullscreen and VSync settings; record any shader compilation stutters separately.
5. Compare profiles sequentially: Legacy (low dynamic lights/no shadows), Hybrid (voxel models/selective dynamic lights), Experimental (shadows/postFX isolated).
6. Log average FPS, 1% low, frame-time p50/p95/p99, peak RAM, observations, crash count. FPS-only averages hide severe stalls.
7. Repeat 1920×1080 only if 720p gate is stable. Record API OpenGL/Vulkan and actual driver, don't assume Vulkan availability.
8. Audit thermals/throttling on extended run.

## Proposed acceptance targets — design constraints, not test results

- Baseline profile: minimum acceptable 30 FPS with stable navigation, preferred 60 FPS.
- Scene coverage: combat, lights in view, voxel-rich area, transition/load and repeated save/load.
- Critical: no hard hangs, invalid frames, repeated crashes or silent fallback to stock IWAD.
- Averages must be supplemented with 1% lows and frame-time percentiles.

## Blank capture table

| Engine revision | Backend | Scene/profile | Resolution | FPS avg | 1% low | p95 ms | p99 ms | Peak RAM | Outcome |
|---|---|---|---|---|---|---|---|---|---|
| NOT RUN | — | — | — | — | — | — | — | — | PENDING |

## Environment constraint

No measured claims from another PC count as target-machine results. Engines must load a custom Sovereign Nodes scene, not merely a vanilla Doom level.
