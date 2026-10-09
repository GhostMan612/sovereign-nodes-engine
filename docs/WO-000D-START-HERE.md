# WO-000D v0.6.0 — Operator entry point

## Scope

This is **planning and source-backed verification design**, not executable engine work. It advances the Windows/UHD 620 decision packet without installing dependencies or running the game. The existing original `GhostMan612/Sovereign-Nodes` repo is read-only.

## Read in order

1. `WO-000D-INSTALL.md`: ZIP extraction, fixed Git baseline and explicit staging verification.
2. `artifact-chain/work-orders/SNE-WO-000D.md`: authority boundaries and acceptance definition.
3. `evidence/sources/SNE-000D-PIN-LEDGER.md`: exact upstream source revisions, file/line observations.
4. `blueprints/research/SNE-000D-BUILD-LANE-MATRIX.md` + `SNE-000D-CMAKE-OPTIONS.md`: Windows-specific configuration differences.
5. `blueprints/research/SNE-000D-DEPENDENCY-LOCK-PROTOCOL.md` and security/license matrix.
6. `blueprints/research/HARDWARE-BENCHMARK-PLAN.md` + `SNE-000D-MEASUREMENT-SOP.md` + `SNE-000D-TEST-SCENES.md`.
7. `templates/SNE-000D-*.json`: sample *blank* operator evidence records; unknown values intentionally `null`.
8. `governance/WO-000D-RISK-REGISTER.md`, verification, acceptance and independent reviewer files.

## What v0.6.0 cannot establish

We cannot tell yet if a particular Windows native compiler is present, which renderer API is supported on this UHD 620 driver, whether any fork builds without errors, whether source game scripts run, or which engine is faster. WO-000E may prepare a **conditional** ADR but must not force a foundation choice without tests and operator acceptance.

## Prior source pins

SNE planning baseline `706db57` is distinct from original game commit `44034e9`, GZDoom `c26ce2e`, UZDoom `dbedcc8`, and BiasedDoom `6147e06`. Independent full-source and asset licensing review still needed.
