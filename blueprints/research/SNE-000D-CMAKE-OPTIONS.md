# WO-000D — CMake options and semantics reviewed at pinned source

| Option/setting | Candidate | Exact observed behavior | Validation before use |
|---|---|---|---|
| `CMAKE_CXX_STANDARD 17` | GZDoom | declared by root `CMakeLists.txt` | confirm actual compiler configure line and ABI |
| Windows `VCPKG_TARGET_TRIPLET x64-windows-static` | GZDoom | root forces default when platform conditions match and no override | inspect vcpkg installation/triplet and cached value |
| `LIBVPX_VCPKG` / `OPENAL_SOFT_VCPKG` | GZDoom | relevant manifest features under conditional options | capture ON/OFF and resulting link graph |
| `CMAKE_CXX_STANDARD 20` | UZDoom | declared root requirement | confirm MSVC toolset C++20 features |
| `find_package(Python3 3.6 REQUIRED)` | UZDoom | configure-time dependency used by build tooling | record Python executable/version; no Python modding inference |
| `FORCE_NO_LTO` | UZDoom | prevents optional IPO checks and release LTO | initial troubleshooting can select ON, performance comparison must record state |
| `USE_UPDATER` | UZDoom | Windows default OFF | keep OFF for baseline; if enabled, require MSVC and CURL review |
| `CMAKE_CXX_STANDARD 17` | BiasedDoom | root requirement | match observed MSVC/SDK |
| `BIASEDDOOM_ENABLE_GLTF` | BiasedDoom | ON by default; `find_package(fastgltf CONFIG REQUIRED)` if ON | record actual fastgltf version and compile definition |
| `BIASEDDOOM_BUILD_GLTF` | BiasedDoom | separate option ON by default; compiled path requires audit | confirm macro `NEODOOM_GLTF_SUPPORT` and registered model loader |
| `BIASEDDOOM_ENABLE_PYTHON` | BiasedDoom | default requested ON if development files found | explicitly OFF for first synthetic baseline unless trusted scripting approved |
| `BIASEDDOOM_REQUIRE_PYTHON` | BiasedDoom | OFF default; configure failure if runtime required but absent | prevent silently missing a required feature |

**No configuration was executed.** Do not accept cache value alone as evidence a feature was linked and behaves correctly. Capture flags, CMakeCache excerpts, compiler/linker inputs, binary hash, resource bundle hash and runtime proof.

Provenance: immutable root `CMakeLists.txt` links in `evidence/sources/SNE-000D-PIN-LEDGER.md`. Option stability must be rechecked after any revision change.
