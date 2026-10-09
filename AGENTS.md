# AGENTS.md — Root governance

## Authority
Operator owns decisions, repository and remote operations. ChatGPT may author/review **downloadable overlay packages**; local coding agents may implement only against an approved work order. Gemini/other research outputs are evidence inputs, not authority. No agent may approve its own implementation.

## Guardrails
1. Read this file, nearest nested `AGENTS.md`, `README.md`, architecture ADRs, and active work order before editing.
2. Documentation changes are allowed only when explicitly requested. Engine source/build/dependency edits require separate authorization.
3. Preserve existing files and unrelated dirty work. No force push, resets, destructive cleanup, or auto-merge.
4. Keep every artifact traceable with IDs and links; mark unknowns **UNVERIFIED**, not PASS.
5. Keep conversation transcripts and agent chat logs out of the repository. Store only curated evidence, decisions, specifications, and verification results.
6. No sensitive real-person genealogy, credentials, private ledger data, or copyrighted Doom IWADs.
7. Prefer complete-file replacements for approved overlays; never silently overwrite operator-customized files.
8. Agent must record changes, test commands/results, risks, and rollback path in verification report.

## Initial scope
Scaffolding and research only. Engine fork, programming, builds and GitHub push require explicit authorization.
