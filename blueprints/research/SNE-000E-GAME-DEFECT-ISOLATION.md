# WO-E — Separate original game defects from source-engine failures

## Motivation

Prior source audit indicates two first-order risks from the game itself. They must be isolated before choosing a fork or diagnosing GPU speed:

1. Existing game uses long sprite names `ORESHAA0` and `TOOLAA0`, while pinned GZDoom sprite lookup indexes four-character family names plus frame/rotation. Runtime binding is **not yet verified**; do not assume mismatch silently fails, since archive aliases/load rules may change behavior.
2. Existing Godot producer writes JSON `hasParadox` as a boolean, while the current ZScript consumer uses integer-oriented scanning. True/false outcomes are **not yet verified** and may mask authoring error rather than engine incompatibility.

## Future proposed discriminating tests

- Run original verified PK3 unchanged on stock control candidate and another candidate, assert unique custom MAP01 marker.
- Use *disposable generated fixtures only* to change one sprite mapping or handoff JSON representation at a time; never replace the authoritative game source without separate approval.
- Record baseline original bytes/hash, fixture diff/hash, actor/HUD/GLDEFS screenshots, load logs and any failure. Restore fixture automatically only within approved ephemeral area.
- If both engines fail identically on original and fixture resolves it, classify **likely game content defect** pending source review; do not penalize engine as a parser regression.
- If one passes original and other fails, classify **candidate compatibility discrepancy**, preserve exact version, flags and logs.
- Never patch the source game to hide a failure and then use the modified PK3 to claim unmodified parity.

## Other confounders

MAPINFO root-package placement, `addfragments` grammar, missing generated WADs, mislabeled official IWAD fallback, separate ZDaemon grammar, and virtual filesystem path rules. Stop when game identity is ambiguous.
