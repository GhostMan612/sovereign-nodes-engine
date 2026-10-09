# WO-000D — Dependency lock and SBOM protocol

## Fixed inputs required for repeatability

- Exact repository URL and 40-hex Git commit, plus recursive submodule SHAs if present; no floating branches, unreviewed shallow clones or submodule HEAD guesses.
- Git status must be clean for source candidate before configuration. Record all local patch hashes if future work explicitly permits them.
- Compiler path+version, CMake/Ninja/Windows SDK, VS build tools and environment architecture; Windows native must not be conflated with WSL.
- Package manager identity, checkout commit, manifest feature set, triplet, vcpkg baseline/overrides and package source/checksum; track bundled libraries **in addition to** external packages.
- Content origins and licenses for every engine asset, shader, model, ZMusic output, fonts, images and pack-ins. `*.wad`, proprietary IWADs and real genealogy are excluded from public artifact bundles.

## Reproduction stages (future execution authorization)

1. Freeze source / SDK / package managers into `SNE-000D-DEPENDENCY-RECORD.json` for each component.
2. Perform network/domain and license review before retrieving dependencies. An existing vcpkg cache is not automatically trusted as matching the manifest.
3. Capture configure summary and CMakeCache file hashes; distinguish generator (Visual Studio multi-config vs Ninja single-config), build mode, parallel count and toolchain CMake vars.
4. Capture linker inputs, exported symbols if relevant, hashes of executable, support DLLs and resource PK3. No promise of bitwise reproducibility until tested with a second clean-room build.
5. Verify executable's Git identity and custom game data identity independently. A `gzdoom.exe` filename alone is not proof of source pin.

## SBOM minimum row

`component_id`, source URL, upstream revision or version, SHA-256, copyright, SPDX/license link, bundled/vcpkg/system, static/dynamic/runtime, distribution obligations, CVE/exposure review status and reviewer. Unknown license or missing attribution is **BLOCKING** for redistribution.

## Explicit prohibited shortcuts

No `git submodule update --remote`, `git pull` or floating vcpkg baseline in the evidence run; no installer helpers that mutate global machine state without a separate owner-approved scope; no network verification by trying random downloads from the game. Build success alone is not software supply-chain approval.
