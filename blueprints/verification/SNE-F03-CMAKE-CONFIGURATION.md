# F-03 — CMake cache/configure and binary provenance checks

## Before configure (future AUTH-B only)

- Worktree clean at approved SHA and correct submodule state. Empty candidate-specific build directory. Record CMake version, generator, platform, toolset, approved flags and dependency roots.
- Use a deliberately chosen `CMAKE_TOOLCHAIN_FILE` only when authorized and available; do not silently auto-bootstrap vcpkg. Review `VCPKG_TARGET_TRIPLET`, `VCPKG_MANIFEST_FEATURES`, Python interpreter and all feature defaults.
- `CMAKE_CXX_STANDARD` is a source requirement; actual `cl`/SDK must support selected dialect. Detect configure warnings like unused manually specified options as discrepancies requiring review.

## After configure (if later run)

Capture redacted configure stdout/stderr, process exit, CMakeCache raw SHA, material values for `CMAKE_GENERATOR`, `CMAKE_CXX_COMPILER`, `CMAKE_BUILD_TYPE`/`CMAKE_CONFIGURATION_TYPES`, `CMAKE_MSVC_RUNTIME_LIBRARY`, `CMAKE_TOOLCHAIN_FILE`, `VCPKG_TARGET_TRIPLET`, `Python3_EXECUTABLE`, feature flags, and generated build files. Validate scope paths did not escape.

Cache capture ≠ build; build success ≠ resource completeness. Don't inject undocumented flags to quiet an error, and don't treat a stale CMakeCache as a valid new trial. Mark unexpected optional default ON (Python/glTF, updater, nonfree assets) for review before proceeding.
