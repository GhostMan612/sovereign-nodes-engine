# WO-F — Blank verification records

These templates contain **no actual run data** and are not a task-execution workflow. Use only after operator authorizes the exact category and a human/test agent collects primary evidence:

- `SNE-000F-AUTHORIZATION.json`: granular signed scope for each category; defaults NOT AUTHORIZED.
- `SNE-000F-CASE-RESULT.json`: one case/engine/fixture with exact artifact identities; defaults NOT RUN.
- `SNE-000F-DEFECT-DISPOSITION.json`: original vs disposable fixture, one-variable causal classification; defaults UNDETERMINED.
- `SNE-000F-REVIEW-RESULT.json`: independent reviewer findings, dissent, evidence pointers; defaults PENDING.
- `SNE-000F-GATE-LEDGER.json`: G1–G8 all OPEN; ADR HOLD, Phase 01 NOT AUTHORIZED.

Use `null` and empty arrays for unknowns; never fabricate pass/fail scores, user identity, measured FPS, binary checksum or authorization. Raw logs and reviewer personal identifiers should remain in private approved storage; public repository includes redacted summaries and hashes only. If form schemas change, version them and add a migration record instead of rewriting historical evidence.
