# SNE-WO-000D — Hardware/build verification design

- Phase: SNE-P00
- Status: READY FOR AUTHORIZATION / NOT EXECUTED
- Mode: READ-ONLY research; no project source or upstream fork mutations
- Evidence requirements: repo URL, exact commit SHA, file/symbol locations, retrieval date, uncertainty, independently reviewable findings

## Mission

Create repeatable source-build and profiling plans for Windows/UHD 620; record dependencies, release settings, shader/driver hazards.

## Deliverable

Build recipe draft and on-device benchmark protocol, not false results.

## Exit gate

Operators can run tests and record enough detail to reproduce.

## Guardrails

No implementation, no repository pushes, no copying engine source into SNE scaffold, no unlicensed commercial IWAD, no private genealogy, no claimed runtime PASS without logs. Curated evidence only: no conversation transcripts.

## Handoff

Evidence → `artifact-chain/evidence/SNE-EVD-000.md` and appropriate `evidence/` records; review → `governance/PHASE-00-REVIEW-GATES.md`; acceptance → `artifact-chain/acceptance/SNE-ACC-000.md`.
