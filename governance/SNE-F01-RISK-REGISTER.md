# F-01 — Authorization, scope and handoff risks

| ID | Severity | Risk | Prevention / stop |
|---|---|---|---|
| F01-R01 | CRITICAL | template mistaken for actual signed authorization | default `PROPOSED`, private authenticated operator proof |
| F01-R02 | CRITICAL | approval category inherited (e.g. build→run) | one category and one immutable scope per request |
| F01-R03 | CRITICAL | scope path escapes via wildcard/symlink/junction | absolute canonical allowlist with filesystem check |
| F01-R04 | HIGH | outdated approval replay / revoked actor | short bounded validity, revocation check at dispatch |
| F01-R05 | CRITICAL | commercial IWAD or private genealogy enters public repo | legal external asset pointer and redacted/private evidence |
| F01-R06 | CRITICAL | author certifies own independent review | distinct reviewer, conflict declaration and dissent |
| F01-R07 | HIGH | unapproved source or dependency mutation | freeze SHA, commands, network and artifact hashes |
| F01-R08 | HIGH | host inventory silently installs SDK or edits PATH | only version inspection, block missing tool |
| F01-R09 | CRITICAL | fixture repair represented as unchanged game PASS | B0/B1/B2 hashes, distinct case states |
| F01-R10 | HIGH | GPU thermal risk and unfair cross-engine comparison | thresholds, cap, scene, actual on-device controls |
| F01-R11 | HIGH | public JSON APPROVED fraud or accidental trigger | signature external and required live operator confirmation |
| F01-R12 | HIGH | unlimited evidence retention or private log publication | scope-specific privacy, retention and review |
| F01-R13 | HIGH | source push substitutes for technical acceptance | documentary Git checks distinct from G1…G8 gates |
| F01-R14 | CRITICAL | engine selected before runtime/license evidence | ADR-SNE-002 stays HOLD until independent review and operator decision |

Each item remains OPEN: F-01 is documentation design, not mitigated execution or audited rights. Escalate any scope mismatch as `BLOCKED`, never silent repair.
