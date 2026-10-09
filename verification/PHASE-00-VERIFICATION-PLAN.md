# Phase 00 verification plan and record

**Plan status:** DEFINED  
**Actual test status:** NOT RUN  
**Independently accepted:** NO

## Documentary checks

- D-01 Verify every internal path referenced by the manifest exists after overlay extraction.
- D-02 Confirm ZIP contains no executable/source engine code, Git metadata, private genealogy or Doom IWADs.
- D-03 Confirm all added/updated content is human-readable Markdown/JSON.
- D-04 Confirm source IDs and source URLs match evidence index.
- D-05 Confirm Phase 00 status/ADRs remain pending, not falsely accepted.
- D-06 Confirm no unexpected changes to existing root AGENTS, baseline ADR or other phase files.

## Planned runtime checks (separately authorized)

Use test matrix C-001…C-015 on actual machine after selected engine candidate source has been reviewed and compiled. Record commands, output, captures, hashes, GPU driver, versions and exact revision.

## Report fields

- Date, reviewer, local commit
- Commands/checks and outcome
- Files changed
- Tests run (NONE until performed)
- Deviations/conflicts
- Rollback instructions
- Acceptance recommendation to operator
