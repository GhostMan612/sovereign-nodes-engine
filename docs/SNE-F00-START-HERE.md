# F-00 / v0.9.0 — Start here

1. **Read** `artifact-chain/work-orders/SNE-WO-F00.md` for exact research limits.
2. **Inspect** `blueprints/verification/SNE-F00-CLAIM-CATALOG.md` and `SNE-F00-PIN-AND-BLOB-CHECKS.md` for the 16 primary-source audit items.
3. **Challenge** sprite loading, handoff boolean/schema behavior, missing validator, CMake feature flags and UZDoom upstream policy; see corresponding source-review blueprints.
4. **Assign** an independent source reviewer using `governance/SNE-F00-REVIEW-ASSIGNMENT.md` and the blank templates. No independent review has occurred merely because these files are created.
5. **Reconcile** actual reviewer disputes in `blueprints/verification/SNE-F00-DISSENT-RESOLUTION.md` and keep G1/G7 open until independently signed.
6. **Proceed only with separate approval** to F-01 or F-02; do not run fixtures, builds, performance tests, or source-game edits under this document.

### Documentation-only publication

`SNE-F00-INSTALL.md` contains exact pre-extraction HEAD, paths and Git blob preimages. This ZIP merges into `C:\sovereign-nodes-engine` when extracted to `C:\`. `scaffold/SNE-F00-MANIFEST.md` lists every intentional ADD/REPLACE; `scaffold/SNE-F00-SHA256.json` hashes every archive member except the ledger itself. Only operator stages, commits and pushes the final local diff.

**Phase 00 technical gates:** OPEN. `ADR-SNE-002`: HOLD. GZDoom-first remains only a proposed control testing order.
