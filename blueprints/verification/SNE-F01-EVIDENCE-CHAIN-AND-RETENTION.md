# F-01 — Evidence identity, publication and retention

## Each future run record is linked to its actual scope

`authorization_id`, `scope_sha256`, `category`, `task_id`, `operator_signoff_private_ref`, `executor`, `reviewer`, `source_git_shas`, `input_asset_hashes`, `generated_artifact_sha256`, `command_record`, `timestamps`, `result_state`, `raw_evidence_private_ref`, `sanitized_summary_sha256`, `stop_reason`, `retention_policy`, `revocation_id`.

## Proof grades

- `SOURCE-OBSERVED`: immutable source text checked; not a runtime pass.
- `TEST-SPECIFIED`: blueprint with oracles, negative controls; not run.
- `NOT RUN`: no authorized attempt.
- `BLOCKED`: scope not approved, prerequisites or rights absent.
- `INCONCLUSIVE`: authorized attempt yielded inadequate evidence.
- `FAIL`: authorized attempt violated expected oracle with evidence.
- `PASS`: authorized attempt achieved oracle/negative controls, authentic artifacts, reviewed outcome.
- `ACCEPTED`: operator explicitly adjudicates reviewed result/gate; not inferred by Git push.

## Storage/retention

Raw source/game binary, licensed IWAD, full profiler CSV, sensitive directories and actual private operator signatures **must not** be placed in planning repo. Store in an operator-approved private location with a scope-specific retention/erasure policy, redact public summaries before stage. No retention period is invented here: the operator must choose one per permission. The signed private record is referenced using an opaque ID, without making its contents public.

## Artifact immutability

Never overwrite an old evidence row or source pin silently; add superseding ID with old reference and explanation. A later source commit is a new experiment, not retroactive proof for frozen `148dc28`/game `44034e97`. On revoke, preserve necessary private audit trail only to the extent the operator explicitly allowed; stop automated future actions immediately.
