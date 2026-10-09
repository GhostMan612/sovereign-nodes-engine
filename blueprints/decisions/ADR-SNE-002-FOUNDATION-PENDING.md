# ADR-SNE-002 — Upstream engine foundation (PENDING)

- Decision status: PROPOSED / NOT DECIDED
- Decision owner: operator
- Review phase: Phase 00
- Revisit after: P00-G1…G8

## Context

A Doom-derived compatibility runtime is desired with extensible voxel models, modern lighting, connected zones, and an optional isolated Mantle bridge. The existing FPS game already targets ZDoom/GZDoom-family scripting and MAPINFO semantics. Intel UHD 620 is the minimum initial hardware profile.

## Options

1. UZDoom — candidate production fork.
2. GZDoom — candidate production fork.
3. BiasedDoom — experimental reference or fork subject to ZScript roadmap/security/performance review.
4. Chocolate Doom or original Doom — source-study, generally impractical as drop-in base.
5. Fully new engine — strategic possibility; excluded for Phase 01 unless research discovers fatal fork blockers.

## Provisional preference

Shortlist **UZDoom and GZDoom**, use **BiasedDoom as an implementation reference**. This is a planning hypothesis, not an adopted decision.

## Decision data missing

- exact source commits and build toolchain constraints
- per-dependency license review
- actual Tier-A compatibility test outputs
- hardware frame-time and stability results
- upstream maintenance/diff/conflict cost estimates
- specific safe seams for custom rendering/model/world additions

## Proposed follow-on decision format

Record selected URL+commit, alternative scores with evidence references, accepted license obligations, explicit compatibility exclusions, hardware results, fallback/rollback, and Phase 01 authorized changes.

**No fork, source import, package download or build authorization follows from this ADR.**
