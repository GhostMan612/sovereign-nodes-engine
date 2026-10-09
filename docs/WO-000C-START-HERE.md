# Start here: SNE-WO-000C / v0.5.0

## What this package is

A documented, pinned-source **compatibility and rendering feasibility** blueprint for Sovereign Nodes Engine. It maps game behavior to tests, candidate engine seams, and later operator-controlled implementation work. It does not modify the game repo or build an engine.

**Baseline:** `edc274f320cbd891c1f7fcef80f308562c0067ef`. Game revision `44034e97fd22129f919a18cadceb84466ef1bcd3`; candidates `c26ce2e6ca2a0c770f140cb25dde0d30073ca8f7`, `dbedcc894fb6866c48520cf27ae773f9957024b9`, `6147e0670458e48e63d1a40750f36dfc68b00f7f`.

## Reading order

1. `artifact-chain/work-orders/SNE-WO-000C.md` — scope, boundaries, blockers.
2. `blueprints/research/SNE-000C-FEATURE-TRACE.md` — exact code → scenario mapping.
3. `blueprints/research/SNE-000C-TEST-CASE-CATALOG.md` — independent test steps and verdict evidence.
4. `blueprints/research/SNE-000C-ZSCRIPT-PACKAGING.md` and `SNE-000C-HANDOFF-HARDENING.md` — current behavior and risks.
5. `blueprints/research/SNE-000C-VOXEL-GLTF.md`, `SNE-000C-LIGHTING-BUDGET.md`, `SNE-000C-PERFORMANCE-PROFILES.md` — visual extension and UHD 620 plan.
6. `blueprints/research/SNE-000C-WORLD-CONTINUITY.md` — sequential vs seamless distinctions.
7. `evidence/sources/SNE-000C-PIN-LEDGER.md` — exact reviewed revision/path links.
8. `governance/WO-000C-REVIEW-FINDINGS.md` — author self-review and unknowns.

## Important discoveries to verify (not runtime verdicts)

- Names `ORESHAA0` and `TOOLAA0` are suspicious under standard Doom sprite parsing. Build-time asset existence alone is insufficient.
- `hasParadox` is emitted as a JSON boolean but read via an integer scanner; verify with synthetic true/false examples.
- Unknown/newer handoff schemas are tolerated with warnings in currently inspected source; rejection is a proposed hardening requirement, not current behavior.
- BiasedDoom Python is not a sandbox; it requires explicit opt-in and must remain disabled for untrusted mods.

## Exit interpretation

If this package is committed, its **specification publication** is complete. Source audit is partial, all C-001..C-015 runtime evidence remains NOT RUN, performance unmeasured, independent review not accepted, and foundation ADR not signed. Next WO-000D deepens approved hardware/build *plans*; no permission to run a build is inferred.
