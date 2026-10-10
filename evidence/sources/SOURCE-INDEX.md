# SNE-P00 — Source index v0.8.0

All historical WO-A…WO-E source records retain their original pinned scope; no historical checksum or source memo is overwritten by this overlay. Research findings cite source text, not native gameplay success.

| Ledger | Scope | Classification |
|---|---|---|
| `SNE-REVISION-LEDGER.md`, `SNE-SRC-*-001.md` | Initial research | SELECTED PINNED TEXT |
| `SNE-SOURCE-PINS-000B.md`, `SNE-SRC-*-002.md` | Candidate engine code paths | SELECTED PINNED TEXT |
| `SNE-000C-PIN-LEDGER.md`, `SNE-SRC-*-003.md` | Game sprite, handoff, lighting and model concerns | SOURCE/DOC/INFERENCE SPLIT |
| `SNE-000D-PIN-LEDGER.md`, `SNE-SRC-*-004.md` | Build and package manifests | SELECTED SOURCE |
| `SNE-000E-FOUNDATION-PIN-LEDGER.md` | A–D red-team synthesis | SYNTHESIS ONLY |
| `SNE-000F-SOURCE-SNAPSHOT.md` | Published SNE baseline `1644fb8`, game and upstream source pins | PINNED DOCUMENT AND SOURCE |
| `SNE-SRC-GAME-005.md` | Game MAPINFO, GLDEFS, handoff, build packaging and validator-path discrepancy | SOURCE CHECK / RUNTIME NOT RUN |

## Classification discipline

- `SOURCE-OBSERVED`: content from immutable commit and path was inspected; does not imply correct behavior.
- `UPSTREAM-DOC`: claim from upstream documentation; validate before depending on it.
- `INFERENCE`: source-based risk or hypothesis, test needed.
- `TEST-SPECIFIED`: precise setup/oracle/negative control, no execution.
- `RUN`: only separately authorized local run with hashes, real logs/trace and tester signoff.

**No author of WO-F recorded local MSVC setup, engine build, game launch, frame trace, license clearance or independent reviewer approval.** `ADR-SNE-002` remains HOLD.
