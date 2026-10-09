# SNE-WO-000B/000D — Pinned compiler and Windows build matrix

**Review class:** observed exact CMake declarations; no Windows toolchain availability, configuration, compilation or execution has been validated.

| Property | GZDoom | UZDoom | BiasedDoom |
|---|---|---|---|
| Pin | `c26ce2e6ca` | `dbedcc894f` | `6147e06704` |
| `cmake_minimum_required` | 3.16 | 3.16 | 3.16 |
| Declared C++ | 17 | 20 | 17 |
| `project` | GZDoom | UZDoom | BiasedDoom |
| Windows runtime policy | `/MT` / debug `/MTd` via `CMAKE_MSVC_RUNTIME_LIBRARY` when policy effective | same MSVC runtime setting | same MSVC runtime setting |
| Root CMake options | `LIBVPX_VCPKG`, `OPENAL_SOFT_VCPKG`, Windows static vcpkg default | `FORCE_NO_LTO`, `USE_UPDATER` (Win default OFF), `LOAD_CURL_AT_RUNTIME` when updater | `BIASEDDOOM_ENABLE_GLTF`, `BIASEDDOOM_BUILD_GLTF`, `BIASEDDOOM_ENABLE_PYTHON`, `BIASEDDOOM_REQUIRE_PYTHON` |
| Python build behavior | not established in root excerpt | `find_package(Python3 3.6 REQUIRED)`: tool dependency, **not embedded game scripting** | optional embedded CPython, requested ON; availability/configuration unverified |
| native glTF | not confirmed in inspected root | not confirmed in inspected root | `find_package(fastgltf CONFIG REQUIRED)` if GLTF enabled |
| LTO | no dedicated root determination | Release/RelWithDebInfo IPO when supported; `FORCE_NO_LTO=ON` disables | not audited |
| Updater/build side effect | default-specific artifacts need audit | `USE_UPDATER` default OFF on Windows; non-MSVC updater path errors if enabled | bundled build helper might install deps; prohibited until approved |
| Windows compile status | NOT RUN | NOT RUN | NOT RUN |
| UHD 620 behavior | NOT RUN | NOT RUN | NOT RUN |

**Critical nuance:** UZDoom source CMake says “updater.exe currently only builds with msvc” **inside `USE_UPDATER` path**, not that the entire engine necessarily requires MSVC. No claim that a particular compiler lane succeeds until tested. For BiasedDoom, opt-in embedded Python isn't a security sandbox; default future test plans should explicitly disable it unless a trusted-only test requires it.

Full path/line references: `evidence/sources/SNE-000D-PIN-LEDGER.md`; actual discovery plan: `SNE-000D-WINDOWS-ENV-INVENTORY.md`; commands are gated in `SNE-000D-REPRO-BUILD-COMMANDS.md`.
