# WO-000D — UHD 620 device capture and performance confounders

| Control variable | Required recorded value | What can go wrong |
|---|---|---|
| UHD 620 driver | exact version/date/provider, renderer API actually used | silent software fallback or missing backend |
| Windows power policy | balanced/best performance setting, AC adapter wattage | frequency throttling or battery budget limits |
| CPU clocks / thermal | time-series or before/after if available | late-run degradation mistaken for shader cost |
| RAM | total 16 GiB report, channel/speed where discoverable | integrated GPU competes for memory bandwidth |
| GPU shared memory | reported reservation and runtime allocation if measurable | misleading 128 MiB dedicated figure |
| OS build | complete Windows build and update state | scheduler/driver differences |
| Visual presentation | resolution, render scale, display refresh/VSync/FOV | invalid FPS comparisons |
| Overlays/background | capture agent overhead, Windows graphics settings | GPU/CPU contention |
| Shader cache | cold/hot and hash of relevant settings | first-run stutter mistaken for steady-state |
| Scene state | map ID, camera coordinates, seed, visible lights/actors | mismatched draw calls |

## Proposed profiling classes

**CPU limited:** low GPU utilization with scene updates pegging CPU; **GPU limited:** high GPU utilization and poor frame time; **memory/thermal limited:** gradually degrading P99 or spikes correlated to power/clock changes. These are diagnostic **hypotheses**; do not assert causes without logs.

A driver configuration, thermal profile or BIOS change creates a new environment sample. Capture under a different hardware ID; never pool those runs with existing captures without an explicit comparison note.
