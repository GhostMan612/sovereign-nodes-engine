# SNE-SRC-UZDOOM-004 — UZDoom Windows compilation probe

**Repo:** `UZDoom/UZDoom` at `dbedcc894fb6866c48520cf27ae773f9957024b9`; **status:** SOURCE-OBSERVED / NEVER BUILT.

- [Root CMake](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt) lines 1–29: minimum CMake 3.16, C++20, bundled `BUILD_SHARED_LIBS OFF`, optional Release/RelWithDebInfo IPO, `FORCE_NO_LTO` to disable.
- Lines 31–51: `USE_UPDATER` Windows default OFF; when updater enabled, Windows/MSVC constraint and CURL dependency apply. **Do not generalize updater-only MSVC requirement to engine as a whole.**
- Lines 54–55: `find_package(Python3 3.6 REQUIRED)`; build tooling, not embedded CPython game logic. Lines 167–175 compile translated scripts with Python3 interpreter.
- [Contributor policy](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md) prohibits AI-assisted upstream PRs, separate from source-license downstream fork questions.

**Hypothesis:** first diagnostics lane `FORCE_NO_LTO=ON` and `USE_UPDATER=OFF` avoids known optional complexity without claiming the compiled result passes. Unknown: MSVC/SDK versions, bundled libraries, release resource packs, actual test performance.

**Future gate:** C++20 compiler inventory, exact Python path/version, configure logs, built artifact and game parity. Compile errors or missing custom gameplay remain BLOCKED.
