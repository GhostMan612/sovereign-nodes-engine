# WO-E — Evidence-gated foundation scorecard (BLANK)

## Gate-first scoring

Do not calculate or publish a weighted rank until each production candidate has been tested against actual Sovereign Nodes FPS and measured under comparable settings. A failed hard gate is **BLOCK**, not a 0–100 score to average away.

| Gate | GZDoom | UZDoom | BiasedDoom |
|---|---|---|---|
| Legal/asset clearance | PENDING | PENDING | PENDING |
| C-001..C-008 compatibility | NOT RUN | NOT RUN | NOT RUN |
| Windows build reproducibility | NOT RUN | NOT RUN | NOT RUN |
| UHD 620 P0 + frame trace | NOT RUN | NOT RUN | NOT RUN |
| Security and independent review | PENDING | PENDING | PENDING |
| Result | **NOT SCORED** | **NOT SCORED** | **NOT SCORED** |

## Conditional weighted score (only after gates)

| Dimension | Weight | Evidence requirement |
|---|---|---|
| P0/Tier-A exact game correctness | 30% | C-001–C-008 logs plus negative controls and persistence |
| Windows build and maintainability | 20% | reproducible build, patches/conflicts, package provenance |
| UHD 620 measured performance | 15% | three-run 720p fixed scene traces, 1% low/p99/power |
| Modern model/lighting extensibility | 15% | actor-preserving voxel, optional glTF/GLB, fallback |
| Licensing, source policy and distribution | 10% | independently approved SBOM and sustainable collaboration route |
| Logical world continuity, handoff and safety | 10% | C-009/C-015, synthetic-only boundary and model |

Each dimension must have a declared normalization rubric and evidence IDs **before** scoring. No fabricated counts, FPS, benchmark links, rates or toolchain successes permitted. Operator may retain HOLD despite a numerical preference.

## Score entry record template

Use `templates/SNE-000E-ADR-VOTE.json` with per-dimension numbers left `null` until reviewer validates evidence. Scores derived from abstract checklists or marketing bullet points are forbidden.
