# WO-000D — Toolchain selection and Windows/WSL boundaries

## Default planning lane

Prefer one Windows-native x64 MSVC/Visual Studio toolset for apples-to-apples candidate experiments, subject to actual installed tooling and source compatibility. Visual Studio 2022 is a **planning candidate**, not a claim that it is installed. Use isolated engine checkout/build directories (paths chosen by operator) and stable generator/SDK/CRT settings.

## Why not assume WSL parity

WSL Ubuntu can compile Linux-target binaries with Linux drivers and toolchain flags, but cannot prove Windows-native OpenGL/Vulkan paths or Windows executable/distribution compatibility. If WSL is tested later, make a separate labeled lane and do not combine FPS figures with Windows-native test runs.

## CMake mode hazards

- Visual Studio generator is multi-config: `--config Release` chooses build configuration; setting `CMAKE_BUILD_TYPE` alone does not select it.
- Ninja single-config uses `CMAKE_BUILD_TYPE` at configure; `--config Release` is not a substitute.
- Keep source tree, build tree, cache, vcpkg triplet and target x64 ABI consistent; never recycle a cache after switching generator/compiler/architecture.
- Disable optional multi-project features for first build when supported (example UZDoom `USE_UPDATER=OFF`; BiasedDoom Python OFF). Do not remove a required feature merely to declare Tier-A parity.
- Record Windows SDK, `cl` build, CMake version and target machine architecture; build tools installed != configured environment activated.

## Acceptance strategy

Stage one user-authorized build per candidate; normalize runtime environment and game fixture; move to optional features only after stock custom-game parity; validate a second clean-room build before claiming binary repeatability. Exclude engine compilation from Phase 00 assistant execution.
