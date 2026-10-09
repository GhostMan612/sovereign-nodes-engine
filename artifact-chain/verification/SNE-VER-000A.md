# SNE-VER-000A — Verification matrix (not executed)

| Gate | Method | Status |
|---|---|---|
| V-A1 | Compare source links and SHA pins to expected content | SOURCE READ; INDEPENDENT RECHECK PENDING |
| V-A2 | Exhaustive gameplay paths and class inclusion review | PARTIAL; PENDING |
| V-A3 | Inspect generated WAD binaries and PK3 members | NOT RUN |
| V-A4 | Execute current game build/validation scripts | NOT RUN; separate authorization required |
| V-A5 | Boot baseline GZDoom with custom maps and verify identity | NOT RUN |
| V-A6 | Observe Godot→Doom synthetic handoff behavior | NOT RUN |
| V-A7 | Test hostile/oversize/stale handoff handling | NOT RUN |
| V-A8 | Compare engine candidates on UHD 620 | NOT RUN |
| V-A9 | Verify patch/asset licensing beyond root licenses | INCOMPLETE |
| V-A10 | Independent critical review | PENDING |

## Evidence required

Record each test's command, environment, source and data hashes, actual output, discrepancy, reviewer, and rollback in a later operator-authorized run. A successful UI launch is not evidence that custom ZScript loaded.

**Verdict:** Verification gate remains OPEN.
