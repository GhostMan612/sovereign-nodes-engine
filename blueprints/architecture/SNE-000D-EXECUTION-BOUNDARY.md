# SNE-WO-000D — Execution and trust boundaries

```text
ChatGPT / research agent [read-only upstream + authored Markdown/JSON]
    ↓ reviewed ZIP, fixed-member hashes, clean-baseline guard
SNE planning repository [docs only; published by operator]
    ↓ independent review + separate written authorization
Operator Windows workstation [inventory; then user-run build if authorized]
    ↓ pinned binaries, lawful IWAD, synthetic PK3 + evidence
Controlled operator benchmark [frame traces + redacted metrics]
    ↓ independent checker, licensing + security review
WO-000E decision packet [operator accepts/blocks ADR]
```

Never collapse arrows into a single “phase passed” statement. A research SHA is not a binary SHA. A binary that launches is not a game parity PASS. A passing benchmark is not a license clearance. A documented command is not authorization to run it.

## Protective boundaries

- No edits in original `Sovereign-Nodes` monorepo, upstream engines, `.git` internals, or system configuration by this package.
- No agent-initiated Windows installation/build/game launch; user controls every future execution.
- Engine checkouts and build directories should be explicitly approved **outside the SNE planning overlay**, never automatically placed by ZIP. Windows/WSL build artifacts must not mix or silently overwrite one another.
- Actual IWAD provenance belongs in operator-private test records, not copied into public Git. Paths can reveal personal usernames; redact public reports and preserve hashes.
- Synthetic test fixture and false-name data only; no real Mantle ledger, genealogy, credentials or unsandboxed Python mods.
- Source pin plus file SHA-256 does not imply reproducible binary bit-for-bit output; document compiler, SDK, caches and timestamps separately.

The project can record a researched build recipe now and explicitly authorize controlled execution only in a future work order.
