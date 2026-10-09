# WO-000D — Open risks and stop conditions

| Risk | Severity | Evidence needed | Control |
|---|---|---|---|
| Wrong/missing compiler/SDK | HIGH | inventory of actual `cl`/SDK/CMake | block configuration until approved |
| Mixed multi-config vs single-config build | HIGH | generator and Release/Debug state | isolated build directories, separate records |
| Unpinned dependencies/vcpkg baseline | CRITICAL | complete SBOM, hashes, source URL | no distribution/performance decision |
| UZDoom updater-only failure misread as engine failure | MEDIUM | `USE_UPDATER` value and error branch | baseline OFF, diagnose per-branch |
| BiasedDoom Python running untrusted code | CRITICAL | trust review and explicit opt-in | request OFF in baseline; no unknown mods |
| GLTF ON/feature macro absent | HIGH | options, symbols and runtime asset proof | independent ON/OFF lanes |
| UHD 620 thermal/driver VSync confounding | HIGH | environment and raw traces | 3-run, rotated, stable profile comparisons |
| Vanilla IWAD fallback inflates apparent FPS | CRITICAL | custom MAP01 unique proof C-001 | reject whole run |
| Source sprite/handoff problems from WO-C | CRITICAL | C-004 and C-006 negative controls | do not score engine while unresolved |
| Legal/brand asset omission | CRITICAL | full rights/notice review | no redistributed binary or IWAD |
| Stale preimage from unexpected Git state | HIGH | baseline SHA and exact REPLACE blobs | stop extraction, never silently clobber |
| Reviewer self-certification | HIGH | independent report and owner choice | never auto-accept author-produced packet |

**All execution risks open** until real evidence. This is a risk plan, not test result.
