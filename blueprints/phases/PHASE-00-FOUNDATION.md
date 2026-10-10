# PHASE-00 — Foundation research, evidence closure, and engine decision

- ID: `SNE-P00`; status **A–E DOCUMENTATION PUBLISHED / EVIDENCE GATES OPEN**.
- Research work orders A–E are published and not thereby independently accepted; WO-000F v0.8.0 is a **readiness overlay**, not a technical result.
- Candidate foundation: **UNDECIDED**; `ADR-SNE-002` **HOLD**; Phase 01 implementation: **NOT AUTHORIZED**.
- Gate authority: operator, with independent reviewer input. A package author cannot independently certify their own findings.

## Product contract

Retain existing Sovereign Nodes FPS PK3/WAD, `MAPINFO version "4.14"`, three `addfragments`, ZScript actors and HUD, `GLDEFS` lights, Godot→Doom synthetic handoff, and MAP01→MAP02→MAP03 while evaluating voxels, selective glTF, controlled lighting and persistent logical zones. The reported minimum reference device is Dell Latitude 5400 (i5-8365U, 16 GB RAM, UHD 620). Nothing measured on that device is implied by this document.

## Published documentation chain

| Order | Scope | Git publication checkpoint | Formal acceptance |
|---|---|---|---|
| SNE-WO-000A | Reconnaissance | `369722f` | PENDING |
| SNE-WO-000B | Engine source audit | `edc274f` | PENDING |
| SNE-WO-000C | Compatibility and rendering plan | `706db57` | PENDING |
| SNE-WO-000D | Windows build and UHD 620 protocols | `1f21e4c` | PENDING |
| SNE-WO-000E | Red-team decision packet | `1644fb8` | PENDING |
| SNE-WO-000F | Evidence-closure **readiness** and authorization design | v0.8.0 overlay; not yet published | PENDING |

## Eight acceptance gates

`P00-G1` provenance; `G2` licensing and asset rights; `G3` C-001…C-008 actual game parity; `G4` reproducible Windows build; `G5` measured UHD 620 frame times; `G6` synthetic handoff and Python/Mantle security; `G7` truly independent review; `G8` operator-selected foundation with rollback. See `governance/PHASE-00-REVIEW-GATES.md`.

## Evidence-closure sequence (proposed, not authorized)

1. `F-00`: appoint independent reviewer; confirm exact frozen A–E source pins and identify stale references.
2. `F-01`: operator explicitly authorizes *only the desired category* of work (read-only inventory, fixture creation, build, or runtime). No category implies the next.
3. `F-02`: validate official lawful resource identity, actual PK3/WAD provenance, custom MAP01 marker and source-game sprite/handoff hypotheses in **disposable fixtures**.
4. `F-03`: record Windows/MSVC/SDK/driver before operator-run candidate build. Builds belong to a separate authorized work order and workspace.
5. `F-04`: run C-001…C-008 on unchanged game, per candidate; classify source-game versus fork regressions with exact logs and hashes.
6. `F-05`: only parity-qualified candidates advance to controlled UHD 620 P0 and optional graphics experiments; keep off-repo raw traces.
7. `F-06`: independently complete SBOM/asset/branding review, security threat checks, and maintenance plan.
8. `F-07`: independent review and operator signoff on each gate; only afterward reopen ADR and separately authorize Phase 01.

## Boundary and stop conditions

- Documentation ZIPs contain Markdown/JSON only; no new engine code, game edits, installers, binaries, proprietary IWADs, private genealogy, vault exports, secrets, or conversation transcripts.
- `F-00…F-07` are planning labels, not active task dispatches. Neither reading nor installing this overlay authorizes a build, game run or source modification.
- A source-identified problem is not a measured failure. An untested feature is `NOT RUN`; an absent test is never `PASS`.
- Level hubs and serial map changes do not prove simultaneous world streaming or physical seamless rendering.
- UZDoom's upstream contribution rules are separate from GPL downstream fork rights and trademark/asset rights.
- If a local Git preimage differs or an added path already exists, **STOP** rather than silently overwrite.

## Exit

Phase 00 cannot be closed by WO-000F publication. Hold ADR-SNE-002 and require independently checked G1–G8 evidence plus operator acceptance before any foundation decision.
