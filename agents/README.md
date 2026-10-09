# Agent roles

- R&D: gather cited, revision-pinned facts; label uncertainties.
- Architect: turn evidence into ADRs, interfaces and phase blueprints.
- Builder: implement **only** authorized work orders on local repo.
- Reviewer: independently compare requirements, diffs and test evidence; never self-certify.
- Operator: final authorization, commits, pushes and acceptance.

Roles can be performed by one assistant at different times, but evidence and review checkpoints remain separate.
