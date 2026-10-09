# SNE-SRC-BIASEDDOOM-004 — BiasedDoom Windows compilation probe

**Repo:** `EricsonWillians/BiasedDoom` at `6147e0670458e48e63d1a40750f36dfc68b00f7f`; **status:** SOURCE-OBSERVED / NEVER BUILT.

- [Root CMake](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt) lines 1–95: CMake 3.16, C++17, opt-in embedded Python build request ON unless configured otherwise, separate required-Python flag, glTF and build-glTF options ON; `fastgltf CONFIG REQUIRED` if glTF enabled.
- [vcpkg manifest](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json) `gltf-support`/fastgltf, `vcpkg-python` and observed 3.12.13 Python override; transitive libraries and actual toolchain remain unknown.
- [README](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/README.md) documents VS2022 Windows build directions, a **project-authored assertion**, not a verified build on the operator device.
- [Python security docs](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/scripting/python.md) explicitly call embedded Python unsandboxed and powerful; keep trusted-only, default baseline OFF.

**Test partition:** (1) C++17 gameplay compatibility with Python OFF and glTF OFF; (2) separate glTF ON / Python OFF build with fastgltf; (3) no scripting-Python lane without a dedicated security authorization. The asset `.gltf` with external textures and `.glb` embedded-texture behavior must be measured separately.

**Unknowns:** actual compiled macro propagation/registration, MSVC flags, resource and dependency identities, UHD 620 draw cost, sustained upstream ZScript policy. No asset or licensing review completed.
