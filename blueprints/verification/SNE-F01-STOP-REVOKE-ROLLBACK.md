# F-01 — Stop, revocation, expiry and rollback

## Immediate stop if any condition holds

- No separately authenticated operator approval; wrong category; missing private signature; F-00 reviewer identity unresolved for a task requiring a reviewer.
- Scope/object SHA, immutable repository revision, candidate binary hash, legal asset reference, allowed path or actor differs from authorized freeze.
- Operator revokes or window expires; dependency requires unapproved network/installer/system change; command has unlisted side effects.
- An output path targets original game source, `sovereign-nodes-engine` planning repo for binary artefacts, secrets, real lineage or proprietary IWAD; junction/symlink can escape allowed root.
- Native process attempts untrusted embedded Python, unexpected firewall/driver update, an engine replaces custom GapNode with IWAD Entryway, machine thermal instability or missing evidence provenance.
- A reviewer claims independence while they are the original author or is unable to inspect primary source.

## Recovery policy

1. Stop the current **future separately authorized** task; do not run next tasks automatically.
2. Mark actual state `BLOCKED`, `INCONCLUSIVE` or `FAIL` with accurate cause; never fabricate PASS or hide invalid result.
3. Preserve original source and evidence identity, retain only data permitted by scope; redact before any public report.
4. Revert only explicitly listed disposable fixture files in their isolated temporary root by the approved method. Do not mass-delete, force reset, `git clean`, rewrite another agent's work or erase raw proof outside policy.
5. Record operator revocation/new-scope request under a **new ID**. Reusing an expired signed request is prohibited.
6. For documentation ZIP failure, STOP on wrong base or unexpected local file and manually reconcile manifest preimages. Never unconditionally overwrite unrelated dirty files.

## Expiry is not approval for cleanup

A task expiring stops new work. Any cleanup that could alter user data also needs to be covered by the original scope; otherwise request a new narrowly bounded cleanup approval and hold the unsafe operation.
