# SNE-VER-F00 — Publication/package verification scope

## Generation-level controls

1. ZIP central directory/CRC integrity and no duplicate/case-insensitive collision.
2. Every member under `sovereign-nodes-engine/`; no traversal, scripts, binaries, WADs, IWADs, engine code, .git entries or symlinks.
3. File action manifest exact: new files all ADD, six source-backed REPLACEs have the expected frozen Git blob SHA-1s.
4. All Markdown/JSON files decode as UTF-8, use LF, end in newline and contain no trailing whitespace.
5. Every JSON file parses. Archive member SHA-256 verified against ledger except the ledger itself to avoid recursion.
6. All original source pins, review result states and author independence disclaimer cross-checked for logical consistency.

## Explicit non-results

- **NOT RUN:** independent reviewer audit, source game validation script, actual game launch, native engine compile, Windows environment inventory, GPU benchmark, official IWAD license check, transitive SBOM and security tests.
- **NOT ACCEPTED:** Phase 00 G1–G8 or ADR-SNE-002 foundation.

## Local operator checks after extraction

Run `git status --short`, `git diff --check` (tracked changes only), explicit-path `git add -- ...`, `git diff --cached --check`, `git diff --cached --stat`, `git diff --cached --name-only` and inspect the full staged diff before committing. A clean check is only documentation hygiene.
