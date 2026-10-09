# SNE-WO-000C — Risk register (unclosed)

Risk rankings are planning judgments, not defects proven at runtime.

| ID | Severity | Exposure | Mitigation proposal | Verification | State |
|---|---|---|---|---|---|
| C-R01 | CRITICAL | Long ORESHA/TOOL sprites possibly parsed as wrong family/frame | compare decoded frame and packed names; approved game fix only after proof | C-004a | OPEN |
| C-R02 | CRITICAL | JSON bool `hasParadox` decoded through integer scanner | explicit synthetic bool fixture; design typed v2 parse | H-02/H-03 | OPEN |
| C-R03 | HIGH | Old/new schema tolerated without integrity/freshness | ADR on v2 validation, replay protection and v1 migration | H-04..H-10 | OPEN |
| C-R04 | HIGH | Vanilla Entryway fallback mistaken for project success | unique custom map marker and scripted interaction | C-001 | OPEN |
| C-R05 | HIGH | GLDEFS defined but not attached/visible | render on/off control; log and sprite truth | C-005 | OPEN |
| C-R06 | HIGH | BiasedDoom glTF asset loading fails on embedded textures | external-texture positive control, GLB separate case | C-011b | OPEN |
| C-R07 | HIGH | Untrusted Python mods gain process filesystem/network access | disabled/untrusted scripts blocked; threat model first | SEC-003 | OPEN |
| C-R08 | HIGH | GPU thermal throttling and frame-time spikes | 3-run 720p capture and measured profile downgrade | PERF-001 | OPEN |
| C-R09 | HIGH | Engine fork breaks save/map/HUD behavior | full Tier-A parity before new visuals | C-001..009 | OPEN |
| C-R10 | HIGH | World megamap overpromised as current hub support | W1..W4 terminology, separate ADR for W4 | W-001..004 | OPEN |
| C-R11 | HIGH | ZDaemon compatibility inferred from GZDoom behavior | independent ZDaemon test lane | C-014 | OPEN |
| C-R12 | HIGH | Proprietary assets or real lineage accidentally committed | synthetic fixtures, no IWAD copying, filtered logs | S-001 | OPEN |
| C-R13 | MEDIUM | Cross-engine benchmark differences mistaken for fair comparison | fixed PK3/hash, driver and route; note backend variations | PERF-001 | OPEN |
| C-R14 | MEDIUM | New docs overwrite dirty local work | clean baseline SHA and explicit preimage checks | install gate | OPEN |

## Escalation

A CRITICAL or HIGH issue with insufficient proof remains a HOLD, not a silent waiver. Only the operator may approve an exception, with independent review and explicit rationale. Engine ADR remains blocked until source, licensing, runtime and performance evidence exists.
