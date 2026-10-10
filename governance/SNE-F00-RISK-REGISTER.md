# F-00 — Active review risks and controls

| ID | Severity | Risk | Control and future evidence | State |
|---|---|---|---|---|
| F00-R01 | CRITICAL | author self-certifies independent G7 | distinct reviewer, primary-source recheck, signed dissent | OPEN |
| F00-R02 | HIGH | false sprite-render failure inferred from naming | inspect full parser and aliases, then later unchanged PK3 | OPEN |
| F00-R03 | HIGH | Boolean truthiness claimed without ToInt proof | trace engine conversion and synthetic later test | OPEN |
| F00-R04 | HIGH | missing `validate_pk3.py` path treated as no game validation | full tree, built-in packager checks, actual tool entrypoint | OPEN |
| F00-R05 | HIGH | wrong SHA/line citation or branch drift | Git blob preimage and immutable URL checks | OPEN |
| F00-R06 | HIGH | comments or README misread as actual executable PASS | source-vs-runtime classification, test evidence IDs | OPEN |
| F00-R07 | CRITICAL | licensed IWAD/private Mantle data enters public repo | strictly docs-only ZIP, redacted source links and review IDs | CONTROLLED BY PACKAGE SCOPE; future risk open |
| F00-R08 | HIGH | option flags imply glTF/Python build or harmless execution | source flags vs binary flags, independent security review | OPEN |
| F00-R09 | HIGH | unapproved execution beyond read-only review | explicit operator category and isolated scope | NOT AUTHORIZED |
| F00-R10 | HIGH | A–F historic checksum ledgers rewritten in place | append corrective record; preserve history | OPEN |
| F00-R11 | CRITICAL | engine chosen before G2–G7 | keep ADR HOLD and scorecard null | OPEN |

No risk is mitigated by invented sample logs or by author declaring PASS. Actual acceptance requires reviewer and operator involvement.
