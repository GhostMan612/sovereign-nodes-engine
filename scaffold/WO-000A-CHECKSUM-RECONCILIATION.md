# WO-000A — Historical ZIP-to-commit checksum reconciliation

- Original shipped ZIP: `SNE-WO-000A-Research-v0.3.0.zip`
- Original manifest: `scaffold/WO-000A-FILE-SHA256.json` (DO NOT OVERWRITE; correctly describes archive bytes)
- User's published, manually whitespace-corrected Git commit: `369722fcd0839447cd5ecf5b78aa1ca7d8e2645c`
- Comparison ledger: `scaffold/WO-000A-COMMITTED-SHA256.json`

## Cause

The original archive contained trailing spaces in 11 Markdown files (24 offending lines total). The operator removed whitespace before committing. Thus the archive-byte manifest (historically correct) no longer matches those edited local/Git blobs. These are **different content states**, not a Git hashing failure.

## How this reconciliation was established

1. Reconstructed all 28 original v0.3.0 ZIP members from the still-available original ZIP.
2. Removed only trailing spaces/tabs in each Markdown line (the operator's recorded correction operation).
3. Computed Git-style blob SHA-1 and SHA-256 for the resulting LF bytes.
4. Cross-checked **all 11 modified entries** against GitHub's blob SHA returned at published `369722f`; **all 11 matched**. Unmodified entries retain the original archive bytes; the complete on-commit file inventory was not re-fetched in a second tool pass.
5. Kept the original package manifest unchanged to preserve package provenance.

## Changed paths (11)

- `WO-000A-INSTALL.md`
- `artifact-chain/evidence/SNE-EVD-000A.md`
- `blueprints/research/SOVEREIGN-NODES-INVENTORY.md`
- `blueprints/research/UPSTREAM-CODE-MAP.md`
- `docs/WO-000A-START-HERE.md`
- `evidence/sources/SNE-SRC-BIASEDDOOM-001.md`
- `evidence/sources/SNE-SRC-CLASSIC-001.md`
- `evidence/sources/SNE-SRC-GAME-001.md`
- `evidence/sources/SNE-SRC-GZDOOM-001.md`
- `evidence/sources/SNE-SRC-UZDOOM-001.md`
- `governance/WO-000A-REVIEW-FINDINGS.md`

## Reliability

The committed-blob SHA-1 for the 11 corrected files matches GitHub's reported blob IDs. SHA-256 values are calculated from the same reconstructed LF-normalized Git bytes, not from the operator's Windows CRLF working copy. The remaining files are reconstructed from the previously shipped ZIP, consistent with the reported commit file list; independent full Git blob verification can be run later.

**Outcome:** Documentation discrepancy reconciled; WO-000A independent research acceptance remains an independent gate.
