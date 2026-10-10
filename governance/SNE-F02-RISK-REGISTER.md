# F-02 — Risk and stop register

| Risk ID | Severity | Detection | Stop / disposition |
|---|---|---|---|
| F02-R01 | CRITICAL | unsigned/expired or spoofed AUTH-H/F/T | `BLOCKED`, no commands |
| F02-R02 | CRITICAL | source game checkout or SNE repo targeted by fixture writes | stop; choose off-repo scoped sandbox |
| F02-R03 | CRITICAL | commercial IWAD bytes, credentials, personal Mantle record or home path in public data | stop, redact and isolate privately |
| F02-R04 | CRITICAL | vanilla Entryway mistaken for original GapNode | reject original parity, no FPS scoring |
| F02-R05 | HIGH | B1/B2 change alters more than one independent variable | invalidate fixture, preserve before/after hash |
| F02-R06 | HIGH | `SNDINFO` omission assumed a defect despite pinned packager intentionally excluding | correct baseline acceptance catalog |
| F02-R07 | HIGH | static validator print treated as ZScript compile or gameplay proof | downgrade to source/static only |
| F02-R08 | HIGH | missing exact `validate_pk3.py` path misinterpreted as missing *all* validation | independent function-to-check crosswalk |
| F02-R09 | HIGH | false handoff result misread as correct while true parse is broken | two-sided truth table + numeric-only control |
| F02-R10 | HIGH | GPU AdapterRAM / missing `cl` misreported as actual resource or no installed compiler | record probe limitation, never guess |
| F02-R11 | HIGH | symlink/reparse point escapes approved test workspace | stop before any write |
| F02-R12 | HIGH | synthetic case is treated as original B0 PASS | preserve immutable original hash and separate result IDs |
| F02-R13 | HIGH | repo baseline differs, REPLACE preimage mismatch or ADD exists | stop extraction and manually reconcile |
| F02-R14 | HIGH | reviewer author self-signs G1/G7 | hold independent acceptance |

Owner remains operator; package author may self-critique but is not independent G7 reviewer. `ADR-SNE-002` remains HOLD and no permission is granted.
