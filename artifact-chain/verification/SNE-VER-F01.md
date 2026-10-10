# SNE-VER-F01 — Document/ZIP verification vs actual experiment gates

## Package-generation verification checklist

| Check | Required |
|---|---|
| ZIP | opens; central-directory CRC passes; no duplicates/casefold collisions/path traversal |
| Payload | 42 files in `sovereign-nodes-engine/`; Markdown/JSON only; no `.git`, executable, game binary or IWAD |
| Path actions | 37 ADD, 5 REPLACE and each REPLACE preimage matches pinned Git blob at base |
| Bytes | UTF-8 LF, terminal newline, no trailing whitespace or tabs |
| JSON | all examples, request schema and ledgers parse; default request not approved |
| Ledger | SHA-256 for every member excluding self-referential hash file; exact member inventory |
| Installation | PowerShell explicit staging for all 42; operator confirms Git staged `--check` |

## Non-package verification

- User local extraction/staging/push: **PENDING**.
- F-00 independent source review: **NOT SIGNED**.
- F-01 actual authorization: **NOT GRANTED**.
- Native toolchain, fixtures, C-series runtime and UHD 620 performance: **NOT RUN**.
- G1–G8 technical acceptance and ADR: **OPEN/HOLD**.

Passing ZIP validations must never be transcribed into a successful build, source audit approval or developer permission.
