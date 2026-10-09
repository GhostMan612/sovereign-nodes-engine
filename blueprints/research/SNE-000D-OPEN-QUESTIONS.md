# WO-000D — Unresolved build and benchmark questions

| ID | Urgency | Unknown | Closure evidence |
|---|---|---|---|
| DQ-01 | P0 | Is MSVC 2022 / Windows SDK / CMake 3.16+ actually installed? | operator Windows environment record |
| DQ-02 | P0 | Which exact GPU driver/backend runs UHD 620 today? | driver diagnostic and actual engine backend log |
| DQ-03 | P0 | What dependencies are required beyond root CMake/vcpkg list? | full CMake configure and transitive SBOM |
| DQ-04 | P1 | Does UZDoom link under Windows with default LTO vs `FORCE_NO_LTO`? | controlled build records |
| DQ-05 | P1 | Can BiasedDoom compile with GLTF ON and Python OFF? | flags, dependency/version, symbol and runtime tests |
| DQ-06 | P0 | Do all candidates pass C-001…C-008 with identical PK3? | operator custom game logs and visible proof |
| DQ-07 | P0 | What is P0 stable performance on actual laptop? | 3-run per candidate/scene frame traces |
| DQ-08 | P1 | How fast do 0/2/8/16 visible dynamic lights scale? | fixed scene/profile, valid P99 and 1% low |
| DQ-09 | P1 | Are GPU/CPU thermal and shared-memory confounds controlled? | hardware record and time-series temperature/power |
| DQ-10 | P0 | Have all transitive code and asset licenses been reviewed? | independently signed SBOM/notice decision |
| DQ-11 | P1 | Can a clean-room second build reproduce expected artifact hashes? | two independently recorded build environments |
| DQ-12 | P0 | Who approves the execution commands and storage locations? | explicit operator authorization with scope/date |

No question is answered merely by a readme claim or a well-formed JSON record. Preserve WO-000C sprite/handoff blockers as prerequisite tests.
