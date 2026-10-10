# F-03 — Native Windows readiness risks (unresolved)

| ID | Severity | Risk | Required control | Present state |
|---|---|---|---|---|
| F03-R1 | CRITICAL | unsigned AUTH-B treated as permission | private operator auth with exact scope digest | BLOCKED |
| F03-R2 | HIGH | Visual Studio/SDK assumed installed | signed AUTH-H host inventory | NOT RUN |
| F03-R3 | HIGH | source/submodule/dependency revision floats | exact SHAs, no-network default | NOT VERIFIED |
| F03-R4 | HIGH | runtime binary and PK3 conflated | separate file hashes and resource manifest | NOT BUILT |
| F03-R5 | HIGH | `SNE` / source-game checkout mutated | external isolated build outputs and clean guards | PLAN ONLY |
| F03-R6 | HIGH | UZDoom Python build requirement misdiagnosed | native Python3 >=3.6 inventory | UNKNOWN |
| F03-R7 | HIGH | BiasedDoom embedded Python executes | Python OFF and verified cache, no untrusted scripts | NOT RUN |
| F03-R8 | HIGH | glTF fastgltf dependency silently fetched | glTF OFF baseline, optional approved separate lane | NOT RUN |
| F03-R9 | HIGH | unlicensed bundled asset (`BUILD_NONFREE`) | per-asset notices, G2 and AUTH-D hold | NOT CLEARED |
| F03-R10 | MEDIUM | VS/Ninja generator or CRT ABI mismatch | separate caches, actual toolchain and symbols | UNKNOWN |
| F03-R11 | MEDIUM | bitwise mismatch misunderstood | two fresh attempts and diff classification | NOT RUN |
| F03-R12 | CRITICAL | build PASS mistaken for game/FPS PASS | require separate AUTH-T/P + G3/G5 | NOT RUN |
| F03-R13 | HIGH | AI-assisted upstream UZDoom PR contrary to policy | no upstream PR, independent downstream terms review | BLOCKED |
| F03-R14 | CRITICAL | independent reviewer self-certification | distinct reviewer and dissent record | PENDING |

No row implies a real failure was observed. Operators/reviewers may append findings only from future separately authorized actions and authenticated evidence.
