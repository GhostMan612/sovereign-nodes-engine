# WO-F — False positives and benchmark confounders

| False positive | Why it appears credible | Required falsification |
|---|---|---|
| Vanilla `Entryway` loads instead of custom `GapNode` | Doom runtime boot appears successful | unique project actor and geometry; omit-PK3 control |
| ZScript listed in PK3 but not compiled | archive inspection passes | actual class instantiation, HUD and negative fragment control |
| Sprite filename exists but actor invisible | prefix vs frame confusion | actor interaction plus exact rendered frame screenshot |
| GLDEFS `pointlight` present but not attached | definition conflated with binding | identical light-on/off and association-omission controls |
| `hasParadox=false` observed for false input | default false masks a broken scanner | true and false *both* tested plus numeric-only fixture |
| Game generator prints success | validator or independent parser may be missing | inspect actual validator file, WAD bytes and gameplay |
| glTF README says supported | feature may be conditionally compiled | binary flag, actual external texture/animation test |
| Fast GPU FPS without new models | assets quietly absent | screenshot/image-diff and actor counts |
| Native build succeeds | no custom mod loaded | C-001…C-008 follow-on proof |
| UZDoom PR rules treated as GPL veto | contribution policy != redistribution license | independently read source license + policy separately |
| Save/load works in one level | does not prove world continuity or cross-engine save | real map transition/revisit state ledger |
| Self-review marked independent | author and reviewer same source | separate reviewer identity and primary evidence sampling |

No target candidate can be promoted based on these uncontrolled signals. A reproducible negative control is required where specified in the C-series catalog.
