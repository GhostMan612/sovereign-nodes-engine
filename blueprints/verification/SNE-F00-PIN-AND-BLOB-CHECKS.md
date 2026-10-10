# F-00 — Immutable provenance verification blueprint

## Read-only Git procedures (future approved reviewer)

For an already-present repository and approved read-only scope, inspect exact revisions without touching tracked or untracked working files:

```powershell
# Example only; not executed on user's laptop in this package.
git show 44034e97fd22129f919a18cadceb84466ef1bcd3:games/SovereignNodesFPS/game/MAPINFO.txt
git rev-parse 44034e97fd22129f919a18cadceb84466ef1bcd3:games/SovereignNodesFPS/game/MAPINFO.txt
# Compare the returned Git blob to pinned ledger before evaluating contents.
```

The shown command assumes it is run inside the **game repository**, not the SNE documentation repository. If reviewer uses a web/API source instead, record exact immutable URL and returned Git blob. `git show SHA:path` reads stored source; it does not prove compiled execution. Do not run `git checkout`, `git clone`, submodule updates, scripts, or network installers under a read-only source authorization.

## Chain-of-custody ledger requirements

- Repository full identity, commit SHA, file relative path, blob SHA-1 returned from Git, date, reviewer tool, attempted line span and exact claim ID.
- For 404/missing files, capture attempted revision/path, error class, tree-listing/search follow-up, and whether an equivalent different path was found.
- When source proves a *conditional* feature, record its gate flag and both ON/OFF build requirements; preserve `NOT RUN` until binary identity exists.
- Source may be stale even with a valid SHA. “Pinned source describes historical behavior” is not a claim that today's released engine has the same design.

## Review halt

Mismatch between expected blob and actual frozen commit, inconsistent line evidence, ambiguous path alias, or unknown source provenance ⇒ mark `UNRESOLVED`; do not close G1. Correct source metadata with a new record and re-review the impacted claims, preserving original package manifest.
