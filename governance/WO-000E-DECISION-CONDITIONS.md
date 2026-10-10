# WO-E — Foundation ADR conditions and non-waivable holds

## Author recommendation

Recommend **GZDoom first as test control, UZDoom as parallel comparator and BiasedDoom as optional glTF technology probe**. Recommend **NO FOUNDATION SELECTED** now.

## Non-waivable present holds

- No independent G7 reviewer; no operator acceptance of A–E documentation chain.
- No source-game runtime C-001–C-008 PASS on any candidate.
- No native target Windows engine builds and no target UHD 620 benchmark.
- No full license/asset provenance and release/distribution clearance.
- Source-game sprite/GLDEFS and handoff boolean behavior unresolved; private/Mantle security boundary untested.

## Decision tree

1. Missing any mandatory hard evidence → **HOLD**.
2. Evidence invalid because original game fixture fails independent of candidate → open separately authorized game-content repair assessment; never call fork incompatible automatically.
3. Candidate passes core parity but misses optional rendering → designate only P0/P1 scope conditionally, measured per operator thresholds.
4. Candidate passes functionality but fails legal/security gate → REJECT production/adoption until resolved, even if high FPS.
5. Candidate passes all evidence, reviewer objections resolved, operator explicitly chooses → adopt pinned ADR; then **separately** authorize Phase 01 source/engine implementation.

## Decision packet signature fields

Operator identity/signature/date, reviewer identity/findings, chosen URL/SHA, accepted profile level, evidence IDs, recognized exclusions, rights analysis, update responsibility, rollback target and source-modification scope. All **PENDING** at v0.7.0.
