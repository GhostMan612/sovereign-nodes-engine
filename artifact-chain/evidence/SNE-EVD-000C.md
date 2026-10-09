# SNE-EVD-000C — Curated compatibility and feasibility evidence

- Author: architecture/source reconnaissance
- Collection date: 2026-10-09
- Mode: remote GitHub read-only; no engine build, launch or live GPU test
- Base: `edc274f320cbd891c1f7fcef80f308562c0067ef`
- Source review pins: `evidence/sources/SNE-000C-PIN-LEDGER.md`
- Evidence class: **SOURCE-OBSERVED** (code lines), **DOC-CLAIM** (maintainer prose), **INFERENCE** (risks), **NOT RUN** (runtime)

## Findings

| ID | Class | Finding | Source record | Confidence and gap |
|---|---|---|---|---|
| EV-C01 | SOURCE | MAPINFO lists three custom maps and three ZScript fragments | SNE-SRC-GAME-003 | static; runtime resolution unproven |
| EV-C02 | SOURCE | GLDEFS declares pointlights and names long frame bindings | SNE-SRC-GAME-003 | static; actual rendered lights unproven |
| EV-C03 | SOURCE + INFERENCE | GZDoom sprite parser indexes 4-char base plus frame/rotation while game uses long names | SNE-SRC-GZDOOM-003, GAME-003 | high-risk discrepancy; needs actual PK3 test |
| EV-C04 | SOURCE + INFERENCE | Producer's `hasParadox` is JSON bool; receiver calls `ScanInt` | SNE-SRC-GAME-003 | needs boolean truth-table execution |
| EV-C05 | SOURCE | Handoff schema is warning-tolerant for absent/newer stamps | SNE-SRC-GAME-003 | cannot report current strict rejection |
| EV-C06 | SOURCE | GZDoom and UZDoom have VOXELDEF and sprite/voxel integration | SNE-SRC-GZDOOM-003, UZDOOM-003 | extension seam; actor visuals NOT RUN |
| EV-C07 | DOC + SOURCE | BiasedDoom glTF/fastgltf available conditionally, but external textures recommended | SNE-SRC-BIASEDDOOM-003 | compiled features and embedded image path NOT RUN |
| EV-C08 | DOC | BiasedDoom Python is unsandboxed trusted-code execution | SNE-SRC-BIASEDDOOM-003 | no permission to enable |
| EV-C09 | SOURCE | GZDoom and UZDoom contain map-change and hub-state code | SNE-SRC-GZDOOM-003, UZDOOM-003 | logical transitions != multi-map stream |
| EV-C10 | PLAN ONLY | 720p benchmark profiles and light count sweeps defined | HARDWARE-BENCHMARK-PLAN.md | UHD 620: **NO MEASUREMENTS** |

## Scope constraints

No complete class-level game inventory, no binary test, no authoritatively validated third-party IWAD content and no exhaustive license evaluation. Any previously reported game build green status is historical and cannot satisfy a new-engine parity check.

## Preservation

Curated technical observations only. No pasted assistant/agent conversations, personal ancestor names, secrets, private snapshots, raw session logs or copyrighted IWADs.
