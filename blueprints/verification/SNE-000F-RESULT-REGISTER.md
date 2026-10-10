# WO-F — Forward evidence register (F-02 blueprint)

Historical IDs and statuses must not be rewritten as PASS because a newer document was published. This file is a planning index, not a test report.

| ID | Evidence target | Relevant source or plan | Status | Independent/operator acceptance |
|---|---|---|---|---|
| F-R001 | sprite family/GLDEFS | `SNE-SRC-GAME-005.md`; `SNE-F02-SPRITE-ALIAS-MATRIX.md` | SOURCE-ONLY / NOT RUN | PENDING |
| F-R002 | handoff boolean | `SNE-F00-HANDOFF-PARSER-REVIEW.md`; `SNE-F02-HANDOFF-BOOLEAN.md` | SOURCE-ONLY / NOT RUN | PENDING |
| F-R003 | missing validator path | `SNE-F02-VALIDATOR-PATH.md` | EXACT PATH LOOKUP FAILED; EQUIVALENT COVERAGE OPEN | PENDING |
| F-R004 | original PK3 + lawful IWAD | `SNE-F02-PK3-STRUCTURE.md`; `SNE-F02-IDENTITY-AND-CHECKSUM.md` | NOT CAPTURED | PENDING |
| F-R005 | Windows candidate build | `SNE-F02-F03-ENTRY-GATE.md` | NOT RUN | PENDING |
| F-R006 | C-001..C-008 original parity | `SNE-F02-GAPNODE-CONTROL.md` | NOT RUN | PENDING |
| F-R007 | UHD 620 frametime | `SNE-000F-HARDWARE-TRIAL-MATRIX.md` | NOT RUN | PENDING |
| F-R008 | rights/security/SBOM | `SNE-F02-EVIDENCE-QUALITY.md` | NOT CLEARED | PENDING |
| F-R009 | G1/G7 independent reviewer | F-00 source packet and F-02 review protocol | NOT COMPLETED | PENDING |
| F-R010 | ADR-SNE-002 foundation | ADR-SNE-002 | HOLD | PENDING |
| F-R011 | F-00 selected author source recheck | `SNE-F00-PIN-LEDGER.md` | AUTHOR SOURCE ONLY | PENDING |
| **F-R012** | F-01 authorization/scopes | `725fded39c0d50139ab76182211e32375bc2764e` operator-published documentation | TEMPLATE PUBLISHED; NO AUTH APPROVED | PENDING |
| **F-R013** | F-02A noninvasive host metadata | `templates/SNE-F02-HOST-INVENTORY.json` | NOT RUN | PENDING |
| **F-R014** | F-02A original B0 PK3/WAD static identity | `templates/SNE-F02-BASELINE-IDENTITY.json` | NOT CAPTURED | PENDING |
| **F-R015** | F-02B B1 sprite fixture and B2 synthetic handoff | `templates/SNE-F02-FIXTURE-CONTROL.json` | NOT RUN | PENDING |
| **F-R016** | Pinned builder SNDINFO intentional omission | `SNE-F02-PRIMARY-SOURCE-NOTES.md` | SOURCE-OBSERVED (AUTHOR); PK3 NOT RUN | PENDING |

A future real result must specify immutable evidence ID, operator authorization, original/fixture hashes, legal external IWAD ref, actual artifacts, negative controls, independent reviewer and dated operator disposition. New runs should use new IDs or explicit supersession records; never silently overwrite F-R history.
