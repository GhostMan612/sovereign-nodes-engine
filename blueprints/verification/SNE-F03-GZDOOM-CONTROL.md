# F-03 — GZDoom native Windows control lane (future only)

**Pinned source:** `ZDoom/gzdoom@c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`; root `CMakeLists.txt` Git blob `8a1becdb8546036d117f63db0a18c5a45541a8ba`.

## Source-observed facts

- Minimum CMake 3.16 at root, C++17 required; root Windows static vcpkg triplet is conditionally set as `x64-windows-static`.
- Options include `LIBVPX_VCPKG`, `OPENAL_SOFT_VCPKG`, `FORCE_INTERNAL_BZIP2`, `FORCE_INTERNAL_ZMUSIC`, `FORCE_INTERNAL_ASMJIT`, `FORCE_INTERNAL_CPPDAP`; their availability/values depend on the actual configuration path.
- Root `vcpkg.json` exists at pinned source, blob `69ba288e4957eb76c6e4044953f0dd5a85d2bddc`, with conditional features. Manifest existence does not prove all transitive packages installed or licenses cleared.

## Required prospective evidence

1. Signed AUTH-H host inventory, exact VS/MSVC/SDK + CMake version, approved dependency manifest and GZDoom source tree SHA/status.
2. Separate AUTH-B approval for configure/compile: chosen VS generator or Ninja, x64, approved CMake flags, isolated build tree, permitted writable output paths, offline/allowlisted dependency policy.
3. Configure log, exit code and actual CMakeCache with resolved flags; compiler/link evidence; generated engine executable + runtime resource PK3/DLL SHA-256.
4. Repeat under same effective inputs in a fresh build directory and compare file identity or explain nondeterminism. Reuse neither CMakeCache nor stale generated resource package.
5. Do **not** launch original game to demonstrate a build; F-04 `AUTH-T` is distinct.

**State:** SOURCE-OBSERVED only / CONFIGURE NOT RUN / BUILD NOT RUN / G4 OPEN. GZDoom is a test control, NOT adopted as foundation.
