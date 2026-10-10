# WO-F — Evidence result register (blank / non-execution status)

| ID | Scope | Evidence identity | Execution status | Independent review | Operator acceptance |
|---|---|---|---|---|---|
| F-R001 | source sprite and GLDEFS hazard | `SNE-SRC-GAME-005.md` | SOURCE-OBSERVED / NOT RUN | PENDING | PENDING |
| F-R002 | handoff `hasParadox` boolean | `SNE-SRC-GAME-005.md` | SOURCE-OBSERVED / NOT RUN | PENDING | PENDING |
| F-R003 | PK3 validator-source discrepancy | `SNE-SRC-GAME-005.md` | SOURCE-PATH DISCREPANCY | PENDING | PENDING |
| F-R004 | original PK3 and legal IWAD | NONE | NOT CAPTURED | PENDING | PENDING |
| F-R005 | Windows candidate build record | NONE | NOT RUN | PENDING | PENDING |
| F-R006 | C-001…C-008 parity per candidate | NONE | NOT RUN | PENDING | PENDING |
| F-R007 | UHD 620 frame-time recordings | NONE | NOT RUN | PENDING | PENDING |
| F-R008 | rights/security SBOM | NONE | NOT CLEARED | PENDING | PENDING |
| F-R009 | independent G1–G8 review | NONE | NOT COMPLETED | PENDING | PENDING |
| F-R010 | ADR-SNE-002 selection | NONE | **HOLD** | PENDING | PENDING |

## Adding a future measured row

Use one `templates/SNE-000F-CASE-RESULT.json` with real source SHA, artifact hashes, setup, negative control, observable outcome and signed review; then reference its immutable **approved and sanitized** evidence ID in this table. Do not fill with guessed numbers, fictitious binary names or fabricated log timestamps. Raw evidence stays in an operator-approved off-repo location.
