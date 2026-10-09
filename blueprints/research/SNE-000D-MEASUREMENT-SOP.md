# WO-000D — Operator-run frame-time capture SOP (future approval required)

## Controlled steps

1. Approve test session and scene fixtures, ensure target actually renders `GapNode` MAP01; a `DOOM2 Entryway` fallback voids every performance result.
2. Before each engine/profile, record engine exe hash and configuration + support resources, PK3 hash, lawful IWAD hash, OS/driver, display/FOV/backend, VSync/limits, AC/power/thermal conditions and start time.
3. Use a fixed camera or deterministic movement route. Prefer repeated pre-stabilized 60 s segments (duration must be agreed and unchanged) after warm-up. Start/stop markers exclude loading/alt-tab; capture loading separately.
4. Collect raw per-frame timestamps or durations by a measurement tool approved for this backend. Calibrate overhead with/without recording. Do not assume screenshot overlays are accurate enough to compute p95/p99.
5. At least three measured runs per engine×scene×profile, rotate run order and keep cooling consistent. If a measured run is missing, status remains INCOMPLETE; do not silently replace it with warm-up.
6. Store raw traces privately with SHA-256; sanitize any included absolute paths, usernames, real-person identifiers and secrets before curated reporting. Use JSON templates for summaries.
7. Analyze p50/p95/p99 frame times, average FPS and 1% low FPS with the same estimator and windowing across candidates. Report worst-run p99, sample count, confidence limitations and stutter spikes; separate thermal drift from GPU feature cost.
8. Validate visual/collision/light equivalence using paired screenshots, map/actor markers and logs. Only then compare the FPS. A high score from a missing model/light is invalid.

## Reject run when

Scene/map differs; compositor/frame cap unknown; only a single average FPS value exists; title never shows custom map; compiler `Debug` vs `Release` differs; raw trace is lost or contains invalid frame times; graphics backend is not verified; shader warm-up differs; crash/unresponsive state; unapproved IWAD or private Mantle data.

## Metric computation documentation

Frame times measured in milliseconds. For N positive samples `t_i`, compute `mean_t=Σt_i/N`, `mean_fps=1000/mean_t`, `p95(t)`, `p99(t)` and the method for 1% low (recommend `1000 / mean(slowest ceil(.01*N) frame times)` as a conservative slowest-1% mean; explicitly label not equivalent to the 99th-percentile reciprocal). State percentile interpolation method, outlier handling and dropped-frame handling. A reviewer cannot infer 1% low from a single p99 alone.

## Escalation

Any persistent regression or artifact generates a defect record and blocks candidate scoring. Performance is not a proxy for licensing, safety, WAD parity or game completeness.
