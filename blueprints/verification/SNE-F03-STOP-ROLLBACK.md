# F-03 — Stop conditions and bounded recovery

**During preparation/extraction:** stop if current SNE HEAD differs from the exact manifest baseline, `git status --short` has unrelated changes, a planned ADD file exists, a planned REPLACE blob differs or ZIP member integrity fails. Manually reconcile; never `reset --hard`, `git clean`, stage all files or silently overwrite.

**During any future approved build:** stop on missing/expired/revoked AUTH-B, dirty upstream source, wrong MSVC/SDK/generator, unexpected network/installer, unapproved code edit, dependency/license gap, path escape, wrong config flag, resource containing unlicensed assets or private data, uncontrolled Python feature, host instability or suspicious console output.

Report accurate `BLOCKED`/`FAIL`/`INCONCLUSIVE` by stage with original evidence IDs. Do not auto-retry under altered flags, delete unrelated directories, erase failed logs or execute a later gameplay test. Cleanup is restricted to known disposable outputs **only if explicitly permitted** by original approved scope.

SNE documentation overlay installation is reversible only by a deliberate operator review of Git diff and path manifest; no scripted destructive rollback is provided. The original Sovereign Nodes and candidate repositories are untouched by this ZIP.
