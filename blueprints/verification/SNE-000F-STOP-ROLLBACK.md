# WO-F — Stop conditions, reversible experiments and local Git discipline

## Stop immediately if

- `git rev-parse HEAD` differs from `1644fb80c3e2803dd19465292423832e8fdf8e24` before extraction, or worktree has unrelated changes.
- Any expected ADD already exists locally or any REPLACE preimage does not match its manifest Git blob SHA-1.
- User authorization is absent/revoked for fixture, device inventory, native build, runtime test, network activity or game-source edit.
- Expected custom GapNode identity cannot be proven; ZScript/HUD light/map fallback is ambiguous; evidence cannot identify engine binary/PK3.
- Licensed IWAD, private genealogy, credentials, account names/paths or untrusted Python mod would enter a public output.
- A controller wants to overwrite original game/engine checkout to run a disposable fixture or run mass `git clean`/`reset --hard`.
- Thermal failure, repeated system stalls, integrity error, unknown license, unexpected driver/backend or inconsistent test parameters.

## Safe recovery

1. Stop the specific experiment and retain redacted failure diagnostic, source+binary+fixture hashes and operator signoff status.
2. Mark `BLOCKED`, `FAIL`, or `INCONCLUSIVE` according to real cause; do not relabel just to proceed to benchmarks.
3. Future authorized disposable workspaces are returned to baseline by discarding only known experiment artifacts, never deleting unrelated directories.
4. Prior user game repositories and local SNE history remain untouched; future repair changes require separate explicit scoped work order and backup/diff review.
5. If the document overlay was applied at wrong base, **do not** force-reset. Manually reconcile using the ZIP manifest/preimage SHA and local commit history.
6. Git stage only listed paths. Verify `git diff --cached --check`, `git diff --cached --name-only` and full staged diff; operator commits/pushes manually.

No continuous monitoring or automatic re-runs. Any repeated build/hardware actions require an approved test plan and separate operator execution.
