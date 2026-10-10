# F-01 — Network and dependency budget before execution

**Default: network use prohibited for local experiments.** Read-only public GitHub inspection already performed by the planning author is not a license to run downloads on the user's Windows device.

## Category decisions

- `AUTH-R`: permitted only to selected public immutable source URLs if operator agrees; no third-party uploader, unreviewed URL redirect or modifying repository.
- `AUTH-H`: local command metadata only, no update checks, automatic installer or telemetry unless explicitly reviewed and separately consented to.
- `AUTH-F`: fixture-only local synthetic generation; no remote asset pulls, external model fetches or `curl | sh`.
- `AUTH-B`: any Git checkout, submodule, vcpkg/archive download, package manager, compiler installer or network dependency is separately listed with exact URL, revision, expected SHA and allowed output root; default block.
- `AUTH-T/P`: local game/performance sessions are offline by default; network multiplayer/ZDaemon must be a separate explicit scope.
- `AUTH-S`: static rights research may query approved public documentation; no proprietary blobs transmitted.

## Supply-chain invariants

A package or checkout is not trusted merely because the name matches. Freeze source commit, deps manifest, checksums, signing policy and `CMakePresets`/generator values. If an unlisted new dependency appears, stop and revise approval rather than installing it. Check UZDoom's `USE_UPDATER` branch separately, and keep BiasedDoom embedded Python OFF for baseline until trusted/native execution is authorized.

## Failure and evidence

Dependency unavailable under denied network scope → `BLOCKED: DEPENDENCY_NOT_AUTHORIZED`, not engine incompatibility. A hash mismatch or untrusted install step → STOP, preserve the sanitized requested URL/hash and operator decision. No actual dependency retrieval is part of F-01.
