# SNE-EVD-000F — Read-only evidence readiness packet

## Available documentation and source-backed observations

- WO-A…E published commits, current SNE repo base `1644fb8`, game `44034e97`, upstream source pins (`GZDoom c26ce2`, `UZDoom dbedcc`, `BiasedDoom 6147e0`). See `evidence/sources/SNE-000F-SOURCE-SNAPSHOT.md`.
- Exact original game MAPINFO custom maps and ZScript fragments, long sprite/GLDEFS names, JSON boolean→ScanInt mismatch **risk**, and packager validator filename discrepancy. Source-level only; see `SNE-SRC-GAME-005.md`.
- Previously drafted WO-C C-001…C-015 case catalog and WO-D target Windows/UHD 620 command/measurement plan. No runs or results in this packet.

## Evidence missing for technical acceptance

1. Named independent reviewer of primary source and A–E discrepancies.
2. Written operator authorization by category and workspace for any future inventory, fixture, build or runtime activity.
3. Known original PK3 hash, lawful external IWAD identity and actual unique custom MAP01 identity.
4. Valid operator-run Windows native compiler/build records and per-candidate binary hashes.
5. Game C-001…C-008 unchanged PK3/negative controls per candidate.
6. UHD 620 >=3 real run traces with p95/p99/1% low and meaningful renderer integrity.
7. Full transitive SBOM, brand/asset rights, Python/Mantle security verification, maintenance review.
8. G1–G8 independent check, operator signed acceptance and ADR decision.

## Evidence storage and integrity policy

Raw binary logs/recordings and device paths remain off the public Git repository in an operator-approved location; sanitized summaries may cite hashes and assigned evidence IDs. Proprietary IWADs, private lineage, API secrets and copied transcripts never enter planning files. Blank templates are **not** evidence.

**Evidence classification: SOURCE-OBSERVED / TEST-SPECIFIED / ALL RUNTIME NOT RUN.**
