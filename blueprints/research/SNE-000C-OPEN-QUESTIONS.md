# WO-000C — Open technical questions ranked by stop-risk

| ID | Severity | Open question | Required next evidence | Owner role |
|---|---|---|---|---|
| OQ-01 | CRITICAL | Do ORESHAA0 and TOOLAA0 resolve to intended sprite families and GLDEFS lights? | exact packed archive symbol/frame runtime proof | compatibility tester |
| OQ-02 | CRITICAL | Does boolean `hasParadox` round-trip via `ScanInt`? | synthetic true/false baseline run | handoff tester |
| OQ-03 | HIGH | Should newer or missing handoff schemas be accepted, rejected or migrated? | ADR for schema evolution + threat review | architect/operator |
| OQ-04 | HIGH | Does each chosen engine compile all three source ZScript fragments unchanged? | exact engine log+actors+HUD | tester |
| OQ-05 | HIGH | Does the game custom MAPINFO survive map transitions and saves? | three-map state ledger | gameplay tester |
| OQ-06 | HIGH | What is BiasedDoom glTF compile registration / embedded texture behavior? | feature-flags+runtime fixture | rendering reviewer |
| OQ-07 | HIGH | Are inherited voxel associations enough for desired model coverage? | KVX fixture across actor categories | rendering reviewer |
| OQ-08 | HIGH | What dynamic-light count is sustainable on actual UHD 620? | three-run p99 + 1% low data | laptop operator |
| OQ-09 | HIGH | How is W1/W2 world state persisted across custom clusters? | GZDoom/UZDoom save/hub trace and runtime | simulation reviewer |
| OQ-10 | HIGH | What can ZDaemon actually run? | native ZDaemon-only profile and fixtures | multiplayer reviewer |
| OQ-11 | HIGH | Which engine fork permits manageable license and asset redistribution? | third-party SBOM and attribution | legal reviewer |
| OQ-12 | MEDIUM | What is fallback when upgraded renderer unavailable? | explicit backend selection and P0 measurements | operator |

All questions remain open until source-specific or operator runtime evidence is attached. The findings in WO-C are research inputs, not authority to make changes in the original game repo.
