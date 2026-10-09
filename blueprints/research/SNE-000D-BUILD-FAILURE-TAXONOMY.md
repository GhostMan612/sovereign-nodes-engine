# WO-000D — Build and startup failure taxonomy

| ID | Observable symptom | Immediate discriminator | Evidence to capture | Next decision |
|---|---|---|---|---|
| BF-01 | CMake generator unavailable | missing VS/Ninja/architecture | configure command, stderr, installed-tool inventory | toolchain prerequisite not satisfied |
| BF-02 | Compiler rejects C++20 | UZDoom requirement vs old toolset | compiler/version and feature error | choose qualified compiler or block UZ lane |
| BF-03 | Missing Python3 in UZDoom configure | `find_package(Python3 3.6 REQUIRED)` | error, Python paths/version | inventory; do not add Python scripting claims |
| BF-04 | vcpkg triplet or CRT mismatch | static `/MT` vs resolved dependency | triplet, CMakeCache, linker diagnostics | resolve isolated lane only if approved |
| BF-05 | fastgltf package not found | BiasedDoom GLTF option active | CMake config, vcpkg feature state | explicitly compare GLTF-off lane or restore deps |
| BF-06 | Updater / CURL failure | UZDoom `USE_UPDATER` enabled | option value, CMake output | disable for baseline, never blanket blame UZDoom |
| BF-07 | Compile/link fails in bundled lib | mismatch in SDK or compiler flags | first failing translation unit, full command and dependency revision | upstream compatibility review |
| BF-08 | Engine starts but stock map loads | custom MAP01 or PK3 missing/mispackaged | unique MAP01 marker and log | C-001 FAIL, no benchmark |
| BF-09 | Script/GLDEFS sprite missing | parse/actor-binding difference | parser diagnostic and rendered actor behavior | C-002/C-004/C-005 FAIL |
| BF-10 | Driver/backend fails | unsupported API or shader issue | driver and GPU API, backend selection log | fallback to verified basic backend, no invented Vulkan support |
| BF-11 | FPS differs drastically | power/throttling, VSync, scene drift | traces, per-run P99, environment record | rerun controlled or mark NOT COMPARABLE |
| BF-12 | Content rights/notice gap | unknown bundled license or proprietary IWAD | component/asset provenance | redistribution blocked |

## No hidden repair policy

Future agents must **not** automatically install packages, delete caches, disable Defender, patch game scripts, downgrade SDKs, weaken policies, clone replacement repos, change BIOS, or modify the original game to “make green.” Escalate with failure evidence and a separately reviewable, minimal change proposal.
