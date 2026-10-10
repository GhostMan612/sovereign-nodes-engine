# WO-F — UHD 620 graphics and frame-time trials

**Status: PROTOCOL ONLY / NOT RUN.** Existing WO-D benchmark SOP governs raw frame-time math. Use only an operator-approved threshold (provisional 30 FPS min / 60 FPS preferred is not a measured outcome or final SLA).

## Test matrix and gates

| Trial | Scene and variation | Required repetitions | Admission condition |
|---|---|---|---|
| GPU-00 | P0 original sprite, static-light baseline custom GapNode at 1280×720 | warm-up + >=3 trace runs | C-001…C-008 PASS on unchanged PK3 |
| GPU-01 | P1 selective KVX (actor behavior unchanged) | >=3 comparable traces | GPU-00 stable |
| GPU-02 | 0/2/8/16 visible GLDEFS lights fixed view; shadows controlled | >=3 each | validated light attachments |
| GPU-03 | P2 mixed voxels/model effect if candidate actually supports it | >=3 | feature confirmed by model test |
| GPU-04 | BiasedDoom glTF external textures, then GLB separately | >=3 | separately compiled feature flag and lawful asset |
| GPU-05 | P3 shadows/PBR/postFX on/off, 1080p only if 720p usable | >=3 | explicit owner opt-in |
| GPU-06 | save, level transition and 10+ min thermal stability | dedicated trace window + notes | correctness first |

## Fairness and instrumentation

- Identical game PK3, map, camera path/seed, actor/light counts, resolution/FOV, renderer/API or explicit API difference, VSync, refresh/cap, capture duration, driver/power/thermals.
- Record raw frame intervals (ms), sample count and SHA-256; mean FPS derived from mean frame duration, a declared 1%-low estimator, p50/p95/p99, long-frame count and per-run spread. A screenshot of FPS text alone is invalid.
- Log shader cold-start separately from warmed steady state; rotate candidate order to reduce thermal bias; never hide silent asset omissions, Vulkan fallback or simplified scene geometry.
- Candidate reaches only the profile actually supported and **measured**. A fast but wrong or missing custom map cannot be compared.

## Missing decisions

Absolute p95/p99 and 1%-low ceilings, exact run duration and acceptable thermal throttling require operator approval *before* tests. If thresholds are chosen after viewing data, flag exploratory and do not call them pre-registered pass/fail gates.
