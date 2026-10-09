# SRC-BIASEDDOOM-001 — BiasedDoom experimental lane

**Pin:** `6147e0670458e48e63d1a40750f36dfc68b00f7f`
**Status:** SELECTED FILES VERIFIED / FEATURE CLAIMS NOT RUNTIME-VALIDATED.

- [`README.md`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/README.md) — Documents glTF, skeletal animation, PBR-oriented materials, lighting, Python and ongoing ZScript support as claimed upstream features.
- [`src/common/models/model_gltf.cpp`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp) — Compiled behind NEODOOM_GLTF_SUPPORT and includes fastgltf parser/types; actual model loader source exists.
- [`src/common/models/model_gltf.h`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.h) — GLTFLoadOptions limits for vertices/triangles/textures, mesh/skin/material/animation structures.
- [`CMakeLists.txt`](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt) — CMake 3.16; conditional glTF and Python build options; vcpkg feature gating.

## Suitability

BiasedDoom is strongest as reference/prototype for a glTF and animated-model path. `NEODOOM_GLTF_SUPPORT` confirms actual feature gating in source; the engine being able to compile without it means *the feature must be explicitly verified in any test build*. In README the developer encourages AI-assisted development subject to review, unlike UZDoom's upstream contribution policy.

## Major risks

- Python mods are arbitrary trusted code; opt-in controls are not sandboxing. No untrusted mod execution or Mantle data access.
- The published roadmap suggests eventual ZScript deprecation, **not current removal**. Never migrate working gameplay based on roadmap statements alone.
- Shader cost and FPS on UHD 620 unknown; no native glTF acceptance result recorded.
- Code-level license headers may differ from the repository's top-level GPL license. Example `model_gltf.cpp` uses LGPL language; preserve headers, inspect provenance and full package license dependencies before code transplantation.
