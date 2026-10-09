# IF-SNE-003 — Logical world continuity contract (DRAFT)

## Phase 00 responsibility

Determine whether current MAP01→MAP02→MAP03 transitions can preserve selected state under available engine mechanics. No continuous-world streaming guarantee is made.

## Proposed abstractions

- `ZoneId`: stable namespace-scoped string independent of map display name.
- `PortalLink`: source/target zones, destination spawn, transition flags.
- `TransitionSnapshot`: player/game-safe world state with schema/version.
- `ZoneRegistry`: map ID and metadata mapping.

## Staged roadmap

1. Compatible conventional map change with state carryover.
2. Persistent logical world state.
3. Preloading and transition presentation improvements.
4. Truly simultaneous zones / render-through portals only after renderer and save/physics audit.

Do not call sequential map exits "seamless physical world".
