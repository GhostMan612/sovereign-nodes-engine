# AGENTS.md — Evidence-closure blueprints

These Markdown documents define **future** experimental obligations, not agent execution rights. Read root `AGENTS.md`, `SNE-WO-000F.md`, the pending foundation ADR and operator authorization record before acting.

1. Preserve original source game/engine repos and unrelated dirty work. No automatic source edits, system installs, builds, game launches or Git pushes.
2. Use exact game SHA, candidate SHA, PK3/IWAD references and hashes for every reproducibility claim. Proprietary IWAD bytes stay outside repo; personal paths and hostnames are redacted.
3. `SOURCE-OBSERVED` and `TEST-SPECIFIED` are not `PASS`. Tests begin `NOT RUN`; authorization missing means `BLOCKED`, not `FAIL`.
4. Capture original and altered fixture hashes separately. A fixture-only repair never proves unchanged PK3 parity.
5. Independent reviewers must be distinct from package authors; all dissent and residual critical risks remain visible.
6. No real Mantle genealogy, private graph, vault data, untrusted embedded Python or live external network connector in test fixtures.
7. Use complete files for documentation changes, explicit-path staging only, and final end-of-plan Git checks under operator control.
