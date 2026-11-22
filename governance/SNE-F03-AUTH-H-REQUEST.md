# SNE-F03 — AUTH-H read-only host inventory request (UNSIGNED DRAFT)

- State: **PROPOSED / NOT APPROVED / DISPATCH BLOCKED / EXECUTION NOT RUN.**
- Work order: `SNE-WO-F03`; frozen planning revision: `ef32a03d5b1d7bf70818404af9d7f27481e4a11e`.
- Companion record: `templates/SNE-F03-AUTHORIZATION-H.json` (validated against
  `templates/SNE-F03-AUTHORIZATION.schema.json`, adapted from the F-01 schema with a
  fresh parent constant — never reuse the historical `148dc28` value silently).
- Relationship: implements "least-powerful useful request now: AUTH-H, NOT AUTH-B"
  from `governance/SNE-F03-AUTHORIZATION-REQUEST.md`; follows the F-03 audit addendum
  (`artifact-chain/verification/SNE-VER-F03-ADDENDUM-AUDIT.md`) next-step proposal.
- This document and its templates confer **no permission**. Presence in Git,
  `APPROVED` text or a copied command list is not authenticated consent. Execution
  starts only from an individually dated, operator-authenticated private record with
  the scope digest filled in.

## Requested scope (mirrors the JSON record)

| Field | Value |
|---|---|
| task_id | `AUTH-H-SNE-F03-001` |
| purpose | Read-only Windows host/toolchain inventory for the P00-G4 native build preflight; no installs, builds, game launch or network |
| actor / device | null until the operator completes them privately |
| allowed reads | `C:\sovereign-nodes-engine` (HEAD check); system metadata queries below |
| allowed writes | private raw capture root only (`C:\Users\612co\.sne-private\auth-h\`) |
| network / downloads | forbidden / forbidden |
| budget | 20 minutes; 262144 output bytes max |
| retention | raw private max 14 days then delete; redacted summary retained in chain |
| public output | `verification/SNE-F03-HOST-INVENTORY-REDACTED.md` (future) |

## Proposed read-only command allowlist

Exactly the query set already specified in `blueprints/verification/SNE-F02-HOST-INVENTORY.md`
and `blueprints/verification/SNE-F03-WINDOWS-TOOLCHAIN.md`:

- `Get-CimInstance Win32_OperatingSystem` — Caption, BuildNumber, OSArchitecture
- `Get-CimInstance Win32_Processor` — Name, cores, logical processors
- `Get-CimInstance Win32_VideoController` — Name, DriverVersion, DriverDate, AdapterRAM (driver values may mislead on UMA)
- `Get-CimInstance Win32_ComputerSystem` — TotalPhysicalMemory only (no hostname/user)
- `Get-Command cmake|ninja|git|python|vswhere`; `cmake --version`, `ninja --version`, `git --version`, `python --version` when present
- `vswhere -products * -property installationVersion,installationPath` only if the operator approves this VS-locator method explicitly
- `git -C C:\sovereign-nodes-engine rev-parse HEAD`

Absence of a tool is recorded `NOT DETECTED BY METHOD` with the method; it is never
guessed and never repaired by installing anything.

## Stop conditions and rollback

Stop on: any write outside the private root, any needed network access, any
install/update prompt, revocation. Rollback: delete the private capture tree; the
queries are read-only, so no system-state restoration is expected.

## What remains before execution

1. Operator completes actor/device private fields, dates, expiry, private signature reference, and signs privately.
2. Executor recomputes `scope_sha256` over the exact frozen scope object and records the verification.
3. Only then run the allowlist into the private root, redact, publish the public summary and fill `templates/SNE-F03-HOST-READINESS.json`.

Until step 1 exists, AUTH-H stays **NOT GRANTED** and every dependent gate (G4 and
beyond) stays BLOCKED, not FAIL. This draft is not AUTH-B and implies no build lane.
