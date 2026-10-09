# Mantle and gameplay security boundaries — Phase 00 research

## Explicit trust model

- Sovereign Mantle private graph/ledger/vault: external trusted authoritative system, **not accessible directly to game renderer/scripts**.
- Export adapter: allowlisted, explicit operator-approved, strips personal or private data.
- Snapshot/importer: bounded schema and sizes, no dynamic code execution, rejects invalid signatures and versions when signature support exists.
- Godot→Doom handoff: separate existing game protocol with synthetic test payloads, no assumption of cryptographic integrity.
- Python and mod script support: engine scripts can be more privileged than game data; no untrusted script execution without isolated, verified threat model.

## Risk checklist

| Threat | Mitigation candidate | Evidence gate |
|---|---|---|
| Real-person lineage leaked into games/saves/logs | synthetic only; data minimization, explicit export consent | security test S-001 |
| Malicious snapshot path escape | no arbitrary file paths; canonical root; bounded parse | S-002 |
| Replay/tamper handoff | schema stamp, size limits, run ID, integrity protection per design | S-003 |
| Python mod gains unrestricted OS access | opt-in/trusted author only; OS-level restriction if needed | S-004 |
| Game mutates authoritative Mantle ledger | read-only bridge API, separate processes/principals | S-005 |
| Untrusted resource decompression bomb | archive size/count bounds and limits | S-006 |

The exported game-safe graph is fictionalized/synthetic by default. This document is a threat-model starting point, **not** a completed security assessment.
