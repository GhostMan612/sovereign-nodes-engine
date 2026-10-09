# SNE-WO-000B — Detailed upstream engine audit

- Phase: SNE-P00
- Research execution: READ-ONLY INSPECTION PERFORMED on selected pinned files, 2026-10-09
- Status: EVIDENCE PRODUCED / FIRST-PASS REVIEWED / NOT ACCEPTED
- Base: SNE `369722f`; current-game source `44034e9`; candidate pins in `SNE-SOURCE-PINS-000B.md`
- Engine implementation: NOT AUTHORIZED

## Mission

Pin UZDoom, GZDoom and BiasedDoom. Inspect their relevant source code and documentation for concrete Doom compatibility, voxel/model support, GLDEFS and rendering, scripting, hub/world state, build constraints, licensing, and contribution policy. Compare the architectural surfaces against the active Sovereign Nodes FPS contracts.

## Findings completed (selected files, not entire repositories)

1. All five historical/candidate upstream commit revisions identified; three engine candidates receive targeted path-level review.
2. Actual GZDoom voxel/parser/model and light parser source locations found.
3. Actual UZDoom actor compiler, renderer/light, voxel, hub and contributor policy code/docs found.
4. Actual BiasedDoom glTF header/implementation, build options, vcpkg feature dependencies and model-workflow docs reviewed.
5. Build-language baselines and separation between GPL engine licenses, third-party notices and branding/assets recorded.
6. Research reference for original game's ZScript, MAPINFO, GLDEFS, HUD, map generator/validator and Godot/Doom handoff mapped.
7. Preliminary extension seam strategy and independently testable gates authored.

## Not completed / stop conditions

- No complete recursive code inventory, source builds, local clone, link/integration proof, GPU benchmark or runtime parity proof.
- Dependency and per-file licensing inventory is sampled, not a release clearance.
- Preserve upstream file licenses and source attribution in any future authorized derivative; no source is copied here.
- No external GitHub write, commit or fork authorization.

## Deliverables

- `blueprints/research/SNE-000B-ENGINE-CODE-MAP.md`
- `blueprints/research/SNE-000B-COMPILER-BUILD-MATRIX.md`
- `blueprints/research/SNE-000B-EXTENSION-SEAMS.md`
- `blueprints/research/SNE-000B-MAINTENANCE-RISK.md`
- `blueprints/research/SNE-000B-TEST-GATES.md`
- `evidence/sources/SNE-SOURCE-PINS-000B.md`, three detailed source records
- Updated research matrices and dependencies
- Full work-order artifact chain: evidence → review → verification → acceptance → reconciliation

## Acceptance criteria

Provenance pins and paths reviewed; no undocumented PASS; licensing/contribution distinction made; compatibility claims limited to source inspection; review actions and work order C handoff enumerated; operator approval required for WO-000B acceptance. An independent reviewer should examine a representative subset of raw upstream code and every major open blocker.
