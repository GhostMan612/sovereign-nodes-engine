# SNE-WO-000B — First-pass reviewer findings

**Reviewer:** Assistant (same entity as author). **Independent-review gate: NOT MET.**
**Review date:** 2026-10-09

| Finding | Severity | Observation | Resolution / status |
|---|---|---|---|
| B-R01 | High | UZDoom CONTRIBUTING prohibits AI-authored code/comments PRs, distinct from GPL licensing | Documented; do not upstream AI contributions |
| B-R02 | High | BiasedDoom glTF `#ifdef NEODOOM_GLTF_SUPPORT` and CMake enable flags not proven end-to-end | Mark unresolved; validate registration and runtime |
| B-R03 | High | BiasedDoom README roadmap would deprecate ZScript, conflicting with current game's dependency | Maintain compatibility-first lane; no migration approval |
| B-R04 | High | Full asset/code notices and third-party transitive licenses remain unaudited | Block release clearance |
| B-R05 | High | All Tier-A runtime and Intel UHD 620 performance untested | Block foundation decision |
| B-R06 | Medium | Original WO-000A ZIP manifest hashes differ after 24 whitespace trims | Separate normalized committed-byte reconciliation ledger, leave historical package manifest intact |
| B-R07 | Medium | GZDoom/UZDoom hub stats are not simultaneous streamed geometry | Limit initial world scope to logical continuity |
| B-R08 | Medium | `hasParadox` JSON bool versus ZScript `ScanInt` is suspicious | Specific pending T-A07 test; do not declare defect without execution |
| B-R09 | Medium | WAD generator requirement `dirofs=12` is project-local layout, not universal WAD rule | Clarified in code map |
| B-R10 | Medium | BiasedDoom docs state external `.gltf` textures safer than `.glb` embedded images | Dedicated T-R03 format coverage |

## Conclusion

The source-map and option comparison provide a useful blueprint base and support incremental reuse. **They do not justify an engine selection.** After independent review, route compatibility-focused research to WO-000C and build/performance planning to WO-000D.
