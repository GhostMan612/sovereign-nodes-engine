# F-03 — Non-executable command patterns for future signed AUTH-B

**All commands in this document are examples and NOT EXECUTED.** Placeholder paths do not exist here. An owner must authorize *each candidate and exact resolved paths/flags*; no blanket or automatic command execution.

## Prerequisite: actual host inventory under separate AUTH-H

Native Windows CMake/MSVC/SDK must be observed, not inferred. VS 2022 x64 generator is a proposal, not known installed. Do not run installer, bootstrap, `git clone` or `git pull` by default.

## GZDoom control — conceptual

```powershell
cmake -S "<APPROVED_GZ_SOURCE>" -B "<APPROVED_GZ_BUILD>" -G "Visual Studio 17 2022" -A x64 -DLIBVPX_VCPKG=OFF -DOPENAL_SOFT_VCPKG=OFF
cmake --build "<APPROVED_GZ_BUILD>" --config Release
```

## UZDoom comparator — separate conceptual lane

```powershell
cmake -S "<APPROVED_UZ_SOURCE>" -B "<APPROVED_UZ_BUILD>" -G "Visual Studio 17 2022" -A x64 -DFORCE_NO_LTO=ON -DUSE_UPDATER=OFF
cmake --build "<APPROVED_UZ_BUILD>" --config Release
```

## BiasedDoom baseline — separate experimental lane

```powershell
cmake -S "<APPROVED_BD_SOURCE>" -B "<APPROVED_BD_BASE_BUILD>" -G "Visual Studio 17 2022" -A x64 -DBIASEDDOOM_ENABLE_PYTHON=OFF -DBIASEDDOOM_ENABLE_GLTF=OFF -DBIASEDDOOM_BUILD_GLTF=OFF
cmake --build "<APPROVED_BD_BASE_BUILD>" --config Release
```

These echo the older `SNE-000D-REPRO-BUILD-COMMANDS.md` *planning examples* and are **not proven working invocations**. A source revision, compiler or vcpkg toolchain difference can require additional approved changes; a missing dependency must be reported, not secretly installed. `BUILD_NONFREE` in UZDoom must be explicitly reviewed before selecting the final configuration.

## Ninja caution

If future operator chooses Ninja instead, configure must use an initialized approved MSVC environment, omit `-A x64`, use a new build tree and specify the single-config `-DCMAKE_BUILD_TYPE=Release`; mixing generator caches invalidates the trial.
