# SNE-SRC-BIASEDDOOM-003 — glTF and Python risk/feasibility review

- Repo: `EricsonWillians/BiasedDoom`
- Pin: `6147e0670458e48e63d1a40750f36dfc68b00f7f`
- Review class: SOURCE-OBSERVED and DOC-CLAIM; NO COMPILE/EXECUTION.

## Findings

- `src/common/models/model_gltf.cpp` includes fastgltf interfaces and model-processing helpers inside `#ifdef NEODOOM_GLTF_SUPPORT`; header defines `GLTFLoadOptions` memory-oriented limits. A defined source path is not proof the pinned executable was compiled with the feature.
- `CMakeLists.txt` exposes `BIASEDDOOM_ENABLE_GLTF` (ON by default) and optional `BIASEDDOOM_ENABLE_PYTHON`; fastgltf is a required configured package when glTF enabled. Need verify compilation and runtime registration per target.
- Project `docs/gltf/README.md` explicitly recommends external textured `.gltf + .bin + textures`, noting `.glb` embedded texture surprises. Treat as maintainers' guidance not a rigorous pass/fail result.
- `docs/scripting/python.md` says embedded Python is unsandboxed native-equivalent code; loader is opt-in, and opt-in is process-wide rather than per-PK3. Untrusted Python mod execution is prohibited in SNE plan without new security design.
- `docs/engine/procedural-map-generation.md` claims a separate generated-procedural-map path; it does not establish persistent simultaneous geometry or multi-map streaming.
- README discusses future ZScript deprecation; roadmap intent does **not** establish removal from the inspected source. Tier-A ZScript proof remains required.

## Immutable links

- [gltf cpp](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.cpp)
- [gltf options](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/src/common/models/model_gltf.h)
- [CMake flags](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt)
- [asset workflow](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/gltf/README.md)
- [Python security](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/scripting/python.md)
- [procedural maps](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/engine/procedural-map-generation.md)
- [README](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/README.md)

## Test separation

First prove unchanged Sovereign Nodes FPS Tier-A. Only then introduce synthetic fixture model load tests separately for `.gltf` geometry, `.glb` geometry, external textures, embedded texture, skeletal animation and errors. No model feature score without on-device proof.
