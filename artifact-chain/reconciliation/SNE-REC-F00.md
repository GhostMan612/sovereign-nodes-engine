# SNE-REC-F00 — Baseline and evidence reconciliation

- Latest **confirmed** user-pushed SNE planning commit: `1c01d2ff5bc3a1369210a7d68dd58269ecf6506d` (WO-000F).
- F-00 package: **v0.9.0** documentation-only overlay, not a new remote commit at authoring.
- Prior work orders A–F remain published with open acceptance; do not overwrite historical `SNE-ACC-*` signoff state.
- Intentional action count and Git blob preimages: `scaffold/SNE-F00-MANIFEST.md`.
- Runtime, code fork, hardware/build and third-party rights verification: **NOT RUN/OPEN**.
- Source review: author selected-file check completed; external independent review **PENDING**.
- `ADR-SNE-002`: **HOLD**.

## After user installation

Compare local full HEAD and diff to manifest, stage only explicit paths, validate staged 6 REPLACE + expected ADD count, inspect all changed documents and then operator may commit/push. Append actual new commit ID only after user supplies the Git output; no invented publication SHA. If conflicts, stop and reconcile manually without force reset.
