# SNE-WO-000B — Research overlay v0.4.0

- Target repository: `C:\sovereign-nodes-engine`
- Extraction destination: `C:\` (archive already has `sovereign-nodes-engine/`)
- Required published base: `main` at `369722fcd0839447cd5ecf5b78aa1ca7d8e2645c` (`369722f`)
- Scope: Markdown/JSON research and documentation only; **NO engine code, build outputs, `.git`, IWADs, or changes to GitHub**
- Author/reviewer: ChatGPT (first-pass review only; independent acceptance NOT MET)

## Installation safeguards

1. In `C:\sovereign-nodes-engine`, confirm `git rev-parse HEAD` matches the base above and `git status --short` is empty. **Stop on a dirty tree or unexpected HEAD.**
2. Make a backup of any locally customized file listed as REPLACE in `scaffold/WO-000B-MANIFEST.md`. Every replacement includes its expected preimage Git blob SHA-1 so it can be independently compared.
3. Extract this ZIP into `C:\`. Do not extract into `C:\sovereign-nodes-engine` or a doubled subdirectory will result.
4. Review `git diff` and `git status --short`; run `git diff --check`, and stage only manifest-listed paths (no `git add -A` or `git add .`).
5. Run `git diff --cached --check` after staging. Confirm the count and scope before manually committing and pushing.
6. Do not label the engine audit/Phase 00 ACCEPTED on the basis of documentation. The verification records list unfinished work.

## Delivery contents

- Technical source audits for GZDoom, UZDoom, BiasedDoom, engine extension seam map, dependency/license register, build and compatibility risk analysis.
- Curated source evidence with immutable commit links; no copied third-party source code.
- Updated WO-000B work order, research queue, indices and review records.
- WO-000A checksum reconciliation anchored to GitHub commit `369722f` without rewriting the historical ZIP's original checksum manifest.
- An overlay file manifest and SHA-256 ledger whose hashes describe the exact bytes **inside this ZIP**.

## Non-goals

No foundation selection, no fork, no compile, no runtime verification, no new engine subsystem, no benchmark assertion, no private family genealogy, no upstream pull request.
