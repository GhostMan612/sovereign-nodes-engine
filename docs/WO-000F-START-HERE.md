# START HERE — SNE-WO-000F Evidence Closure Readiness v0.8.0

## What this package does

Converts the Phase 00 A–E source research into future operator-run, auditable experiments and reviewer decisions. Contains **only Markdown and JSON**. `ADR-SNE-002` remains HOLD; no executable engine has been assembled or tested here.

## Read sequence

1. `WO-000F-INSTALL.md` — required Git baseline, backup/overwrite checks and explicitly scoped staging paths.
2. `artifact-chain/work-orders/SNE-WO-000F.md` — delivery boundaries and acceptance criteria.
3. `blueprints/verification/SNE-000F-SUBWORKORDER-ORDER.md` — sequencing and discrete approval requirements.
4. `blueprints/verification/SNE-000F-CASE-TO-GATE-TRACE.md` and `SNE-000F-RESULT-SEMANTICS.md` — complete proof map and truthful test status handling.
5. `SNE-000F-SPRITE-TESTS.md`, `SNE-000F-HANDOFF-TESTS.md`, `SNE-000F-PK3-AND-WAD-GATES.md` — baseline content verification before blaming engines.
6. `governance/WO-000F-AUTHORIZATION-MATRIX.md` and `WO-000F-INDEPENDENT-REVIEW-HANDOFF.md` — permissions and review.
7. `scaffold/WO-000F-MANIFEST.md` and checksum ledger — file and preimage checks.

## Do not run this work now

This ZIP *specifies* commands/conditions for future operator-approved verification, but neither extracts, installs dependencies, builds a source port, runs a game, changes the source-game repo, accesses an IWAD or performs benchmarks. No existing game or engine files are packaged.

## Initial operator checkpoint

Confirm clean `C:\sovereign-nodes-engine` at `1644fb80c3e2803dd19465292423832e8fdf8e24`. Extract ZIP **into `C:\`**; archive root is `sovereign-nodes-engine/`. Inspect 6 REPLACE paths carefully; stage only the explicitly listed files. Full staged counts appear in manifest; `git diff --cached --check` must pass. Publication remains manual.

## After commit

An independent reviewer must validate primary source claims and gate methodology before any game/device/build test is authorized. Evidence is deliberately unpopulated. Zero measured performance claims or assumed engine compatibility results are provided.
