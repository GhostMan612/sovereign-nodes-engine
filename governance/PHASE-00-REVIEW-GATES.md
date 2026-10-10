# Phase 00 — Acceptance and permission gates after WO-F / F-00

**State:** Published A–F plans; F-00 independent source reviewer packet authored, **not independently reviewed or operator-accepted**. `ADR-SNE-002` HOLD. Signing or installing a Markdown package is not a test outcome.

| Gate | Required real evidence | Present state | What F-00 contributes |
|---|---|---|---|
| P00-G1 Provenance | independent primary-source URL@SHA/blob/line, checked counterclaim and path resolution | SELECTED AUTHOR-SOURCE; INDEPENDENT PENDING | 16-item source claim catalog, pin ledger |
| P00-G2 Rights | full transitive code/asset/branding/source distribution SBOM, legal review and lawful external IWAD | NOT CLEARED | upstream policy claims and gaps only |
| P00-G3 Parity | C-001…C-008 on unchanged original game, correct GapNode, actor/GLDEFS/HUD/negative controls | NOT RUN | source-risk falsification, not parity |
| P00-G4 Build | exact Windows toolchain, dependencies, native binary/config/resource SHA and repeatability | NOT RUN | root CMake claim audit, not compiled |
| P00-G5 UHD 620 | >=3 valid actual P0 traces per scene and operator-approved thresholds | NOT RUN | no device access or measurements |
| P00-G6 Security | synthetic JSON truth table/replay/schema/path safety, optional CPython and Mantle separation | NOT TESTED | source parse questions only |
| P00-G7 Independence | distinct reviewer inspects primary source and tests, retains dissent, operator reconciliation | NOT COMPLETED | appointment and blank reviewer protocol |
| P00-G8 Foundation | all relevant approved evidence, score and explicit operator engine SHA/rollback | HOLD | no engine adoption or Phase 01 approval |

## Approval categories remain independent

`AUTH-R` reviewer read-only source; `AUTH-H` host inventory; `AUTH-F` disposable fixture; `AUTH-B` build; `AUTH-T` parity runtime; `AUTH-P` GPU measurement; `AUTH-S` rights/security; `AUTH-I` implementation; `AUTH-D` redistribution. All categories that access user's computer, build, test or modify code default **NOT GRANTED** unless user separately signs. The current overlay is document preparation and author source inspection, **not an AUTH-R signoff for a third-party reviewer**.

## Truth/status enforcement

- Source observed ≠ independent accepted; test specified ≠ passed; absent permission/resource ≠ engine failure.
- Reviewer must reconstruct evidence; signoff must be dated, scoped and distinct from author; dissent and conflicting evidence preserved.
- Any claimed runtime PASS requires actual binary and fixture hashes, exact lawful resources, real logs/trace and independent scrutiny.
- Unresolved validator-path question, sprite naming and `hasParadox` source mismatch remain risks, not known runtime defects.
- Operator may accept **documentation** without closing any technical gate. Full Phase 00 and Phase 01 remain separate authorizations.

See `governance/SNE-F00-REVIEW-ASSIGNMENT.md`, `SNE-F00-CONFLICT-OF-INTEREST.md`, `blueprints/verification/SNE-F00-GATE-IMPACT.md` and the existing `SNE-000F-*` workstream blueprints.
