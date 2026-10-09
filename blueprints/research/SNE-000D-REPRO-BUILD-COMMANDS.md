# WO-000D — Operator-reviewed native Windows command templates (NOT EXECUTED)

**STOP:** These are future *proposed* steps for a separate authorized build/testing activity. They are not instructions for ChatGPT or agents to run during this Phase 00 overlay. Exact checkout, SDK, toolchain file, generator, dependencies and output paths must be approved by the operator. PowerShell syntax assumes native Windows x64 and installed Visual Studio generator; none are verified present.

## Future non-mutating inventory sketch

```powershell
# After owner approval to inventory, not to install:
cmake --version
ninja --version
git --version
python --version
# MSVC/SDK and driver versions need separate Windows-specific inspection.
```

## Candidate pinning and source discipline

Use an isolated, owner-selected source checkout **outside SNE planning repo**; explicitly inspect `git rev-parse HEAD`, `git status --short` and submodule state. This package never clones/downloads sources, and no unapproved `git pull`, submodule-remote update or patch is allowed. Source SHA values:

```text
GZDoom:   c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7
UZDoom:   dbedcc894fb6866c48520cf27ae773f9957024b9
BiasedDoom:6147e0670458e48e63d1a40750f36dfc68b00f7f
```

## Conceptual CMake configure/build commands

These **do not** constitute known-working build recipes. `<SOURCE>` and `<BUILD>` are placeholders to be replaced only after toolchain/distribution review. `-G` and `-A` must match installed tools. Use different build trees per lane.

### GZDoom / baseline

```powershell
cmake -S "<GZ_SOURCE>" -B "<GZ_BUILD>" -G "Visual Studio 17 2022" -A x64 -DLIBVPX_VCPKG=OFF -DOPENAL_SOFT_VCPKG=OFF
cmake --build "<GZ_BUILD>" --config Release
```

### UZDoom / minimal Windows startup

```powershell
cmake -S "<UZ_SOURCE>" -B "<UZ_BUILD>" -G "Visual Studio 17 2022" -A x64 -DFORCE_NO_LTO=ON -DUSE_UPDATER=OFF
cmake --build "<UZ_BUILD>" --config Release
```

### BiasedDoom / base gameplay parity without Python/glTF extras

```powershell
cmake -S "<BD_SOURCE>" -B "<BD_BASE_BUILD>" -G "Visual Studio 17 2022" -A x64 -DBIASEDDOOM_ENABLE_PYTHON=OFF -DBIASEDDOOM_ENABLE_GLTF=OFF -DBIASEDDOOM_BUILD_GLTF=OFF
cmake --build "<BD_BASE_BUILD>" --config Release
```

### BiasedDoom / experimental glTF (separate lane; after baseline)

```powershell
cmake -S "<BD_SOURCE>" -B "<BD_GLTF_BUILD>" -G "Visual Studio 17 2022" -A x64 -DCMAKE_TOOLCHAIN_FILE="<VCPKG_ROOT>/scripts/buildsystems/vcpkg.cmake" -DBIASEDDOOM_ENABLE_GLTF=ON -DBIASEDDOOM_BUILD_GLTF=ON -DBIASEDDOOM_ENABLE_PYTHON=OFF
cmake --build "<BD_GLTF_BUILD>" --config Release
```

**Important:** Missing libs or CMake failures are possible, and should be recorded rather than patched implicitly. GZDoom's OFF vcpkg options are not a promise no other dependencies are needed. BiasedDoom GLTF=ON requires fastgltf; validate the feature manifest and macro. UZDoom requires Python3 **for build tooling**. `USE_UPDATER=OFF` deliberately avoids updater complexities. Real source versions and generator selection can require adjustments; write a revised work order rather than improvising an unrecorded command.

## Proposed exact evidence after an approved run

Record each command, process exit code, complete redacted configure/compiler error excerpts, configuration file checksums, actual executable and support-resource SHA-256, build time, compiler/SDK versions, optional feature flags, and baseline game C-001…C-008. No source build is PASS in v0.6.0.
