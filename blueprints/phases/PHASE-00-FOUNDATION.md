# PHASE-00 — Foundation reconnaissance and upstream decision preparation

**ID:** SNE-P00  
**Package:** SNE-P00-FOUNDATION-0002  
**Status:** SCOPED / EVIDENCE SEEDED / NOT ACCEPTED  
**Research execution authorization:** PENDING OPERATOR APPROVAL  
**Engine implementation authorization:** NOT GRANTED  
**Upstream baseline:** UNDECIDED

## Goal

Select, with evidence, a sustainable Doom-derived engine foundation for SNE while preserving existing Sovereign Nodes FPS behavior, designing modular voxel/render/world/Mantle extensions, and respecting the Dell Latitude 5400 (i5-8365U, 16 GB, Intel UHD 620) as a low-end reference.

## Definition of research, not implementation

Phase 00 is read-only analysis of upstream sources, source licensing, existing gameplay contracts and hardware requirements. No fork, engine recompilation, binary experiment, dependency update, remote edit or gameplay refactor is authorized in this phase. Benchmarks are proposed and remain NOT RUN until separately authorized and performed on the target laptop.

## Work order sequence

| Order | Activity | Deliverable | Dependency |
|---|---|---|---|
| SNE-WO-000A | Inventory current Sovereign Nodes FPS and interfaces | compatibility inventory, reproducible source evidence | none |
| SNE-WO-000B | Candidate engine source audit | engine source map, licensing and dependencies | A recommended |
| SNE-WO-000C | Compatibility + rendering feasibility matrix | feature/test matrix; suspected extension seams | A, B |
| SNE-WO-000D | Hardware/build reproducibility plan | precise benchmark and build plan (not results) | B, C |
| SNE-WO-000E | Independent architecture review & foundation ADR proposal | decision packet, red-team review, accepted/rejected options | A–D |

## Questions to resolve

1. Which upstream revision builds reproducibly with the user's Windows/WSL toolchains?
2. Which upstream preserves `MAPINFO version "4.14"`, `addfragments`, ZScript class behavior, GLDEFS binding, existing sprite frames and three-map flow?
3. Does the upstream comply with the project's requirement to work with AI-assisted developer-authored contributions and maintainer policies?
4. How does each candidate load voxels and models, and what is an extension vs renderer rewrite?
5. What can run smoothly on UHD 620 with discrete performance profiles? Data is currently missing.
6. What degree of save-game and demo compatibility can be promised? Default answer: none beyond actual tests.
7. How should local Godot-to-Doom handoff and future Mantle Bridge be isolated from arbitrary/untrusted input?
8. What licensing notices, code/asset separation and redistribution obligations follow from the selected base?

## Required evidence packet

- `artifact-chain/intake/SNE-INT-000.md`
- `artifact-chain/evidence/SNE-EVD-000.md`
- `evidence/sources/SOURCE-INDEX.md`
- `blueprints/research/CANDIDATE-MATRIX.md`
- `blueprints/research/UPSTREAM-CODE-MAP.md`
- `blueprints/research/SOVEREIGN-NODES-INVENTORY.md`
- `blueprints/research/DEPENDENCY-LICENSE-MATRIX.md`
- `blueprints/research/COMPATIBILITY-TEST-MATRIX.md`
- `blueprints/research/HARDWARE-BENCHMARK-PLAN.md`
- `blueprints/decisions/ADR-SNE-002-FOUNDATION-PENDING.md`
- `artifact-chain/work-orders/SNE-WO-000A...E.md`
- review, verification and acceptance records

## Acceptance gates (all required)

- **P00-G1:** Every foundation candidate identified by exact repo URL and pinned Git commit or release tag, with retrieved source evidence.
- **P00-G2:** License inventory includes main license, relevant bundled components, binary/asset license obligations, and notices; any uncertainty explicitly blocks adoption.
- **P00-G3:** Existing game compatibility requirements traced to exact source paths and test scenarios; no false PASS based solely on a successful boot.
- **P00-G4:** Build dependency matrix tied to documented upstream revision and target OS; build status accurately identified as NOT RUN until evidence exists.
- **P00-G5:** UHD 620 renderer feasibility defined as testable acceptance criteria, not claimed benchmark results.
- **P00-G6:** Security boundary and Mantle data-handling threats reviewed using synthetic-only initial dataset.
- **P00-G7:** Independent review records defects, assumptions and blocking questions; operator accepts or requests revision.
- **P00-G8:** Foundation ADR records alternatives, rationale, evidence, risks, rollback and follow-on Phase 01 gate.

## Stop conditions

No engine selected on feature lists alone. No source modifications without separate approval. No sensitive genealogy data; no proprietary Doom IWADs. Any agent must not mark an unexecuted build, runtime test or licensing review as PASS.

## Next handoff

Complete P00 evidence and review → operator chooses upstream and authorizes Phase 01 upstream-baseline implementation separately.
