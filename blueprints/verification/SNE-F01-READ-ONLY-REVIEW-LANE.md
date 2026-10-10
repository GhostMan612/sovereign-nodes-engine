# F-01 — Proposed narrow `AUTH-R` read-only source-review lane

**State: DRAFT FOR OPERATOR DECISION / NOT APPROVED.** This is the recommended first bounded request because F-00 reviewer appointment and critical source validation remain open.

## Proposed objective and permitted sources

A distinct reviewer independently opens and cross-checks all P0 claims `F00-C01…C11` and samples P1 `F00-C12…C16` with independent counterarguments; explicitly investigates whether `tools/validate_pk3.py` is truly missing at the pinned game commit or has another entrypoint. Pinned source repository refs and claim paths are in `blueprints/verification/SNE-F00-CLAIM-CATALOG.md`, `evidence/sources/SNE-F00-PIN-LEDGER.md`.

## Proposed allowlist (requires operator signoff)

- Allowed operations: read exact immutable GitHub file URLs and already published SNE Markdown; compare git blob SHA-1 and line/body; write only sanitized reviewer report after separate approved location selected.
- Prohibited: git source edits, repository PR, branch changes, local host shell, cloned engine source, downloads/executables, live game/fixtures, copyrighted IWAD retrieval, privileged network scopes and real genealogy.
- Evidence: reviewer ID kept privately; sanitized `SUPPORTED/CORRECTED/DISPUTED/UNRESOLVED` per claim, immutable URLs, independently reproduced observations and counterclaims; no automatic G7 PASS.
- Stops: source pin inaccessible, missing reviewer identity, source contradiction, expired approval or unintended write; preserve disputes for operator.

## Completion vs. acceptance

A completed read-only review may improve G1 source credibility and G7 independence if a genuinely separate qualified reviewer signs it and operator accepts its scope. It **cannot** establish G2 asset rights, G3 game parity, G4 build, G5 UHD performance, or G6 runtime handoff security. Missing reviewer remains `PENDING`, not simulated independent verification.
