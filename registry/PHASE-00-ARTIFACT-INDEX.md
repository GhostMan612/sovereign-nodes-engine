# SNE Phase 00 — Published documentation registry / F-03 v1.2.0 draft

| Work order | Actual operator publication or status | Technical acceptance |
|---|---|---|
| WO-A | `369722f` | source research only |
| WO-B | `edc274f` | candidate source audit only |
| WO-C | `706db57` | C-001…C-015 NOT RUN |
| WO-D | `1f21e4c` | Windows/UHD NOT RUN |
| WO-E | `1644fb8` | ADR HOLD |
| WO-F | `1c01d2f` | readiness, all permissions unapproved |
| F-00 | `148dc28` | author review packet, independent PENDING |
| F-01 | `725fded` | authorization templates, NONE approved |
| **F-02** | **`f2f2cfec676b9a5254fa2a5a7e6f08198581fa09`** | blueprint published; host/PK3/fixtures NOT RUN |
| **F-03** | **v1.2.0 ZIP PREPARED; future Git SHA unknown** | build readiness only; G4 NOT RUN |

## New F-03 artifacts

- Work order / start: `artifact-chain/work-orders/SNE-WO-F03.md`; `docs/SNE-F03-START-HERE.md`.
- Candidate build controls: `blueprints/verification/SNE-F03-GZDOOM-CONTROL.md`, `SNE-F03-UZDOOM-COMPARATOR.md`, `SNE-F03-BIASEDDOOM-EXPERIMENT.md`.
- Dependency/toolchain/configuration: `SNE-F03-WINDOWS-TOOLCHAIN.md`, `SNE-F03-DEPENDENCY-SBOM.md`, `SNE-F03-GENERATOR-MATRIX.md`, `SNE-F03-CMAKE-CONFIGURATION.md`.
- Build evidence and reproducibility: `SNE-F03-REPRODUCIBILITY-TRIALS.md`, `SNE-F03-RESOURCE-HASHES.md`, blank `templates/SNE-F03-*.json`.
- Governance: `governance/SNE-F03-AUTHORIZATION-REQUEST.md`, `SNE-F03-RISK-REGISTER.md`, evidence/verification/acceptance/reconciliation in `artifact-chain/`.
- Pinned author primary-source: `evidence/sources/SNE-F03-SOURCE-PINS.md` and `SNE-F03-CMAKE-OBSERVATIONS.md`.
- ZIP reproducibility: `scaffold/SNE-F03-MANIFEST.md`, `SNE-F03-SHA256.json`, `SNE-F03-BUILD-VERIFICATION.json`, exact staging in `SNE-F03-INSTALL.md`.
- `ADR-SNE-002` remains **HOLD and unmodified** by F-03.

Publication of this packet will not authorize toolchain inspection, compilation, game launch, GPU benchmark or source code edits. Record the actual future F-03 Git SHA in a later reconciliation document, not an invented number.
