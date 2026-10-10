# F-00 — Engine-source and upstream policy selected observations

**Selected pinned lines only; external independent reviewer pending.**

## GZDoom at `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`

- [`src/r_data/sprites.cpp` lines 297–333](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/src/r_data/sprites.cpp#L297-L333), Git blob `0a7be96a12003a4996b0ea1ca2b275eec6840785`, describes four-character family + frame letter + rotation and four-character name hashing.
- [`CMakeLists.txt` lines 1–50](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt#L1-L50), Git blob `8a1becdb8546036d117f63db0a18c5a45541a8ba`, declares minimum 3.16 and C++17; conditional static vcpkg Windows setting is visible.
- Do **not** interpret parser comments as a proven failure of original game sprites, or CMake text as working Windows binaries.

## UZDoom at `dbedcc894fb6866c48520cf27ae773f9957024b9`

- [`CMakeLists.txt` lines 1–55](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt#L1-L55), Git blob `39dcbefed262eab124f23da8efdb7b3ce331dcd9`, declares C++20, optional LTO option, Windows updater OFF by default and `find_package(Python3 3.6 REQUIRED)` (Python used for build tooling, not a proof of embedded gameplay CPython).
- [`CONTRIBUTING.md` code section](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md#L90-L137), Git blob `84621215c99b1da9af913d082e65e20b6d725175`, bars AI-generated/assisted contributions **to upstream code PRs**; art rules also cover AI-generated art. This policy is **not** a blanket prohibition implied by GPL licensing of properly compliant downstream forks. Separate rights/asset review still needed.
- Actual toolchains, successful compile, game parity and hardware behavior **NOT RUN**.

## BiasedDoom at `6147e0670458e48e63d1a40750f36dfc68b00f7f`

- [`CMakeLists.txt` lines 1–98](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt#L1-L98), Git blob `ac506cbca31c2702af87011e1b7fd83e1839813c`, declares C++17, `BIASEDDOOM_ENABLE_PYTHON` ON as an option (conditional build), and `BIASEDDOOM_ENABLE_GLTF`/`fastgltf CONFIG REQUIRED` when enabled.
- Compilation of glTF, `.glb` textures, real animation and CPython trust cannot be deduced from existence of options alone. Default source-level Python enabled request is **not** proof that interpreter is packaged, enabled at game launch, or sandboxed.

## Core follow-up

Independent reviewer challenges each citation/line and may correct the author. Legal approval requires transitive license and asset bill-of-materials review. Foundation preference remains **GZDoom-first testing order**, not adoption or weighted scoring.
