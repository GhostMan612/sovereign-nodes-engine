# WO-F — Disposable fixture design, provenance and failure attribution

## Goal

Distinguish bugs in original Sovereign Nodes FPS assets (sprite naming, handoff scanning, packaging) from incompatibilities in candidate engines, without modifying or compromising the source game.

## Fixture rules (future work, not executed)

1. Obtain explicit operator permission for an isolated, user-chosen workspace; do not write into `C:\sovereign-nodes-engine` or `C:\Sovereign Nodes` during testing except through separately authorized changes.
2. Record exact original repo SHA and original PK3 SHA-256 before any generated fixture. No commercial IWAD copied, edited or redistributed.
3. Build fixture `B0`: byte-identical original game resource set; `B1`: change just one suspected sprite alias/frame mapping; `B2`: change just one handoff JSON scalar representation; `B3`: intentionally omit project PK3 to prove IWAD fallback is detectable; `B4`: deliberately omit one fixture-only fragment to prove parser failure visibility.
4. Hash each fixture and retain a minimal diff (no original copyrighted assets shared). All synthetic fields use `SAMPLE ANCESTOR A`, placeholder node and throwaway UUID; no real genealogy.
5. Run unchanged `B0` on the candidate first, record map/actor/light/HUD data; compare one variable at a time. If a fixture passes and B0 fails, **B0 remains failed**.
6. Attribute possible defect only after ruling out build flags, different IWAD/PK3, renderer API, SDL/audio behavior, profile or incorrectly selected map.
7. A fixture used to test one parser must not inadvertently alter actor health, collisions, inventory, custom HUD or map transitions.

## Classification table

| B0 result | Controlled fixture | Candidate comparison | Proposed interpretation |
|---|---|---|---|
| fails on both GZ and UZ | isolated change passes on both | same environment | *probable game-content defect*, reviewer verify |
| GZ passes, UZ fails | fixture not needed | exact same PK3 | *probable candidate regression* |
| both pass | negative control catches expected absence | original unchanged | baseline candidate validation possible |
| B0 unknown/Entryway | anything | any | inconclusive; cannot score |
| B0 fails and unrelated variables changed | passes | any | inconclusive; restore single-variable experiment |

## Rollback

Delete **only explicitly authorized disposable copied files**, after preserving hash/redacted observation record; never `git reset --hard`, mass clean, overwrite game repo, or remove unrelated host directories.
