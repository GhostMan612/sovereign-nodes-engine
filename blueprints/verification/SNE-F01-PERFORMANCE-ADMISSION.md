# F-01 — `AUTH-P` GPU measurement admission and stop contract

**STATUS: PLANNED / NOT APPROVED / NO FPS DATA.** The reference UHD 620 performance is unknown until physical device trials.

## Prerequisites

1. Actual source/build/executable, lawful external IWAD and unchanged PK3 identities recorded.
2. Target candidate has independently reviewed actual C-001…C-008 gameplay proof with custom GapNode; no fallback Entryway.
3. Actual Windows GPU driver/backend, power, cooling, resolution, refresh, VSync/FPS cap, graphics flags and data capture tool validated.
4. Operator preregisters p95/p99/1%-low limits and proposed P0 floor (30 FPS provisional, 60 preferred; neither measured nor approved threshold by default).
5. Operator separately signs exact `AUTH-P` test scene, maximum trial duration, caps, number of repetitions and stop conditions.

## Method boundaries

WO-D protocol calls for >=3 raw frame-time runs per candidate × scene × profile with warm-up and comparable work. Collect per-frame timestamps/durations and SHA-256 raw traces *off-repo*, compute p50/p95/p99/1%-low with recorded estimator, verify active dynamic-light/model parity and thermal drift. Unverified GPU backend, scene fidelity, display caps, frame interpolation or missing trace → `INCONCLUSIVE`, not a marketing-style FPS claim.

## Abort and downgrade

Stop on thermal emergency, freezes/crashes, driver failures, display mode changes, mismatch between scene content, missing licensed assets, power mode or safety/authorization expiry. Any optional P1/P2/P3 feature drop returns to the last valid proven P0/P1 profile, not a blanket engine pass. Performance approval cannot authorize new engine features, upgrades or OS modifications.
