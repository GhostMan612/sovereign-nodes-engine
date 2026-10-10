# F-02 — Permission matrix and agent dispatch preflight

| Future activity | Minimum signed approval | Additional restrictions |
|---|---|---|
| Independently check source and path/dispute | AUTH-R | exact immutable repo list; no host modification |
| Inspect installed OS/compiler metadata | AUTH-H | exact commands and display fields; no installation |
| Hash existing lawful original PK3/WAD/IWAD | AUTH-H only if scoped for exact file reads and rights; else new exact owner-approved request | no full asset bytes published; paths private |
| Create B1/B2 synthetic fixture | AUTH-F | external sandbox, bounded writes and rollback |
| Invoke builder/validator on modified fixture | AUTH-F if exact command and side effects included | no overwrite of B0 or original checkout |
| Launch actual game for C-001–C-008 | AUTH-T | lawful IWAD, pinned binary, preapproved map/resources/session |
| Install/build candidate | AUTH-B | separate post-inventory; not permitted now |
| Benchmark graphics | AUTH-P | only after parity and preset thresholds |

## Pre-dispatch validation

- Operator **privately authenticates** approved ID, exact scope SHA, actor/device, date/time window, allowed paths/operations, negative controls, stop reason and revocation state.
- `templates/SNE-F01-AUTHORIZATION.json` is an unsigned example whose embedded planning SHA references the F-01 historical baseline. A later authorization must use the operator-selected *current* source/control commit and a new ID; never mutate old authorized scopes invisibly.
- Merely pushing `SNE-WO-F02.md` or copying status `APPROVED` into JSON cannot authorize anything. All categories are `PROPOSED / NOT AUTHORIZED` at release.

Return `BLOCKED` rather than improvising broader access. Approval for F-02A is **not** F-02B. Approval for fixture creation is **not** runtime, and an engine build is **not** a source modification or redistribution grant.
