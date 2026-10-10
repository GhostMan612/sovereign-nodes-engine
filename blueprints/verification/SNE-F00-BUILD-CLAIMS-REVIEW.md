# F-00 — Root CMake source facts vs unexecuted Windows feasibility

| Candidate | Exact pinned root facts | Reviewer must discriminate | Execution outcome |
|---|---|---|---|
| GZDoom `c26ce2e6c` | CMake >=3.16; C++17; Windows static vcpkg triplet conditional under root `CMakeLists.txt` | real vcpkg/SDL/ZMusic/library closure and build flags | **NOT RUN** |
| UZDoom `dbedcc894` | CMake >=3.16; C++20; `FORCE_NO_LTO`; `USE_UPDATER` OFF default on Windows; required `find_package(Python3 3.6)` | build-Python vs runtime-Python distinction; optional updater MSVC branch; installed SDK/compiler | **NOT RUN** |
| BiasedDoom `6147e0670` | CMake >=3.16; C++17; `BIASEDDOOM_ENABLE_PYTHON` initially ON; `BIASEDDOOM_ENABLE_GLTF` ON default; fastgltf CONFIG required if glTF enabled | option interaction, vcpkg manifest features, embedded Python trust and `.gltf`/`.glb` runtime behavior | **NOT RUN** |

Sources: [c26ce2e6c CMake](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt), [dbedcc894 CMake](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt), [6147e0670 CMake](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt). Each is an immutable historical **source file**, not a promise about locally installed versions, successful compilation or performance.

## Negative review probes

1. Confirm root option defaults from exact commit, not another upstream release.
2. Look for target-specific CMake and transitive subprojects that override options; report source-coverage limitations.
3. Mark optional scripting and model features separately: a CMake declaration is not confirmation they were compiled or exercised.
4. Verify Windows generator/config flags vs Ninja single-config differences in WO-D, and note missing compiler/SDK versions.
5. Preserve GZDoom-first as a **verification order** only; UZDoom/BiasedDoom remain unscored.

**No native builds or local environment inventory may be performed under F-00 read-only review.**
