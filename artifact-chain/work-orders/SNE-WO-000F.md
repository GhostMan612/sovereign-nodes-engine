# SNE-WO-000F — Evidence Closure and Verification Readiness

- Phase: `SNE-P00`; release: `v0.8.0`; required clean pre-extraction base: `1644fb80c3e2803dd19465292423832e8fdf8e24`.
- State: **DOCUMENTATION-ONLY WORK PACKAGE PREPARED / INDEPENDENT REVIEW PENDING / NO LOCAL EXECUTION AUTHORIZED**.
- Operator owns actual Git staging, commit/push, repository, experiments, and all prospective changes.
- Existing `ADR-SNE-002`: **HOLD**. GZDoom is merely the proposed first control lane.

## Mission

Turn the open findings of WO-A…WO-E into traceable, bounded evidence-collection tasks, each with a control, failure oracle, responsible role, artifact identity, and explicit authorization request. Do **not** run them during WO-F preparation or ZIP installation.

## Inputs and evidence classes

- A `369722f`; B `edc274f`; C `706db57`; D `1f21e4c`; E `1644fb8` (documentation published, acceptance pending).
- Pinned game `44034e97fd22129f919a18cadceb84466ef1bcd3`; upstream engine source pins in `evidence/sources/SNE-000F-SOURCE-SNAPSHOT.md`.
- `SNE-000C-TEST-CASE-CATALOG.md`: 15 game/renderer/security cases, all unexecuted.
- `SNE-000D-REPRO-BUILD-COMMANDS.md` and `HARDWARE-BENCHMARK-PLAN.md`: prospective procedures only.
- `SNE-000E-EVIDENCE-GAP-MATRIX.md`: source-derived unresolved blockers; updated as a readiness crosswalk, not as closed findings.

## Ordered readiness workstreams

| ID | Objective | Deliverable | Operator gate |
|---|---|---|---|
| F-00 | Independently inspect source statements and stale validator path | signed defect/reviewer record | read-only review approval |
| F-01 | Collect discrete host/fixture/build/test scopes | signed authorization record with paths/date | **every execution scope isolated** |
| F-02 | Validate actual game PK3/WAD baseline and disposable sprite/boolean controls | source-vs-engine defect classification | separately approved synthetic fixture execution |
| F-03 | Capture Windows build prerequisites before any native build | host/toolchain/dependency identity | separately approved inventory/build |
| F-04 | Run C-001…C-008 per pinned candidate | hash-tied result log plus negative controls | separately approved operator runtime |
| F-05 | Compare UHD 620 P0 and optional model/light profiles | real frame trace and variance report | separately approved benchmark |
| F-06 | Independently complete rights, supply chain, security and maintenance review | signed SBOM/security record | reviewer and any testing authorization |
| F-07 | Reconcile independently verified gate results and operator choices | signed G1–G8 ledger; ADR still conditional | operator acceptance |

## Acceptance for this *documentation* work order

- Every C-001…C-015 and G1–G8 has a future evidence owner, case identity and a stable failure/hold status.
- Open sprite naming, `hasParadox`, MAPINFO fallback and missing validator reference are recorded as **unverified risks**.
- No authorization is inferred from an example, template, checklist or acceptance of documentation.
- No false statuses, mock benchmarking numbers, claims of independent signoff, engine selection or Phase 01 approval.
- Exact manifest actions, Git preimage SHA-1, content SHA-256, JSON/ZIP safety checks and rollback instructions included.

## Exclusions

No source game edits, engine/source fork, build, binary, native run, GPU probe, auto-download, shell execution on user's PC, commercial IWAD inclusion, real genealogy, Mantle vault access, network communications, GitHub mutation or upstream PR. Retain evidence summaries only, not gauntlet/conversation transcripts.

## Stop / recovery

If any operator preimage differs, a new path already exists, repo dirty conflicts with overlay, or evidence would leak personal information: **STOP**. Inspect a manual diff rather than mass overwrite, force reset, or staging the entire repo. Existing independent-review requirement is non-negotiable.

**Completion of WO-F planning does not close Phase 00.**
