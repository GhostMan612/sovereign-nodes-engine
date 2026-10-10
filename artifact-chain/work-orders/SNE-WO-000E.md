# SNE-WO-000E — Red-team architecture review and conditional foundation ADR

- Phase: **SNE-P00**; release: **v0.7.0**; parent Git commit: `1f21e4c99da50c83ac0c90d14b2f14a752ae89f4`.
- Scope: **research synthesis, adversarial claim audit, alternatives comparison, independent reviewer handoff and conditional ADR**.
- Status: **AUTHOR REVIEW PREPARED / INDEPENDENT REVIEW PENDING / NO ENGINE CHOSEN**.
- Execution: **read-only upstream assessment and local documentation overlay**, no build, benchmark, game launch, downstream source edit, or remote push.
- Operator controls all approvals. Self-review never satisfies P00-G7.

## Mission and objectives

1. Consolidate A–D's pinned game/upstream source findings without converting reported features into measured PASS results.
2. Challenge incorrect inferences: vanilla-map fallback, sprite naming, JSON handoff, ZScript parity, GLDEFS attachments, glTF build flags, physical seamless streaming, Python trust and license provenance.
3. Define conditional, falsifiable decision rules for **GZDoom**, **UZDoom** and **BiasedDoom**.
4. Preserve a technically credible no-selection outcome and an explicit test-authorization boundary.
5. Set up real independent review and operator decision after the remaining acceptance evidence exists.

## Out of scope

- Forking, copying, building or launching any engine; installing software; reproducing proprietary WADs.
- Editing `GhostMan612/Sovereign-Nodes`, source game ZScript, launchers or the Sovereign Mantle.
- Claiming frame-time measurements, glTF model test results, license clearance or engine selection.
- Accepting earlier work orders simply because they were committed and pushed.

## Inputs

- A `369722f`, B `edc274f`, C `706db57`, D `1f21e4c` published documentation; their individual acceptance files still contain open signoffs.
- Game pin `44034e97fd22129f919a18cadceb84466ef1bcd3`; engine pins and exact source locations in `evidence/sources/SNE-000E-FOUNDATION-PIN-LEDGER.md`.
- 15 compatibility cases `C-001…C-015` and WO-D build/performance test plans, all runtime NOT RUN.

## Deliverables

- Updated `ADR-SNE-002-FOUNDATION-PENDING.md` with HOLD disposition, non-binding conditional lane preference and falsification tests.
- Candidate/risk/claim audit, gate dependencies, prioritized operator experiments, independent review protocol and four blank evidence forms.
- Work-order-specific evidence, reconciliation, verification and acceptance records, archive manifest and SHA-256 ledger.

## Exit criteria (documentation only)

- All A–D claim classes distinguished as SOURCE-OBSERVED, DOC-CLAIM, UNVERIFIED or NOT RUN.
- Non-independent review flagged; independent review required before adoption.
- Each disqualifying condition has test or evidence, owner role and fallback.
- Operator may accept this *documentation packet* without accepting a foundation or opening Phase 01.

## Hard stop

**ADR STATUS MUST REMAIN PENDING.** Candidate score fields stay null until valid measurements and reviewer signoff. Phase 00 and implementation authorization remain open, independent decisions.
