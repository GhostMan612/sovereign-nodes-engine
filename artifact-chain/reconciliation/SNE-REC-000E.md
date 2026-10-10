# SNE-REC-000E — Baseline and release reconciliation

- Expected base commit: `1f21e4c99da50c83ac0c90d14b2f14a752ae89f4`.
- Previous: WO-A `369722f`; WO-B `edc274f`; WO-C `706db57`; WO-D `1f21e4c`.
- Intentional scope: eight full-file documentation replacements and 40 documentation/JSON additions; no deletes, executable code, game assets, private records or `.git`.
- Existing A–D acceptance records remain historically open; WO-E does not overwrite them or claim independent signoff.
- 2026-10-09 source and reviews are time-scoped; pin refresh required before operator-approved execution.

## Operator checks required before merge

1. Run `git rev-parse HEAD`; it must exactly equal the base commit. Run `git status --short`; it must be empty **before extraction**.
2. Compare each replacement preimage via `git rev-parse HEAD:<repo-relative-path>` against `scaffold/WO-000E-FILE-SHA256.json`; abort if any discrepancy. Do not extract on dirty tree.
3. Extract `sovereign-nodes-engine/` archive root into `C:\` (not into project directory). Review all new and changed files.
4. Explicit stage 48 paths; staged check must pass. Publish manually if satisfactory.
5. Record actual new commit hash in registry only after publication; status stays review-pending until independent technical evidence arrives.

## Rollback

Stop before overwrite when uncertain; preserve local changes. Do not force-push or delete unrelated work. If operator intentionally reverses a published doc commit, inspect and use a normal non-destructive Git revert with proper review.
