# F-00 — Evidence chain, citations and conflict management

## Immutable chain

Each claim links `claim ID → source repo@commit → file path → Git blob SHA → line span → author observation → separate reviewer observation → dissent → operator disposition → downstream affected gate`. Never point a supposed proof only at an earlier blueprint: circular documents are not independent evidence.

## Artifact ownership

- **Published in repo:** sanitized source citations, claim IDs, selected line references, issue summary, gate impact and reviewer ID pseudonym.
- **Kept private/off-repo:** signatures and reviewer contact, raw case logs, any licensed game data, real genealogy, credentials, full system user paths, archive copies, source-dependent security findings requiring disclosure controls.
- **Not yet collected:** actual source-generated PK3 hashes, engine binary hashes, lawful IWAD fingerprints, test trace data, installed device driver and compiler details.

## Correction protocol

1. Append issue ID (e.g. `F00-ISS-001`) identifying incorrect previous claim and file, exact source counterexample, severity and observed limitation.
2. Reference it in a future revised blueprint, retaining historic artifact identity and Git history.
3. Reviewer marks issue `OPEN`, `SUPPORTED`, `DISPUTED`, `REQUIRES_RUNTIME` or `RESOLVED_WITH_EVIDENCE`; do not set an outcome until work performed.
4. Operator explicitly approves corrective documentation or authorizes a future separate execution work order.
5. Never regenerate old commit/package checksum ledgers to pretend the old archive was different.

## Cryptographic caveat

A Git blob SHA-1 identifies file contents in a Git repository but is **not** a digital signature of author trust, legal clearance, or runtime correctness. Archive member SHA-256 verifies ZIP contents only; it does not certify upstream correctness or independent review.
