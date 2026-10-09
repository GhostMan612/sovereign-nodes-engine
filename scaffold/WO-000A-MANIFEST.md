# SNE v0.3.0 — WO-000A explicit overlay manifest

- **ZIP prefix:** `sovereign-nodes-engine/` (extract to `C:\`)
- **Expected baseline:** `GhostMan612/sovereign-nodes-engine@317e360c041ce3e02dbef7634085cf687f84c02b`
- **Contents:** only documentation / Markdown and a JSON checksum ledger.
- **Git:** `.git/` not included. No automatic delete/move. Does not include `AGENTS.md`, gameplay assets or implementation.
- **Safety:** Existing file modifications are overwritten on ZIP extraction; compare baseline blob SHA and `git diff` first. Added paths colliding with local files are **CONFLICTS** until operator review.

## Explicit actions

| Action | Path | Expected old Git blob (REPLACE only) |
|---|---|---|
| ADD | `WO-000A-INSTALL.md` | — |
| ADD | `artifact-chain/acceptance/SNE-ACC-000A.md` | — |
| ADD | `artifact-chain/evidence/SNE-EVD-000A.md` | — |
| ADD | `artifact-chain/reconciliation/SNE-REC-000A.md` | — |
| ADD | `artifact-chain/verification/SNE-VER-000A.md` | — |
| REPLACE | `artifact-chain/work-orders/SNE-WO-000A.md` | `b7988eedaaf3949f741d7b834c955ca05e5f91bc` |
| ADD | `blueprints/architecture/SNE-RESEARCH-ARCH-000A.md` | — |
| ADD | `blueprints/diagrams/SNE-000A-RESEARCH-FLOW.md` | — |
| REPLACE | `blueprints/research/CANDIDATE-MATRIX.md` | `ac391793994a99161cef86f5f2bb8dfff9192151` |
| REPLACE | `blueprints/research/RESEARCH-QUEUE.md` | `9ace412929b4a6f73e43a120fe6332e8466ad85b` |
| ADD | `blueprints/research/SNE-000A-RESEARCH-GAPS.md` | — |
| ADD | `blueprints/research/SNE-000A-REUSE-VS-REWRITE.md` | — |
| ADD | `blueprints/research/SNE-000A-TIER-A-COMPAT.md` | — |
| REPLACE | `blueprints/research/SOVEREIGN-NODES-INVENTORY.md` | `52f110b4ff4631029fff17fafe49f4684cdd6aeb` |
| REPLACE | `blueprints/research/UPSTREAM-CODE-MAP.md` | `0a90213d08a6e02d51b4e8129ee848f6ded7b50e` |
| ADD | `docs/WO-000A-START-HERE.md` | — |
| ADD | `evidence/sources/SNE-REVISION-LEDGER.md` | — |
| ADD | `evidence/sources/SNE-SRC-BIASEDDOOM-001.md` | — |
| ADD | `evidence/sources/SNE-SRC-CLASSIC-001.md` | — |
| ADD | `evidence/sources/SNE-SRC-GAME-001.md` | — |
| ADD | `evidence/sources/SNE-SRC-GZDOOM-001.md` | — |
| ADD | `evidence/sources/SNE-SRC-UZDOOM-001.md` | — |
| REPLACE | `evidence/sources/SOURCE-INDEX.md` | `2893c6732c7cec04078a7870e88c7b256f204129` |
| ADD | `governance/WO-000A-REVIEW-FINDINGS.md` | — |
| REPLACE | `registry/PHASE-00-ARTIFACT-INDEX.md` | `e4a6ad7c6a0c219afb4ab2f42582552235fbf04e` |
| ADD | `scaffold/WO-000A-CHANGELOG.md` | — |
| ADD | `scaffold/WO-000A-MANIFEST.md` | — |
| ADD | `scaffold/WO-000A-FILE-SHA256.json` | — |

## Overwrite guard

If the target repo has changed from the expected baseline or any listed REPLACE file differs from the expected Git blob, stop and reconcile; do not silently overwrite operator changes. This is an **overwrite overlay**, not a destructive synchronization; files not listed in the manifest must remain untouched.

## Verification protocol

1. Check archive prefix and JSON SHA-256 records before extraction when possible.
2. Review `git status --short` and scoped `git diff --check` after extraction.
3. Confirm only the manifest paths changed; investigate unexpected modifications.
4. Stage only operator-approved files, by explicit paths. Commit and push manually.
5. Do not conflate a successful push with research review acceptance or engine runtime PASS.
