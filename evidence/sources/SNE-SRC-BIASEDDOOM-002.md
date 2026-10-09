# SRC-BD-002 — BiasedDoom glTF/Python/renderer research

**Pin:** `6147e0670458e48e63d1a40750f36dfc68b00f7f`
**Class:** Pinned-source inspection and published documentation. **No build or performance test.**

| Concern | Pin-backed evidence | Interpretation |
|---|---|---|
| Build | [CMakeLists.txt](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt) | CMake >=3.16, C++17. `BIASEDDOOM_ENABLE_GLTF` and `BIASEDDOOM_BUILD_GLTF` default ON in inspected CMake file; flags require validation at compile |
| glTF dependency | [CMakeLists.txt](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt), [vcpkg.json](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json) | `find_package(fastgltf CONFIG REQUIRED)` when enabled; feature adds fastgltf |
| glTF implementation | [model_gltf.h](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.h), [model_gltf.cpp](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp) | Header has GLTF error/result types, vertex+bone attributes, PBR material values and resource size limits; CPP parses using `fastgltf` under `NEODOOM_GLTF_SUPPORT` guard |
| glTF authoring | [docs/gltf/quick-start.md](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/gltf/quick-start.md) | Authoring docs show Doom actor replacement with ZScript; do not assume example scripts compile without proof |
| Texture caution | [docs/README.md](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/README.md) | Project recommends separate `.gltf + .bin + external textures`; docs describe embedded `.glb` image decoding as limited even though source includes an embedded-image path. This contradiction demands test cases |
| Python build flag | [CMakeLists.txt](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt) | `BIASEDDOOM_ENABLE_PYTHON` ON, `BIASEDDOOM_REQUIRE_PYTHON` OFF. Python may be omitted when development files unavailable; **ON flag is not runtime evidence** |
| Python dependency | [vcpkg.json](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json) | Feature `vcpkg-python`, override Python3 3.12.13; conditional native Windows/macOS, excludes MinGW path |
| Roadmap | [README.md](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/README.md) | Current ZScript/ACS support is claimed while future ZScript deprecation is announced. Future plan is not a currently proven break |

## High-risk investigation targets

1. Inspect macro definition from CMake through compilation and source registration; confirm model classes are linked into asset loader.
2. Build a synthetic `.gltf` with external textures and `.glb` with embedded textures; run same animation/skin tests on actual GPU.
3. Validate memory/mesh hard limits and malformed buffer input rejection; preserve copied LGPL code notices if borrowing.
4. For Python, identify actual opt-in execution path, filesystem scope, module availability, thread affinity, sandbox limitations and untrusted mod behavior. Disable by default until threat-model accepted.
5. Confirm light/shadow settings actually map to renderer backend on Intel UHD 620; separate marketing claims from GPU results.

## Recommendation

Treat BiasedDoom as an experimentally useful reference and optional benchmark target, not the assumed production base. Port **ideas, interfaces, test designs**, not code blobs, until exact license and integration costs are reviewed. The ZScript roadmap needs a maintainability plan if adopted.
