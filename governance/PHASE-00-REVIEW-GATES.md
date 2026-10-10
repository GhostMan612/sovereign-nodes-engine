# PHASE-00 — Independent acceptance, technical and authorization gates

A published document is not independently accepted research. A planning ZIP does not confer permission to perform tests or alter any source repository. Operator owns decisions; independent reviewer cannot be the author of the underlying research packet.

| Gate | Minimum legitimate evidence | State at WO-000F authoring | Failure / stop |
|---|---|---|---|
| P00-G1 Provenance | current immutable source URLs/SHA, blob matches and reviewer-checked high-risk symbols | SELECTED SOURCES PINNED; INDEPENDENT CHECK OPEN | stale source or inferred runtime result |
| P00-G2 Rights | full code/dependency/brand/resource notice inventory, lawful IWAD provenance, distribution clearance | PARTIAL / NOT CLEARED | owned/third-party rights unknown |
| P00-G3 Parity | C-001…C-008 unchanged PK3 per production candidate, observed actor/HUD/map markers, negative controls | NOT RUN | vanilla Entryway mistaken for custom GapNode |
| P00-G4 Build | operator-validated Windows toolchain + one or more candidate builds with flags, paths, hashes, resource package and reproducibility record | NOT RUN | unknown ABI/build provenance |
| P00-G5 Performance | actual UHD 620 >=3 trace-backed comparable P0 runs per accepted scene, p95/p99/1% low and approved thresholds | NOT RUN | FPS guessed, scene differs, VSync unknown |
| P00-G6 Security | synthetic handoff true/false, invalid schema, replay/path checks; Python trust and Mantle separation review | NOT TESTED | private Mantle leak, untrusted code executes |
| P00-G7 Independence | named separate reviewer, primary-source check, dissent, resolution evidence | NOT COMPLETED | author self-certifies |
| P00-G8 Decision | G1–G7 closure plus scorecard with actual evidence, operator signed engine SHA/rollback and explicit Phase 01 boundary | **HOLD** | implied choice from preferred testing order |

## Work-category approval (separate from gates)

| Approval category | Defaults | May authorize |
|---|---|---|
| Read-only repo research | documentation only | source inspection; no local device work |
| Local environment inventory | NOT GRANTED | non-invasive metadata capture on approved host only |
| Disposable synthetic fixture | NOT GRANTED | copies in isolated allowed workspace; original source unchanged |
| Native engine build | NOT GRANTED | exact engine SHA/flags/dependency location, no system installer |
| Local runtime / GPU benchmark | NOT GRANTED | exact binary and fixtures, lawful game data, raw trace storage |
| Source-game / engine implementation | NOT GRANTED | separately scoped Phase 01 or authorized repair WO |
| Redistribution or upstream submission | NOT GRANTED | independent asset/licensing/policy review; distinct authorization |

These categories do not inherit each other's approval. A `PASS` requires a real run artifact, signed scope and independent quality check. `BLOCKED` is different from `FAIL`: missing permission, tool or legal asset means `BLOCKED`, not a negative engine result.

## Legitimate closure workflow

1. Classify evidence as `SOURCE-OBSERVED`, `UPSTREAM-DOC`, `TEST-SPECIFIED`, `NOT RUN`, `BLOCKED`, `PASS`, `FAIL` or `UNVERIFIED` with exact evidence pointers.
2. Record fixture/control IDs, model/system hashes, operator/tester identity, commands and raw logs retained off-repo; only sanitized summaries and checksums enter the planning repo.
3. An independent reviewer checks sampling, controls, unexplained variation and any requested waiver; reviewer disagreements remain visible.
4. Operator accepts or rejects each gate with explicit date and risk rationale. Hard legal/security/core-parity and independence obligations cannot be silently waived.
5. Only then update ADR-SNE-002 from HOLD and independently request authorization for Phase 01.

See `governance/WO-000F-AUTHORIZATION-MATRIX.md`, `blueprints/verification/SNE-000F-RESULT-SEMANTICS.md` and `templates/SNE-000F-GATE-LEDGER.json`.
