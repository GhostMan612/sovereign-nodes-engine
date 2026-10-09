# SNE-REC-000C — Overlay and evidence reconciliation (pending)

- Intended base SHA: `edc274f320cbd891c1f7fcef80f308562c0067ef`
- Source baseline: `scaffold/WO-000C-FILE-SHA256.json` (8 preimage blob SHA-1 entries; 31 ADD paths)
- Source archive: `SNE-WO-000C-Compatibility-Feasibility-v0.5.0.zip`
- Local extraction: NOT OBSERVED
- Staged Git: NOT OBSERVED
- Commit SHA after install: UNKNOWN
- Push: NOT OBSERVED
- Independent review: PENDING

## Reconciliation fields to fill after local operations

| Field | Expected / actual |
|---|---|
| Expected files | 39: 8 REPLACE, 31 ADD |
| Actual `git status --short` | PENDING |
| Actual `git diff --cached --check` | PENDING |
| Actual staged filenames | PENDING |
| Local modifications outside overlay | UNKNOWN — stop if present |
| Source to test mapping | catalog published; engine NOT RUN |
| Operator commit/push evidence | PENDING |

Never change a historical package manifest merely to make the new package appear to pass. Reconcile actual installed bytes if they differ; do not silently trim whitespace after hashing.
