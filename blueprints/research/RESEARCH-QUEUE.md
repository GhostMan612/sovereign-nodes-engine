# SNE Phase 00 research queue — v0.4.0

Date: 2026-10-09. Research statuses distinguish source observations, full audits, operator benchmarks and independent acceptance.

| ID | Priority | Research question | Status | Next action |
|---|---|---|---|---|
| R00-01 | P0 | Pin upstream/source revisions | SOURCE-COMPLETE FOR AUDITED REVISIONS | refresh when selecting release/branch |
| R00-02 | P0 | Current Doom gameplay interfaces | SOURCE-PARTIAL | exhaustive map and classes/validator coverage, game test |
| R00-03 | P0 | GPL + all per-file/assets and dependencies | PARTIAL | enumerate bundled asset notices and full SBOM |
| R00-04 | P0 | Actual ZScript/MAPINFO compatibility | NOT RUN | target-machine Tier-A fixtures |
| R00-05 | P0 | UZDoom policy and C++ toolchain | SOURCE-PARTIAL | record build, legal and downstream maintenance decision |
| R00-06 | P1 | Voxel/GLDEFS/glTF source seams | SELECTED SOURCES VERIFIED | full registration call graph; BiasedDoom GLB proof |
| R00-07 | P1 | Intel UHD 620 graphics benchmark | NOT RUN | separate operator-authorized test work order |
| R00-08 | P1 | Hub state / world continuity | SOURCE-PARTIAL | practical persistence tests, streaming gap |
| R00-09 | P0 | Handoff and optional Mantle bridge security | SOURCE-PARTIAL | test JSON boolean `hasParadox`, no real data, snapshot threats |
| R00-10 | P1 | Fork update/merge maintenance cost | PROPOSAL ONLY | pinned diffs, patch series and CI effort |
| R00-11 | P0 | WP-000A checksum discrepancy | RECONCILED IN DOCS | inspect committed-source hash report; do not rewrite package manifest |
| R00-12 | P1 | BiasedDoom conditional glTF/runtime registration | OPEN | inspect CMake macro mappings and actual plugin registration |
| R00-13 | P1 | UZDoom/C++20 Windows build dependencies | OPEN | planned reproducible build env and operator approval |

**Gate:** Source observed != compiled != played != accepted. WO-000B does not close Phase 00.
