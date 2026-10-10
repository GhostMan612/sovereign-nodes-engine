# SNE-F01 v1.0.0 — Start here

**Purpose:** define exactly which future experiment an operator can authorize, for whom, on which source/device/path, for how long, with which stop conditions. Nothing in the ZIP grants execution permission.

## Document reading order

1. `artifact-chain/work-orders/SNE-WO-F01.md` — scope and hard limits.
2. `governance/WO-000F-AUTHORIZATION-MATRIX.md` — authorization class boundary.
3. `blueprints/verification/SNE-F01-SCOPE-FREEZE.md` and `SNE-F01-AUTHORIZATION-LIFECYCLE.md` — draft→review→private operator decision→future dispatch.
4. `blueprints/verification/SNE-F01-READ-ONLY-REVIEW-LANE.md` — proposed first `AUTH-R` for external F-00 source reviewer.
5. `blueprints/verification/SNE-F01-HOST-INVENTORY-LANE.md` — independently scoped metadata-only Windows inventory option, still unapproved.
6. `blueprints/verification/SNE-F01-F02-ENTRY-GATE.md` — evidence prerequisites before disposable fixture/run/build/bench.
7. `templates/SNE-F01-README.md` — blank forms (all `PROPOSED`, not operator decisions).
8. `SNE-F01-INSTALL.md` — the 42-file exact overwrite and PowerShell verification plan.

## Live hold

`ADR-SNE-002`: HOLD. No real F-00 reviewer signature; no authorized local commands, device inventory, engine test, dependency installation, game code changes, legal asset release, or source fork. If operator requests the first live task, begin with a **new** single-category request and obtain genuine explicit approval outside these documents.
