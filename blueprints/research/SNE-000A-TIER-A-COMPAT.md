# Tier-A source-to-test compatibility contract (SNE-WO-000A)

**Status:** TEST SPECIFIED / NOT RUN. Exact game pin is in the revision ledger. Every result must be independently reproduced and reviewed before acceptance.

| Test ID | Source evidence | Failure injection or assert | Required proof |
|---|---|---|---|
| TA-001 | MAPINFO MAP01 | Force known custom MAP01 identification | Engine clearly loads GapNode, not IWAD Entryway |
| TA-002 | `addfragments` | One fragment missing/invalid in test-only copy | Packaging/compile gate fails, not fallback success |
| TA-003 | Actor/DoomEdNums | Place/activate registered custom actor | Actor tag resolves and behavior seen |
| TA-004 | Sprites | Use referenced exact sprite frames | No invisible or missing-frame actors |
| TA-005 | GLDEFS | At least one ELEC bound actor | Light visibly affects world in requested renderer |
| TA-006 | Map graph | End MAP01 then MAP02 | Both transitions reach intended next map |
| TA-007 | HUD | Change ore, locator and score state | `SNStatusBar` reflects state live |
| TA-008 | Handoff v1 | Synthetic runId/seed/name sent from Godot | Doom receives same values and displays them |
| TA-009 | Handoff malformed | Missing/temp/stale/wrong schema | No crash; policy explicitly defined; no private data |
| TA-010 | WAD validator | Corrupt a test-only generated WAD | Validator fails as expected, not false PASS |
| TA-011 | Standalone mode | Launch FPS with no Godot handoff | Game remains playable without fake genealogy |
| TA-012 | Security | Place oversized handoff file in isolated test | Reader does not hang, leak or allocate without limit; current source unverified |
| TA-013 | ZDaemon lane | Tested separately on its own target | No assumed support for GZDoom-only ZScript/renderer |

## Evidence schema

For each test record: engine project + exact commit, game SHA, packed PK3 hash, authorized IWAD identifier (not contents), GPU/driver, OS, display resolution, command/config, synthetic input hash, expected/observed result, relevant log snippet, screenshot where meaningful, reviewer and severity. Unexecuted row status is **NOT RUN**, never PASS.

## Design acceptance principles

Map identity, fragment loading, shader effects, scripting and handoff must be tested separately; positive boot alone does not imply any of them. Tests must be able to **fail for the known historical defects** to be trustworthy.
