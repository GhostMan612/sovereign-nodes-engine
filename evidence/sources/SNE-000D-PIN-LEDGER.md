# WO-000D — Immutable source pin and file observation ledger

**Retrieved:** 2026-10-09 using connected GitHub read-only file/commit inspection. **Source classifications:** `SOURCE-OBSERVED` for CMake/manifest lines; `DOC-CLAIM` for README/instructions; `NOT-RUN` for commands/build/runtime; no engine branch was updated in this package.

| Source | Immutable commit | Exact file | Relevant inspected evidence |
|---|---|---|---|
| SNE planning | `706db57a4fbabd701244dd9e4674a59f7ab044f3` | `artifact-chain/work-orders/SNE-WO-000D.md` | baseline work order to replace |
| GZDoom | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | `CMakeLists.txt` | lines 1, 27–50 (CMake 3.16/C++17/vcpkg static), 217–223 dependency lookups |
| GZDoom | `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7` | `vcpkg.json` | optional libvpx/OpenAL features, pinned builtin baseline |
| UZDoom | `dbedcc894fb6866c48520cf27ae773f9957024b9` | `CMakeLists.txt` | lines 1–55 (C++20, static libs, release IPO, updater default OFF, MSVC-specific updater, required Python3 >=3.6), lines 167–175 Python script tool |
| UZDoom | `dbedcc894fb6866c48520cf27ae773f9957024b9` | `CONTRIBUTING.md` | independent license and upstream AI-assisted PR constraints (previous WO-B verified) |
| BiasedDoom | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | `CMakeLists.txt` | lines 1–95 (Python/glTF options, static vcpkg, fastgltf CMake config, C++17) |
| BiasedDoom | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | `vcpkg.json` | `gltf-support` feature, CPython port and pinned dependency overrides |
| BiasedDoom | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | `README.md` | Windows VS 2022 build examples and version claims (DOC-CLAIM, not build proof) |
| BiasedDoom | `6147e0670458e48e63d1a40750f36dfc68b00f7f` | `docs/scripting/python.md` | Python is arbitrary native-equivalent; not sandboxed (verified in WO-C) |
| Original game | `44034e97fd22129f919a18cadceb84466ef1bcd3` | `games/SovereignNodesFPS/game/MAPINFO.txt` | version 4.14, 3 ZScript fragment links, MAP01–MAP03 progression |
| Original game | `44034e97fd22129f919a18cadceb84466ef1bcd3` | `games/SovereignNodesFPS/game/GLDEFS.txt` | sprite-bound lights, custom source-game correctness controls |

## Direct pinned URLs

- GZ CMake: https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/CMakeLists.txt
- GZ vcpkg: https://github.com/ZDoom/gzdoom/blob/c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7/vcpkg.json
- UZ CMake: https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt
- UZ contribution: https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md
- BD CMake: https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/CMakeLists.txt
- BD vcpkg: https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/vcpkg.json
- BD README: https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/README.md
- BD Python safety: https://github.com/EricsonWillians/BiasedDoom/blob/6147e0670458e48e63d1a40750f36dfc68b00f7f/docs/scripting/python.md
- Original MAPINFO: https://github.com/GhostMan612/Sovereign-Nodes/blob/44034e97fd22129f919a18cadceb84466ef1bcd3/games/SovereignNodesFPS/game/MAPINFO.txt

## Limits

Target device not inspected. Toolchain not queried. Root CMake line reads are not an exhaustive package closure; compiler/platform branches and libraries change with options. No build, link, GPU test or sample frame-time capture performed. The absence of a manifest under an expected path is not definitive evidence that no dependency installer exists elsewhere. Pin any changed upstream revision independently.
