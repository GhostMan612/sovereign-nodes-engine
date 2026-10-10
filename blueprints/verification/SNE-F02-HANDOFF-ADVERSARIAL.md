# F-02B — Synthetic malformed, stale, schema and path negative controls

| ID | Input variation | Required observation / stop case |
|---|---|---|
| H-N01 | no handoff file | standalone FPS safely starts, no fabricated ancestor identity |
| H-N02 | schema missing | actual current consumer warns/tolerates; record exact behavior, never claim strict rejection |
| H-N03 | schema 999 | source suggests warning/tolerant read; verify actual behavior rather than spec rewriting |
| H-N04 | duplicate `hasParadox` keys | record first/last scanner match, no trust upgrade |
| H-N05 | truncated/unclosed quotes or escaped quote | bounded read; no crash, partial state behavior identified |
| H-N06 | stale runId/issuedAt | measure acceptance vs rejection; current source does **not** prove freshness |
| H-N07 | oversized line/file | bound and stop; no unbounded stress/DoS test without explicit duration/size limit |
| H-N08 | temp env unset or path inaccessible | no fallback into private Mantle directory; document actual path choice safely |
| H-N09 | unexpected nested JSON object in scalar | record ScanRaw handling and partial-default semantics |

All payloads are synthetic, explicitly approved `AUTH-F` outputs; any live gameplay / parser use requires separate `AUTH-T`. Do not place actual test payload or raw personal temp path in public docs. Older schema tolerant behavior is a compatibility choice; versioned fail-closed v2 requires a **separately approved protocol ADR**, not silent test-time change.
