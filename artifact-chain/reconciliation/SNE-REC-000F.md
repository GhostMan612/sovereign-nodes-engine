# SNE-REC-000F — Publication and evidence reconciliation ledger

| Check | State at package creation |
|---|---|
| Published predecessor WO-E | source control commit `1644fb80c3e2803dd19465292423832e8fdf8e24` |
| Required local preimage | exact same SHA, clean before extraction |
| Archive and its file hashes | generated with manifest and SHA-256 ledger |
| New local overlay installed | PENDING OPERATOR |
| Stage/review of full file set | PENDING OPERATOR |
| WO-F Git commit SHA | **UNKNOWN UNTIL USER COMMITS** |
| Remote `main` push | PENDING OPERATOR |
| Independent review | NOT COMPLETED |
| Phase 00 acceptance | OPEN |

## Reconciling an actual published WO-F

After the operator has verified, committed and pushed the ZIP, record the *actual* commit SHA, repository state and any modifications to packaged files in a **new authorized reconciliation update**. Never guess a future SHA or backfill an original historic ledger with fabricated results. The archive checksum applies to bytes in this ZIP, and local CRLF working-tree transformations can differ even when the committed Git blob is equivalent.

## Why this exists

Wo-A historical checksum drift required explicit documentation; WO-F adds immutable preimages and a checksum ledger before installation. A clean Git status is not proof of independent G7 review or of engine execution. Actual user output remains the authority for their local commit/push.
