# F-03 — BiasedDoom experimental build lane (future, lower priority)

**Pinned source:** `EricsonWillians/BiasedDoom@6147e0670458e48e63d1a40750f36dfc68b00f7f`; root CMake Git blob `ac506cbca31c2702af87011e1b7fd83e1839813c`; manifest blob `f298e19602268bb5abb8e8e72c8a0f7d84e48ca4`.

## Actual source options (not successful builds)

- Minimum CMake 3.16 and C++17; `BIASEDDOOM_ENABLE_PYTHON` root default ON; `BIASEDDOOM_ENABLE_GLTF` and `BIASEDDOOM_BUILD_GLTF` defaults ON.
- Root may `find_package(fastgltf CONFIG REQUIRED)` when glTF enabled, so **GLTF must be explicitly OFF** for a deliberately minimal baseline; avoid accidentally triggering vcpkg feature resolution.
- Embedded Python uses CPython native process privileges and is not a mod sandbox. Baseline explicitly requests Python OFF, and runtime permission for arbitrary Python is *not* granted.
- A separate glTF ON build requires fastgltf pin/license, declared model feature flags, separate tree and resource provenance; experimental success is not game parity.

## Required ordering

1. Only after control host/toolchain+dependency admission, separate `AUTH-B` names BiasedDoom (not inherited).
2. Baseline flags proposed `BIASEDDOOM_ENABLE_PYTHON=OFF`, `BIASEDDOOM_ENABLE_GLTF=OFF`, `BIASEDDOOM_BUILD_GLTF=OFF`, with actual option support proven from chosen source tree.
3. Record native x64 configure/build identity, core resources, static/dynamic DLLs and two trials.
4. Optional future `GLTF=ON` is another explicitly approved config and dependency budget. `AUTH-T/P` still required for actual model/fidelity/FPS tests.

**STATE: NOT RUN; NO embedded Python or glTF capability proved in an executable.**
