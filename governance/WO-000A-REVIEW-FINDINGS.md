# Architecture review — WO-000A

**Reviewer:** assistant author/first-pass critic
**Independence:** NOT MET; independent reviewer/operator must inspect.
**Status:** OPEN findings, no acceptance.

## Findings

| ID | Severity | Finding | Remedy / evidence gate |
|---|---|---|---|
| R-A01 | HIGH | Engine may load base IWAD MAP01 despite missing custom fragments; startup logs alone can mislead | Positive custom-map marker and actor proof |
| R-A02 | HIGH | Source declares handoff v1, but behavior and defensive validation not proved | Synthetic end-to-end and malformed-input tests |
| R-A03 | HIGH | Handoff carries ancestor identity/relationship; unsafe for real genealogy in research | Test-only synthetic data; separate redaction and signed snapshot for Mantle Bridge |
| R-A04 | MEDIUM | `build_pk3.py` crosschecks only selected schema/asset conventions; static check is not engine parser | Actual PK3 inspect, engine loader and gameplay proof |
| R-A05 | MEDIUM | `validate_wads.py` has generator-specific header layout requirement | Do not elevate to format-wide compatibility claim |
| R-A06 | HIGH | UZDoom upstream disallows AI-contributed PRs | Treat as contribution limitation, not GPL use revocation |
| R-A07 | HIGH | BiasedDoom Python allows trusted arbitrary code; not sandboxed | Off by default, no untrusted code or private Mantle data |
| R-A08 | MEDIUM | BiasedDoom conditional glTF feature means binaries may omit loader | Verify configuration/feature and model rendering on target GPU |
| R-A09 | HIGH | No UHD 620 measurements yet | Block candidate performance claims |
| R-A10 | MEDIUM | Only selected project files reviewed, map binaries/PK3 unseen | Complete WO-000A inventory before approval |

## Independent review checklist

- [ ] Replicate evidence links against revision SHAs.
- [ ] Challenge missing load-bearing files and gameplay paths.
- [ ] Confirm source observations are not being reported as tests.
- [ ] Assign risk owners and resolve high-impact omissions.
- [ ] Receive operator approval or request revisions.
