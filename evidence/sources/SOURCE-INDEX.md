# Phase 00 — Source and synthesis index v0.7.0

Previous per-work-order pinned source ledgers remain authoritative; WO-E cites their exact upstream observations and reuses pins without claiming fresh builds. One pinned project SHA is the source of truth for each reviewed version.

| Ledger | Description | Source class |
|---|---|---|
| `SNE-REVISION-LEDGER.md` and `SNE-SRC-*-001.md` | WO-A initial upstream/game reconnaissance | SELECTED SOURCE |
| `SNE-SOURCE-PINS-000B.md` and `SNE-SRC-*-002.md` | WO-B model, voxel, scripting, rights | SELECTED SOURCE |
| `SNE-000C-PIN-LEDGER.md` and `SNE-SRC-*-003.md` | WO-C game frame, handoff, levels and glTF | SOURCE/DOC CLAIMS SEPARATED |
| `SNE-000D-PIN-LEDGER.md` and `SNE-SRC-*-004.md` | WO-D CMake, dependencies, Windows build | SOURCE-OBSERVED |
| `SNE-000E-FOUNDATION-PIN-LEDGER.md` | WO-E synthesis and immutable cross-reference | SYNTHESIS, NOT A NEW BUILD |

## Evidence categories

- `SRC`: path and immutable commit prove the **text** being discussed.
- `UPSTREAM-DOC`: upstream author describes a feature, but a runtime proof is still necessary.
- `INFERENCE`: our hypothesis requires falsifiable C-series or device test.
- `RUN`: only a genuine separately authorized run, with exact binaries, fixture hash, logs/trace and signoff.

**Absent as of this packet:** locally measured frame times; actual compiler/configure/build results; C-001…C-015 runtime outputs; complete asset rights; independent review; operator foundation adoption. Refer to `blueprints/research/SNE-000E-EVIDENCE-GAP-MATRIX.md`.
