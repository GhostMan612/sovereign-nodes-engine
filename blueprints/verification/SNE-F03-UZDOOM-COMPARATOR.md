# F-03 — UZDoom native Windows comparator lane (future only)

**Pinned source:** `UZDoom/UZDoom@dbedcc894fb6866c48520cf27ae773f9957024b9`; CMake root Git blob `39dcbefed262eab124f23da8efdb7b3ce331dcd9`; contributor guide blob `84621215c99b1da9af913d082e65e20b6d725175`.

## Source-observed facts and risks

- `CMAKE_CXX_STANDARD 20` (C++20), minimum CMake 3.16; `find_package(Python3 3.6 REQUIRED)` for **build tooling**. Python installed under WSL is not necessarily a suitable native Windows interpreter.
- `FORCE_NO_LTO` exists (normally default OFF); Windows `USE_UPDATER` defaults OFF. Diagnostic proposal: `FORCE_NO_LTO=ON`, `USE_UPDATER=OFF`, not an asserted working recipe.
- `BUILD_NONFREE` source option defaults ON in root at the pinned revision; preserve asset/rights visibility and explicitly review whether to disable it for a future lawful minimal build. Changing it may affect resources/compatibility: record exact choice, no silent option flip.
- Direct root `vcpkg.json` lookup at pinned SHA returned NOT FOUND. That does *not* establish absence of dependency tooling or nested manifests. Independently inspect project scripts/dependencies and do not adopt GZDoom's vcpkg assumptions without proof.
- Upstream `CONTRIBUTING.md` rejects AI-assisted source submissions. Do not submit AI-assisted PRs to UZDoom. Upstream contribution rules do not automatically prohibit an appropriately licensed independent downstream fork, which still requires legal assessment.

## Future acceptance

Separate authorization and isolated C++20 toolchain, Python build interpreter, source/submodule SHA, dependency mapping, explicit updater/LTO/nonfree option values, configure/build/resource hashes and two fresh attempts. No run or compiler measurement exists here. `AUTH-B` for GZDoom must never be inherited by UZDoom.
