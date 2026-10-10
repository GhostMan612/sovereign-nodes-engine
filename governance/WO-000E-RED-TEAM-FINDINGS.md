# WO-E — Author red-team findings (NOT independent review)

- Reviewer role: **research packet author**; independence: **NO**.
- Scope: contradictions and hidden assumptions in documented A–D evidence.
- Result: HOLD foundation selection; recommend GZDoom as a future P0 control *experiment* only.

| Finding ID | Severity | Observation | Required correction before decision |
|---|---|---|---|
| RT-01 | CRITICAL | WO-A/B/C/D published while individual acceptance records remain NOT ACCEPTED | distinguish Git publication from independent/operator signoff |
| RT-02 | CRITICAL | custom game boot may mask IWAD fallback | C-001 exact GapNode identity proof; negative control |
| RT-03 | CRITICAL | long sprite frame strings risk GZDoom parsing/GLDEFS mismatch | C-004/C-005 fixture and actual actor proof |
| RT-04 | CRITICAL | `hasParadox` boolean may be scanned as integer | C-006/C-015 synthetic truth table, schema/path/staleness |
| RT-05 | CRITICAL | no Windows builds or game runs have been performed | operator-only native build and per-engine Tier-A suite |
| RT-06 | CRITICAL | no actual UHD 620 frame traces | 3+ runs with identical scene and environment |
| RT-07 | CRITICAL | full transitive asset/component license review absent | SBOM and independent redistribution clearance |
| RT-08 | HIGH | independent reviewer not named, author self-review could appear authoritative | signed outside-author review with retained dissent |
| RT-09 | HIGH | glTF code path does not prove GLB textures, animation or runtime support | BiasedDoom flag/fixture/correctness proof |
| RT-10 | HIGH | `g_hub` and map change do not provide physical seamless streaming | W1/W2 vs W3/W4 explicit split |
| RT-11 | HIGH | UZDoom's AI upstream policy conflated with GPL downstream rights | separate policy and licensing review |
| RT-12 | HIGH | optional embedded Python has native filesystem/process authority | disabled, trusted-only baseline; security audit |
| RT-13 | HIGH | a fast vanilla map would produce false benchmark score | require custom-map marker and render-output parity |
| RT-14 | MEDIUM | historical WO-A checksum reconciliation not independently checked | sample hash verification from committed blobs |
| RT-15 | MEDIUM | weighted rankings now would be subjective and misleading | score fields remain blank, predefined rubric |

## Adversarial counterarguments to preference

- A source-content bug common to all engines could make GZDoom-first appear uniquely broken or healthy; require unchanged PK3 plus disposable controlled fixture.
- An engine with a simpler documented CMake script could still fail on Windows due to bundled resources; no build has passed.
- A renderer that omits lights/models could falsely appear faster; compare output correctness and timed scene identity.
- Newer/older engine release could change plugin policies or C++ toolchain; exact source pins matter.

**Disposition:** Reviewer needed. This author-issued document is not P00-G7 and author cannot approve own ADR.
