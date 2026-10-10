# F-03 — Blank, nonauthorizing evidence templates

- `HOST-READINESS.json`: future specifically approved non-invasive AUTH-H metadata.
- `DEPENDENCY-ROW.json`: one provenance/license/ABI row per actual dependency.
- `BUILD-RECORD.json`: one candidate configure/compile attempt; all results initially NOT RUN.
- `RESOURCE-RECORD.json`: produced EXE/DLL/PK3/sidecar SHA-256 and rights state.
- `REPRO-RECORD.json`: **two different clean attempt IDs**, input equality, output identity, nondeterminism and reviewer.

Templates are **not** permissions, evidence, results or signatures. Never replace `null` with a guessed hash/version, never publish a private host/user path, and never elevate `status` to PASS absent actual approved operation, artifacts and independent reviewer. Source pins/history remain separate from test capture dates.
