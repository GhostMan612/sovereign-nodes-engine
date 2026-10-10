# WO-E — Build and hardware verification blockers

| Blocker | GZDoom | UZDoom | BiasedDoom |
|---|---|---|---|
| CMake root declares | ≥3.16, C++17 | ≥3.16, C++20 | ≥3.16, C++17 |
| Host tool presence | unknown actual Windows SDK/MSVC/CMake | unknown actual MSVC C++20 support, Python3 utility | unknown MSVC + fastgltf/CPython development deps |
| Build flags | vcpkg Windows static branch | LTO optional, updater OFF default; Python3 build tooling | GLTF conditional via fastgltf; optional embedded Python |
| Compiled artifact | NONE | NONE | NONE |
| Source game parity | NOT RUN | NOT RUN | NOT RUN |
| Actual GPU graphics | NOT RUN | NOT RUN | NOT RUN |

## Test integrity rules

- A build command proposed in WO-D is not a completed compile. Preserve exact executable/resource hash and source commit for every future run.
- Never share one build cache across candidates or MSVC/Ninja configurations; verify actual Release or RelWithDebInfo not Debug.
- Compare scene outputs before comparing FPS; incorrect/missing actors/lights create invalid apparently faster runs.
- For UHD 620 measure baseline 1280×720 P0 first; at least three warm traces with cold start separate, frame-time p50/p95/p99 and 1% lows, VSync/driver/power/thermals documented.
- Do not infer OpenGL/Vulkan availability, GPU shared-memory amount or target FPS from vendor specs; actual driver and engine backend proof required.
- No installs, engine builds or game launches in this authoring work order.

Detailed future run templates stay in WO-D and are only operator-run under separate approval.
