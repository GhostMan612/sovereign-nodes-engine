# SRC-UZDOOM-001 — UZDoom source-reference lane

**Pin:** `dbedcc894fb6866c48520cf27ae773f9957024b9`
**Status:** SELECTED FILES VERIFIED / NO BUILD.

- [`CMakeLists.txt`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CMakeLists.txt) — Requires CMake 3.16; C++20; find_package(Python3 3.6 REQUIRED) is used by the build (not necessarily embedded Python gameplay). LTO settings and platform/dependency flags matter.
- [`src/scripting/zscript/zcc_compile_doom.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/zscript/zcc_compile_doom.cpp) — ZScript compiler source exists.
- [`src/scripting/thingdef.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/scripting/thingdef.cpp) — Scripting/resource loading source reference.
- [`src/d_main.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/d_main.cpp) — Game startup and resource prefix registration includes gldefs, mapinfo and related definitions.
- [`src/common/models/voxels.cpp`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/src/common/models/voxels.cpp) — Voxel asset source exists.
- [`CONTRIBUTING.md`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/CONTRIBUTING.md) — Explicitly disallows AI-generated/AI-assisted code, comments, and art in pull requests to upstream.
- [`LICENSE`](https://github.com/UZDoom/UZDoom/blob/dbedcc894fb6866c48520cf27ae773f9957024b9/LICENSE) — GPLv3 root with specific noted different-license assets and branding; audit before copying/redistribution.

## Contribution policy versus rights in a fork

The **upstream contribution policy** addresses what UZDoom maintainers will accept in their repository. It does **not by itself** revoke rights granted by GPL to make or distribute a compliant independent fork. SNE must not submit AI-assisted changes upstream contrary to policy. GPL compliance, provenance and asset exclusions require a separate review; do not claim an automatic right to reuse every bundled asset.

## Blocking checks

Prove project `version "4.14"` and selected ZScript APIs compile. Confirm Python3 needed for build tooling is present, but do not confuse CMake's Python3 requirement with BiasedDoom's embedded runtime. Audit asset directories `branding/`, `wadsrc_bm/`, `wadsrc_extra/`, `wadsrc_widepix/` against license notices.
