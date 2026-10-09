# SNE-WO-000B — Build/toolchain feasibility matrix

**Evidence:** exact CMake and package manifests at pinned revisions. **No compiler is installed, reconfigured, run or validated by this research package.** The user's existing Windows/WSL environment is not proof the engine toolchain is complete.

| Item | GZDoom | UZDoom | BiasedDoom |
|---|---|---|---|
| Root CMake min | 3.16 | 3.16 | 3.16 |
| Declared C++ language standard | **C++17** | **C++20** | **C++17** |
| Build target | `project(GZDoom)` | `project(UZDoom)` | `project(BiasedDoom)` |
| Windows static runtime/vcpkg | `x64-windows-static` under relevant CMake branch | inspect platform and dependencies in full tree | supports static vcpkg triplet plus feature selection |
| Python build dependency | not established from inspected root excerpt | `find_package(Python3 3.6 REQUIRED)`; build tool, **not gameplay embedded interpreter proof** | optional embedded CPython build; ON request, not guaranteed present |
| glTF dependency | not confirmed native | not confirmed native | optional `fastgltf CONFIG REQUIRED` if glTF enabled |
| LTO | unconfirmed from excerpt | release/relwithdebinfo LTO option shown | not audited |
| Windows build | **NOT RUN** | **NOT RUN** | **NOT RUN** |
| Intel UHD 620 runtime | **NOT RUN** | **NOT RUN** | **NOT RUN** |

## Source-backed details

- GZDoom: [CMakeLists.txt](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt) and [vcpkg.json](https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/vcpkg.json).
- UZDoom: [CMakeLists.txt](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt). Do **not** assume the `find_package(Python3)` line turns Python into a game scripting runtime.
- BiasedDoom: [CMakeLists.txt](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt) and [vcpkg.json](https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json). vcpkg feature `gltf-support` requests fastgltf; `vcpkg-python` includes CPython 3.12.13 override in inspected manifest, but actual selected environment is unverified.

## Proposed future operator-controlled build investigation

For each candidate, first record host Windows edition, Visual Studio/Build Tools edition, MSVC/toolchain version, CMake and Ninja versions, vcpkg checkout/toolchain, Git SHA, target architecture, relevant installed dependencies, and clean-room compilation command. Capture failures and build times. No automatic installs/changes to the user's global toolchains. Only undertake execution after separately approved Phase 01.

## Risk notes

The Latitude 5400's Intel UHD 620 is the graphics bottleneck; compiled success does not imply rendering speed. Device driver OpenGL/Vulkan support must be measured rather than assumed. Keep OpenGL baseline and Vulkan optional. Never compare candidates at different scene complexity, resolution or asset set.
