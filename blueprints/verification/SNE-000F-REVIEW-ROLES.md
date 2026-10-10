# WO-F — Independence, ownership and conflict-of-interest specification

## Distinct roles

| Role | May do | Must not do |
|---|---|---|
| Package author | source read, architecture design, file/ZIP validation, propose hypotheses | approve own independent review or invent measured outcomes |
| Operator | approve exact scope, choose paths and test limits, perform/run delegated work, own Git and ADR | treat ZIP publication as automatic engine permission |
| Game tester | execute only approved game test fixtures, capture logs and negative controls | silently patch original game for parity |
| Build tester | configure/compile only approved source and toolchain | install globally, change OS security, pull arbitrary dependencies |
| Hardware tester | capture controlled UHD 620 traces and reproducibility details | fabricate FPS or compare absent assets |
| Security reviewer | challenge handoff/temp replay and Python/Mantle threats | use real private data in public fixtures |
| Rights reviewer | evaluate GPL, asset brands, bundled dependencies and release terms | infer IWAD redistribution rights from engine code license |
| Independent architecture reviewer | primary-source and evidence review; record dissent and alternative recommendation | copy author's conclusion unexamined |

## Independent review acceptance

Record reviewer's identity in **private signed record**, or use a reviewed non-identifying identifier for public summary; also document qualification/role, date, exact source links, sample size/selection, corrections and dissent. Reviewer must be separate from research author, with independent source checking. A different model paraphrasing the same evidence is not automatically an independent audit.

## Escalation

Critical claim mismatch, exposed user data, no lawful test resource, revoked authorization, source alteration or missing proof → HOLD and operator decision; no default continuation. A rejected hypothesis stays documented with the counterevidence and affected gate IDs.
