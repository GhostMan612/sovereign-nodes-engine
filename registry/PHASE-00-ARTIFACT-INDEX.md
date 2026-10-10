# SNE Phase 00 — Work-order registry v1.0.0, F-01 authorization design

| Work order | Last confirmed operator-published commit | State |
|---|---|---|
| WO-000A | `369722f` | published source research; acceptance pending |
| WO-000B | `edc274f` | published upstream audit; acceptance pending |
| WO-000C | `706db57` | published compatibility specification; no runtime proof |
| WO-000D | `1f21e4c` | published Windows/UHD protocols; not run |
| WO-000E | `1644fb8` | published architecture red-team; ADR HOLD |
| WO-000F | `1c01d2f` | published verification readiness; no approvals granted |
| F-00 | **`148dc28cdbdf4970c8011d76762b31b8dcafea0b`** | published source review handoff; **external independent signoff pending** |
| **F-01** | **NOT YET COMMITTED** | v1.0.0 documentation preparation; **authorization records empty/unapproved** |

## F-01 new canonical artifacts

| Class | File | State |
|---|---|---|
| Operator work order | `artifact-chain/work-orders/SNE-WO-F01.md` | proposed, documentation only |
| Intake | `docs/SNE-F01-START-HERE.md` | usage and hard stops |
| Scope-freeze design | `blueprints/verification/SNE-F01-SCOPE-FREEZE.md` | protocol, not run |
| Approval lifecycle | `blueprints/verification/SNE-F01-AUTHORIZATION-LIFECYCLE.md` | proposed permission state machine |
| Agent handoff | `blueprints/verification/SNE-F01-AGENT-DISPATCH-CONTRACT.md` | no active agent task |
| Review/authority | `governance/WO-000F-AUTHORIZATION-MATRIX.md` | revised matrix with F-01 categories and all pending |
| Evidence and acceptance | `artifact-chain/evidence/SNE-EVD-F01.md`; `artifact-chain/acceptance/SNE-ACC-F01.md` | source-review references, acceptance unfilled |
| Blank operator templates | `templates/SNE-F01-*.json` | unsigned and nonauthorizing |
| File manifest | `scaffold/SNE-F01-MANIFEST.md`; `scaffold/SNE-F01-SHA256.json` | overlay validation only |
| Foundation ADR | `blueprints/decisions/ADR-SNE-002-FOUNDATION-PENDING.md` | **HOLD / unchanged** |

## Registry invariants

The observed commit `148dc28cdbdf4970c8011d76762b31b8dcafea0b` is the **pre-extraction** parent only; the F-01 output commit must be recorded in a later revision after the operator's actual push. Avoid inventing Git SHAs, rewriting historical A–F evidence, accepting G7 from author-written forms, or activating a command because this overlay was installed.

**Next:** after package publication, the operator can appoint an independent F-00 reviewer and separately approve a minimally scoped `AUTH-R`, or request a specific `AUTH-H` metadata inventory. Other F-02…F-07 steps remain individually gated.
