# WO-F — Source and test evidence register after F-00 packet preparation

Historical results remain blank until independent reviewer/operator or real future tester attaches evidence. The F-00 author source recheck is **not** a completed independent review.

| ID | Scope | Evidence pointer | State | Independent review / operator |
|---|---|---|---|---|
| F-R001 | sprite and GLDEFS naming risk | `SNE-SRC-GAME-005.md`; `SNE-F00-GAME-PRIMARY-OBSERVATIONS.md` | SOURCE-OBSERVED, GAME NOT RUN | PENDING / PENDING |
| F-R002 | boolean handoff risk | `SNE-SRC-GAME-005.md`; `SNE-F00-HANDOFF-PARSER-REVIEW.md` | SOURCE-OBSERVED, GAME NOT RUN | PENDING / PENDING |
| F-R003 | missing validator reference | `SNE-F00-PK3-VALIDATOR-REVIEW.md` | EXACT PATH LOOKUP FAILED, TREE AUDIT OPEN | PENDING / PENDING |
| F-R004 | original PK3 + lawful IWAD | NONE | NOT CAPTURED | PENDING / PENDING |
| F-R005 | Windows candidate build identity | NONE | NOT RUN | PENDING / PENDING |
| F-R006 | C-001…C-008 original game parity | NONE | NOT RUN | PENDING / PENDING |
| F-R007 | UHD 620 frame-time traces | NONE | NOT RUN | PENDING / PENDING |
| F-R008 | rights, security, transitive SBOM | NONE | NOT CLEARED | PENDING / PENDING |
| F-R009 | independent G1/G7 and gate review | `SNE-F00-CLAIM-CATALOG.md` is author-ready only | NOT COMPLETED | PENDING / PENDING |
| F-R010 | ADR-SNE-002 foundation | NONE | HOLD | PENDING / PENDING |
| F-R011 | F-00 selected source claim author recheck | `SNE-F00-PIN-LEDGER.md`, source observation memos | AUTHOR SOURCE-OBSERVED; NOT G7 | NOT REVIEWED / PENDING |

## Future reviewer attachment discipline

Never overwrite `F-R001…F-R010` as PASS due solely to a checklist or file import. Reviewer attaches signed claim IDs, primary URLs/SHAs, explicit criticism and operator result. Any new C-series runtime result must instead include separately authorized engine binary, lawful original PK3, external IWAD provenance and actual captured logs, and is **not** delivered by this docs ZIP.
