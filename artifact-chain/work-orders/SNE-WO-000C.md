# SNE-WO-000C — Compatibility and rendering feasibility blueprint

- Phase: SNE-P00
- Revision: v0.5.0
- Base engine-scaffold commit: `edc274f320cbd891c1f7fcef80f308562c0067ef`
- Source pin: game `44034e97fd22129f919a18cadceb84466ef1bcd3`; GZDoom `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`; UZDoom `dbedcc894fb6866c48520cf27ae773f9957024b9`; BiasedDoom `6147e0670458e48e63d1a40750f36dfc68b00f7f`
- State: SOURCE-INFORMED BLUEPRINT PREPARED; RUNTIME NOT RUN; INDEPENDENT REVIEW NOT ACCEPTED
- Authorization: research/specification only. No implementation, engine builds, game launch, repository push, fixture generation, dependency install, or private-data access.

## Mission

Map C-001..C-015 to observable pass/fail cases and inherited engine extension seams. Preserve the existing Sovereign Nodes FPS experience before adding voxels, glTF, new lighting, or simulated connected-world zones. Separate standalone GZDoom-family gameplay from ZDaemon-specific multiplayer compatibility.

## Owned deliverables

1. `blueprints/research/COMPATIBILITY-TEST-MATRIX.md`: C-001..C-015 and subcase ownership.
2. `blueprints/research/SNE-000C-TEST-CASE-CATALOG.md`: full arrange/act/assert evidence requirements.
3. `blueprints/research/SNE-000C-FEATURE-TRACE.md`: actual game-path-to-source-to-test mapping.
4. `blueprints/research/SNE-000C-ZSCRIPT-PACKAGING.md`: parser, ZIP, sprite, map identity.
5. `blueprints/research/SNE-000C-HANDOFF-HARDENING.md`: version/boolean/freshness/tamper.
6. `blueprints/research/SNE-000C-VOXEL-GLTF.md`: optional asset experimentation without simulation rewrite.
7. `blueprints/research/SNE-000C-LIGHTING-BUDGET.md`: controlled light stress and fallback.
8. `blueprints/research/SNE-000C-WORLD-CONTINUITY.md`: hub transitions vs actual simultaneous zones.
9. `blueprints/research/SNE-000C-PERFORMANCE-PROFILES.md`: UHD 620 capture methodology.
10. Pinned source and self-review evidence in `evidence/sources/`, `governance/` and `artifact-chain/`.

## Source-derived blockers requiring operator test (NOT demonstrated crashes)

- **C-RISK-01**: Existing `ORESHAA0` and `TOOLAA0` asset references exceed standard four-prefix-plus-frame/rotation conventions used by GZDoom sprite decoding. A static name/existence check may pass while runtime frame resolution fails. Confirm actual packed sprite mapping; do not rename original game source in this phase.
- **C-RISK-02**: `sn_handoff.zs` scans `hasParadox` with `ScanInt` while Godot's JSON producer emits a boolean. Confirm true/false behavior, record any mismatch; never use real ancestor data.
- **C-RISK-03**: Schema-absent/newer handoff is warning-tolerant in current reader; do not claim its parser rejects unknown schemas. Security hardening remains an unimplemented design target.
- **C-RISK-04**: BiasedDoom documents conditional glTF loading and notes embedded `.glb` texture limitations; compare separate geometry/animation/texture tests.

## Exit gate

Every Tier-A case has an explicit test procedure, controls, expected evidence, negative case and failure condition. Reviewer confirms no benchmark, compatibility, or foundation-decision PASS has been fabricated. This work order's **blueprint** can be marked ready for operator review; technical runtime acceptance remains OPEN.

## Deferred implementation handoff

Any code/source change requires a separate operator-approved work order in the owning repository; preserve the hybrid Godot/Doom boundary, existing game RULES/AGENTS, and synthetic-only Mantle data. Keep Phase 01 foundation ADR-SNE-002 on hold until C/D/E gates.
