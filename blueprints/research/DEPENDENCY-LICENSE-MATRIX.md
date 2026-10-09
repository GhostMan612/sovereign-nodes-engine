# Phase 00 dependency and licensing matrix — WO-000D reproducibility update

**Status: PARTIAL SOURCE REVIEW — NOT A DISTRIBUTION LICENSE CLEARANCE.** Record exact source and binary licenses before redistributing any engine fork, helper, brand asset, library, installer or custom resource.

| Candidate | Root license and per-file variation | Supply-chain facts observed | Owner review blocker |
|---|---|---|---|
| GZDoom | GPL-3 main project, historical BSD-style and LGPL code files | root CMake/vcpkg manifest and `libraries/` bundled sources; `vcpkg.json` optional libvpx/OpenAL features | transitive SBOM, binary notice package, WAD/game asset rights |
| UZDoom | GPLv3+ code contribution guidance; per-file BSD predecessors; separately licensed CC BY-SA branding | root CMake C++20, Abseil static, Python3 build requirement, updater CURL path; no root vcpkg manifest observed at pinned path | bundled assets, source notices, provenance of updater/CURL/Abseil, upstream AI PR policy vs independent fork |
| BiasedDoom | GZDoom-derived mixed per-file terms; fastgltf and CPython separately governed | root CMake controls `fastgltf`, embedded Python, audio libraries; vcpkg pin and overrides (Python 3.12.13) | transitive SBOM, CPython distribution, asset ownership, unsandboxed Python risk |

## Mandatory closure process before distribution

1. Pin checkout, submodules, build toolchain, vcpkg/other package baselines, archives and binary dependencies; record SHA-256 and authoritative URLs.
2. Generate an inventory of every statically and dynamically linked component and any assets embedded into binary or resource PK3. Each row: name, version, origin, license SPDX or file, copyright holder, notice requirement, source origin, binary linking and approval state.
3. Review relevant vendor and model resources separately; a GPL engine source license does NOT license commercial Doom II IWAD, community mods, upstream logos or unrelated graphics.
4. Preserve copyright headers and applicable GPL source/code offer terms for downstream derivative distribution; legal review must assess mixed terms and exact intended delivery.
5. UZDoom upstream forbids AI-assisted **upstream submissions**, which is separate from what its GPL license permits for a compliant independently maintained derivative; never conflate them.
6. No authorized approval or legal advice is supplied by this document; independent reviewer and operator must sign off.

See `SNE-000D-DEPENDENCY-LOCK-PROTOCOL.md`, `SNE-000D-THREAT-LICENSE-CHECKLIST.md`, and `templates/SNE-000D-DEPENDENCY-RECORD.json`.
