# Artifact chain

Each phase has a unique ID. Use `SNE-INT-###` → `SNE-EVD-###` → `ADR-SNE-###` → `SNE-BP-###` → `SNE-WO-###` → `SNE-VRF-###` → `SNE-ACC-###` → archive record. Links are explicit, not implied. Gate order cannot be skipped. Risk and reconciliation entries can be opened at any stage.

## Gate states
`DRAFT`, `IN_REVIEW`, `BLOCKED`, `APPROVED`, `IN_PROGRESS`, `VERIFIED`, `ACCEPTED`, `REJECTED`, `SUPERSEDED`.

Research findings are not accepted implementation evidence. A builder cannot approve its own work; reviewer must check diffs and test evidence independently, even if the same AI authored the package.
