# SNE-WO-000A — Current-game source inventory

- Phase: SNE-P00
- Status: READY FOR AUTHORIZATION / NOT EXECUTED
- Mode: READ-ONLY research; no project source or upstream fork mutations
- Evidence requirements: repo URL, exact commit SHA, file/symbol locations, retrieval date, uncertainty, independently reviewable findings

## Mission

Pin game repo SHA; examine game scripts, map definitions, build/validator scripts, Godot handoff producer and Doom-side receiver; identify all required Tier-A behaviors.

## Deliverable

A source-path- and symbol-linked inventory, no unverified parity claims.

## Exit gate

No omitted load-bearing game files; every claim has SHA/path.

## Guardrails

No implementation, no repository pushes, no copying engine source into SNE scaffold, no unlicensed commercial IWAD, no private genealogy, no claimed runtime PASS without logs. Curated evidence only: no conversation transcripts.

## Handoff

Evidence → `artifact-chain/evidence/SNE-EVD-000.md` and appropriate `evidence/` records; review → `governance/PHASE-00-REVIEW-GATES.md`; acceptance → `artifact-chain/acceptance/SNE-ACC-000.md`.
