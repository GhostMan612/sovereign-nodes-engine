# WO-000D — Native Windows candidate build lanes

All lanes below are **future operator-run hypotheses**. Source revisions and root CMake observations are pinned; recipe success is not established.

| Lane | Source pin | Host/compiler hypothesis | Core features/config | Known complicating condition | Stop gate |
|---|---|---|---|---|---|
| GZ-WIN-x64 | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | Windows native MSVC x64, VS 2022 C++ toolset (check availability) | C++17, `x64-windows-static` vcpkg default in root CMake under Windows | local SDL/ZMusic/libraries availability, resources, audio setup | toolchain/dep failure or missing custom PK3 |
| UZ-WIN-x64 | `dbedcc894fb6866c48520cf27ae773f9957024b9` | Windows native MSVC x64 (not proven) | C++20, `FORCE_NO_LTO=ON` for first diagnostic build, `USE_UPDATER=OFF` | CMake requires Python3 >=3.6 at configure; optional updater is MSVC-specific | missing Python, SDK, toolchain, Abseil/CURL resources |
| BD-WIN-x64 | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | Windows native MSVC x64 (not proven) | C++17; first compatibility baseline can request Python OFF, glTF separately controlled | `fastgltf CONFIG REQUIRED` if GLTF=ON; glTF build path must be verified independently | fastgltf config, Python trust, glTF dependencies |
| ZD-NATIVE | PIN LATER | ZDaemon-specific product lane, not one of these forks | no inferred modern ZScript/glTF equivalence | multiplayer protocol/version divergence | never infer from GZ/UZ results |

## Experiment partitioning

1. Baseline build: stable first-run flags, no unverified optional graphics features, no project source patches.
2. Candidate-specific controlled toggle: for UZDoom, compare LTO ON/OFF only after baseline; for BiasedDoom, GLTF ON/OFF and Python OFF/trusted-on only under explicit approval.
3. Keep `Release`, `RelWithDebInfo`, `Debug` differentiated; CMake multi-config generators use `--config` while Ninja single-config uses `CMAKE_BUILD_TYPE`. Never compare debug and release FPS.
4. Source project build folders cannot share CMake cache, dependency snapshot or output directory across candidate or compiler lanes.
5. Never infer `USE_UPDATER` is enabled: source declares it OFF by default on Windows. If enabled, updater CMake branch raises non-MSVC fatal error.

**Source pins:** `evidence/sources/SNE-000D-PIN-LEDGER.md`. Tool setup is deliberately deferred, and no compiled artifact is included.
