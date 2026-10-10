# F-03 — Direct pinned CMake source observations and review questions

This table supports **source semantics only**. Every listed path is at the immutable SHA in `SNE-F03-SOURCE-PINS.md`.

| Candidate | File/line region | Exact source observation | Limit / verifier question |
|---|---|---|---|
| GZDoom | [CMakeLists 1–50](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt#L1-L50) | min CMake 3.16; C++17; conditional vcpkg/Windows flags | actual installed compiler and complete libs unknown |
| GZDoom | [vcpkg.json](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/vcpkg.json) | root manifest features | port baseline & installed state unknown |
| UZDoom | [CMakeLists 1–60](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt#L1-L60) | C++20, Python 3.6 required, FORCE_NO_LTO, Windows updater default OFF | only root declarations, no run |
| UZDoom | [CMakeLists 495–510](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt#L495-L510) | `BUILD_NONFREE` source option defaults ON | actual included resources, rights and possible OFF behavior unknown |
| UZDoom | [CONTRIBUTING 118–130](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md#L118-L130) | AI-assisted upstream code submissions prohibited | independent downstream licensing still requires review |
| BiasedDoom | [CMakeLists 1–100](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt#L1-L100) | Python default ON, glTF default ON, conditional fastgltf | option set to OFF still requires actual cache inspection |
| BiasedDoom | [CMakeLists 520–540](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt#L520-L540) | conditional CPython dev library discovery | binary/runtime process trust not demonstrated |
| BiasedDoom | [vcpkg.json](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json) | vcpkg feature list includes Python and fastgltf | no package installation/license verification |

Root-only `vcpkg.json` for UZDoom failed a direct pinned lookup. Full-tree inspection is still required to determine actual dependency resolution. Do not treat this authored file as independent review, an exhaustive dependency graph, or configure success.
