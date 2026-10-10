# SNE-VER-F03 — Documentary package verification limits

The package builder checks safe ZIP member paths with single `sovereign-nodes-engine/` prefix; manifest count and ADD/REPLACE actions; no duplicate paths or directory traversal; file CRC; per-member SHA-256 with deliberate self-ledger exclusion; UTF-8 LF and no trailing whitespace; and JSON parsing. GitHub fetched original tracked-document blob SHA-1 values form the replacement preimage guard.

**No user device validation, local Git diff, external independent review, compiler, SDK, resource renderer or C-series test can be claimed here.** Operator must run `git status --short`, validate exact HEAD, inspect staged diff, and verify all files before manually committing.

Tool output `VALIDATED_DOC_ZIP` (see `scaffold/SNE-F03-BUILD-VERIFICATION.json`) is exclusively an archive-format check. `P00-G4` and `ADR-SNE-002` remain unresolved.
