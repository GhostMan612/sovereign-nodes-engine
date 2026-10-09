# Phase 00 review rubric

**Reviewer:** independent of the evidence author where possible. **Operator:** sole acceptance authority.

| Gate | Must inspect | Failure condition |
|---|---|---|
| G1 Provenance | exact URL, commit pin, relevant source locations | README claims without source revisions |
| G2 Licensing | all component licenses/notices, game-asset rights | unreviewed distribution code or asset |
| G3 Tier-A parity | compile/load/map/actor/light/handoff proofs | silent IWAD fallback, missing script |
| G4 Dependencies | platform+compiler+package pin/build guide | undocumented dependencies |
| G5 Performance | Intel UHD 620 on-device captures | inferred instead of measured values |
| G6 Security | clear game vs Mantle trust boundary, mod execution | private lineage exposure/untrusted Python |
| G7 Independent review | defects, correction records, dissent | self-approved green status |
| G8 ADR | candidate comparison, costs, rollback, owner's signature | engine selection without tradeoffs |

**Status for all gates as shipped:** NOT RUN / NOT ACCEPTED. Completing the scaffold does not close these gates.
