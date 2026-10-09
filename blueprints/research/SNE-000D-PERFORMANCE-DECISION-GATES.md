# WO-000D — Performance acceptance gates and downgrade contract

## Two layers of acceptance

**Layer A—unwaivable correctness:** C-001…C-008 game parity, lawful assets, no ZScript compiler errors, real custom MAP01 marker, synthetic handoff safety and no crashes. **Layer B—operator-configurable performance:** measured P0 legacy viability (proposed 30 FPS minimum, 60 FPS desired) plus declared p95/p99 and 1%-low limits *to be approved before measurement*. Neither layer can substitute for the other.

## Feature ladder (hypothesis, not observed GPU capability)

| Profile | First test requirement | Optional benefits | Automatic safety fallback concept |
|---|---|---|---|
| P0 Legacy | custom source-game parity with original sprites and static sector light | correctness/performance anchor | none; failure blocks candidate |
| P1 Hybrid-Lite | P0 passed, optional one/few voxel actors and 0–2 lights | limited visuals | disable dynamic lights and voxel substitution |
| P2 Hybrid | P1 passed, up to controlled 8-light/model sweep | richer visuals | disable shadows/postFX then revert P1 |
| P3 Experimental | explicit owner opt-in, fixed 16-light and model stress | glTF animation, shadows and PBR where supported | revert P2/P1/P0; never shipped default by paperwork |

## Scoring calculation hold

Do not compute final weighted candidate scores or claim any engine is “faster” until same-scene, same-resolution and backed-by-trace evidence exists for all required production candidates. Record both median-of-runs and worst-run performance; compare scene visuals independently so incorrect/missing renders are not rewarded.

## Coverage distinction

An engine that passes P0 may be a valid compatibility baseline while unsupported glTF makes it unsuitable for future feature goals. An engine that draws fancy glTF but fails C-001 is not suitable even if its frame time is excellent. ZDaemon remains a separate compatibility lane, not a source-engine runtime candidate.

**Decision state:** ALL NOT RUN. Proposal does not establish operator-approved numeric 1%-low or P99 ceilings.
