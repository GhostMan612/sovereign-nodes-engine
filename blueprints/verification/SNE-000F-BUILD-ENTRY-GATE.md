# WO-F — Native Windows build admission gate (proposal only)

**NOT AUTHORIZED AND NOT RUN.** `SNE-000D-REPRO-BUILD-COMMANDS.md` contains conceptual MSVC commands. Do not execute them, install SDKs or clone engines without an operator-approved execution work order.

## Mandatory prerequisite checklist

- [ ] owner explicitly approves the host, source checkout, output/build directories, permitted read/write operations, duration and network/dependency policy.
- [ ] exact candidate Git commit (GZ/UZ/BD), submodule revisions, origin, clean state and checksum frozen.
- [ ] Visual Studio C++ toolset, Windows SDK, CMake/generator and Python **build tool** (UZDoom) versions recorded on host.
- [ ] all dependencies available under an approved location with hash and license; no auto-installer or `curl | sh`.
- [ ] no unapproved copying of commercial IWAD, source game modifications, extra network telemetry, Defender changes or Python mod execution.
- [ ] build configuration, generator (`VS 2022` multi-config vs `Ninja` single-config), x64 ABI, static/runtime linkage and optional features recorded.
- [ ] candidate source/build directories isolated from `C:\sovereign-nodes-engine` and canonical game repository.

## Candidate-specific baseline flags to review

| Candidate | Source state | Potential baseline controls | Main unknown |
|---|---|---|---|
| GZDoom | C++17 | first source parity lane; controlled Windows MSVC x64 | installed SDK, dependencies/resource PK3 and actual build |
| UZDoom | C++20 | `FORCE_NO_LTO=ON`, `USE_UPDATER=OFF` as *proposed* diagnostic | build Python3, ABSEIL libs and Windows toolchain |
| BiasedDoom | C++17 | `BIASEDDOOM_ENABLE_GLTF=OFF`, `BIASEDDOOM_ENABLE_PYTHON=OFF` first | baseline feature branches, optional fastgltf/CPython external deps |

No toggle above is proof the named feature is absent or secure at runtime; compiled configuration must be observed. For BiasedDoom advanced lane: test `GLTF=ON` separately, keep Python OFF and document why a texture/animation fixture is lawful.

## Distinguish outcome classes

`CONFIGURE FAIL` = toolchain/dependency/config issue until diagnosed. `COMPILE FAIL` = compiler/link issue, not game incompatibility. `RESOURCE FAIL` = packaged PK3/data issue. `GAME FAIL` = runtime C-series evidence *after* a proven engine build. `PERFORMANCE FAIL` = measured and fair UHD 620 trace; never inferred from build errors.

## Output record

Record CMake generator and actual command, source/submodule SHAs, flags, compiler/linker/SDK versions, dependency list and hashes, tool exit code, redacted configure/build logs SHA, executable and core resource hashes, binary signatures if present, and reviewer. Separate successful native build from successful engine gameplay verification.
