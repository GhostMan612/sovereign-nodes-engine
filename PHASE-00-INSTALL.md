# SNE Phase 00 v0.2.0 — installation and operator checkpoint

**Package:** SNE-P00-FOUNDATION-0002  
**Target:** `C:\sovereign-nodes-engine`  
**Archive root:** `sovereign-nodes-engine/`  
**Type:** Documentation-only overlay; no source code, binaries, IWADs, scripts, or Git metadata.

## Read before extraction

This overlay is based on SNE scaffold v0.1.0 and research performed on 2026-10-09. It adds Phase 00 evidence, research cards, candidate comparison, work orders, interfaces, decisions and review gates. It does **not** choose or fork an engine. It does **not** certify any compilation or FPS measurement.

## Installation

1. In PowerShell, open `C:\sovereign-nodes-engine` and check `git status --short`. Stop if local changes overlap the replacement list in `scaffold/PHASE-00-MANIFEST.md`.
2. Copy or back up any customized files in the replacement list. Keep the current Git commit as the rollback point.
3. Extract the ZIP into `C:\` (NOT `C:\sovereign-nodes-engine`, which would double-nest). Approve **replacement of only the manifest-listed files** if your ZIP tool asks.
4. Review `git diff --stat`, `git diff --check`, and `git status --short`; confirm there is no `engine/` source modification, `.git/` directory, executable, or unrelated file deletion.
5. Review and commit the documentation on your local `main` branch. **Push only when satisfied.** No command in this overlay automatically commits or pushes.

Suggested human-run post-review Git sequence (optional, NOT part of package execution):

```powershell
cd C:\sovereign-nodes-engine
git status --short
git diff --check
git add PHASE-00-INSTALL.md artifact-chain blueprints evidence governance registry scaffold verification docs
git diff --cached --stat
git commit -m "docs: scaffold Phase 00 foundation reconnaissance"
git push
```

## State and provenance

- `PHASE 00`: RESEARCH SCOPED / NOT ACCEPTED; factual findings are labeled VERIFIED FROM SOURCE or UNVERIFIED.
- `SNE foundation`: UNDECIDED; implementation authorization NOT GRANTED.
- `Sovereign-Nodes game`: read-only reference; never copied into this archive.
- The file `scaffold/PHASE-00-FILE-SHA256.json` lists archive content checksums.
- `scaffold/PHASE-00-MANIFEST.md` lists exact ADD and REPLACE paths.

## Next operator decision

After reviewing the overlay, authorize **SNE-WO-000A** (source inventory) and **SNE-WO-000B** (candidate deep audit) as read-only research. Approval is not implied by ZIP extraction.
