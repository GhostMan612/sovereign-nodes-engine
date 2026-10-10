# F-00 — Audit boundary and trust separation

## Invariants

1. Primary source is a pinned Git blob. A Markdown assertion about that blob is a **claim**, not a reproduced independent finding.
2. `SOURCE-OBSERVED` means file bytes or excerpt inspected. It cannot be promoted to `PASS` for any compiled executable, game behavior, graphics fidelity, or legal clearance.
3. Historical A–F evidence and manifests are append-only history. Record corrections as new issue IDs instead of rewriting already published artifact IDs.
4. The reviewer must be distinct from the research/package author, re-open primary sources, and be able to disagree. A distinct person blindly signing a prefilled answer fails the intent of G7.
5. Operator approves reviewer scope/allowed source access separately; that read-only approval does not authorize local experiments, cloned engine builds or GitHub writes.
6. Reviewers retain full raw inspection locally where permitted; public repository receives curated claims/links/hashes, never private device paths, credentials, IWAD contents or real Mantle records.

## Evidence flow

`F-00 claim register → source bytes at SHA → independent challenge → issue/dissent record → operator response → corrected specification or further test request`.

Where a source claim only supports a **hypothesis**, reviewer closes the *source-language question* but leaves behavior classified `NOT RUN`. Block an ADR if G2–G8 still lack real evidence; the source review is not an excuse to skip runtime tests.

## Out of scope

No direct game/engine source edit, code fork, compiling, dependency bootstrap, runnable fixture execution, local device inventory or test-asset distribution. Author can prepare reviewer checklists and source-backed annotations only.
