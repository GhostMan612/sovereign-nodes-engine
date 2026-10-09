# SNE-WO-000B — Upstream engine code audit

**Version:** 0.4.0
**Research date:** 2026-10-09
**Published SNE base:** [`369722fcd0839447cd5ecf5b78aa1ca7d8e2645c`](https://github.com/GhostMan612/sovereign-nodes-engine/commit/369722fcd0839447cd5ecf5b78aa1ca7d8e2645c)
**Status:** Source evidence expanded / acceptance pending / builds NOT RUN

## Read in this order

1. `artifact-chain/work-orders/SNE-WO-000B.md` — scope and stop conditions.
2. `evidence/sources/SNE-SOURCE-PINS-000B.md` — immutable upstream pins, actual file URLs.
3. `blueprints/research/SNE-000B-ENGINE-CODE-MAP.md` — code and integration seams.
4. `blueprints/research/SNE-000B-COMPILER-BUILD-MATRIX.md` and `DEPENDENCY-LICENSE-MATRIX.md` — build/license risks.
5. `blueprints/research/SNE-000B-EXTENSION-SEAMS.md` and `SNE-000B-MAINTENANCE-RISK.md` — proposed hybrid extension layout.
6. `blueprints/research/SNE-000B-TEST-GATES.md` — runtime parity cases **NOT EXECUTED**.
7. `governance/WO-000B-REVIEW-FINDINGS.md` — reviewer findings and blockers.
8. `artifact-chain/verification/SNE-VER-000B.md` and `artifact-chain/acceptance/SNE-ACC-000B.md` — NOT ACCEPTED.

## Key source-derived findings

- **GZDoom** already has `VOXELDEF`, voxel parsing, voxel-to-model conversion, GLDEFS lighting parsing, ZScript actor code, and hub-state code; extending this infrastructure is lower-risk than replacing everything.
- **UZDoom** preserves descendant voxel/ZScript/hub systems but requires C++20 at its inspected source pin. Its contributor policy bars AI-assisted code PRs, a **contribution constraint**, not an automatic GPL licensing ban on a separately maintained fork.
- **BiasedDoom** has guarded `fastgltf` model-loader sources and CMake features for glTF/Python. The docs note external-texture `.gltf` is safer than embedded-texture `.glb`; claimed capabilities need compilation/runtime proof. Its announced intent to deprecate ZScript is a roadmap risk, not proof of present removal.
- **Existing Sovereign Nodes FPS** depends on MAPINFO `version "4.14"`, three `addfragments`, three named maps, GLDEFS sprite-frame light bindings, DoomEdNums, status bar, and Godot-to-Doom handoff. None has been tested here on any candidate engine.

## Preliminary recommendation (NOT ADR)

Keep GZDoom and UZDoom as fork candidates, use BiasedDoom as an optional experimental renderer/model reference. Reject a total renderer rewrite until a measured impossibility is demonstrated. Preserve ZDaemon as a separate compatibility lane; do not assume new renderer features are multiplayer-portable.

## Next

Proceed to WO-000C compatibility and rendering feasibility review after resolving the open WO-000B evidence gaps and obtaining operator acceptance of this research packet. Phase 00 foundation selection remains on hold.
