# F-02 — F-03 and F-04 future entry conditions

**Do not create another implementation order until the operator supplies real evidence and a new explicit scope.**

| Downstream work | Minimum legitimate evidence | Pending blockers now |
|---|---|---|
| F-03 native GZDoom Windows build | approved AUTH-B, exact source SHA, Windows toolchain/SDK inventory, vetted dependency manifest, isolated output location | no installed-tool data; approval absent |
| F-04 original-game C-001..C-008 | approved AUTH-T, lawful external IWAD, original B0 PK3 SHA, candidate binary hash, custom GapNode identity and negative control | B0/binary not captured, no run |
| F-05 UHD 620 P0 benchmark | per-candidate accepted P0 actual parity, AUTH-P, ≥3 real frame traces/scene, pre-registered thresholds | all NOT RUN |
| F-06 source/licensing/security | qualified independent reviewer and AUTH-S for chosen data sources | transitive SBOM/rights not cleared |
| F-07 ADR foundation | G1–G7 evidence and owner signature, alternatives/rollback | ADR-SNE-002 HOLD |

Until a signer explicitly authorizes an experimental category, the next useful action is to request a *narrow* signed AUTH-R or AUTH-H, not generate purported test results. GZDoom-first is a **proposed control order** only, not foundation selection.
