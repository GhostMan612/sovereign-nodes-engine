# Local bootstrap and Git publication

## Target path
`C:\sovereign-nodes-engine` — standalone sibling repository. Keep `C:\svtc` as the orchestration toolchain, not the engine source tree.

## Extract
The ZIP contains one top-level `sovereign-nodes-engine/` directory. Extract into `C:\` to produce `C:\sovereign-nodes-engine\...`. **Do not extract into an existing repo root** or accidentally create `sovereign-nodes-engine\sovereign-nodes-engine`.

## Operator-controlled PowerShell commands
```powershell
cd C:\sovereign-nodes-engine
Get-ChildItem -Force
Get-ChildItem -Recurse -File | Measure-Object
# Inspect before initializing
 git init -b main
 git add .
 git status --short
 git commit -m "docs: initialize Sovereign Nodes Engine governance scaffold"
```
Create a **new empty** GitHub repository named `sovereign-nodes-engine` under your account, without initializing README/license/gitignore remotely. Then (after reviewing remote URL):
```powershell
 git remote add origin https://github.com/GhostMan612/sovereign-nodes-engine.git
 git remote -v
 git push -u origin main
```
The GitHub URL is a **proposed future destination**, not a claim the repo exists. Do not run `remote add`/`push` until created and approved.

## Later overlays
Back up or commit local changes first; inspect each ZIP manifest; unzip overlay at `C:\` if it contains the top-level folder. Never blanket-overwrite locally edited files without diff/review. Package versions live in `scaffold/MANIFEST.md`.
