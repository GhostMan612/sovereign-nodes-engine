# WO-E — Evidence confidence taxonomy

| Label | Appropriate use | Not permissible |
|---|---|---|
| PINNED-SOURCE | immutable commit+path was inspected | asserting feature works in current build |
| AUTHOR-DOC | upstream README/document states capability | claiming measured behavior |
| REASONED-RISK | specific source-pattern concern with a falsifiable future test | claiming runtime bug already reproduced |
| TEST-PLAN | clear setup/oracle/negative control exists | claiming plan is an executed check |
| PACKAGE-PASS | ZIP membership, SHA, syntax and formatting validated | using to close P00-G3/G4/G5/G7 |
| RUNTIME-PASS | real candidate + same PK3 run, logs and reviewer proof | synthetic/unexecuted values or vanilla IWAD |
| ACCEPTED-FOUNDATION | operator signs ADR with hard gates closed | author selects a favorite engine |

The WO-E scorecard is deliberately empty; conditional research priorities are not equivalent to a foundation verdict.
