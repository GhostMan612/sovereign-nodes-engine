# IF-SNE-002 — Optional Mantle snapshot interface (DRAFT)

This is NOT the existing Godot→Doom handoff schema. Do not conflate them.

## Trust boundary

Export adapter outside game → validated synthetic/game-safe immutable snapshot → local, read-only game import → derived mission representation. No ledger writeback, no network requirement, no uncontrolled import of persons.

## Proposed envelope (schema to be designed later)

- `schemaVersion`: explicit positive integer
- `snapshotId`: opaque ID, not a real-person ID
- `generatedAt`: ISO 8601 timestamp
- `payloadType`: finite enumerated types
- `payloadHash`: content digest; signature only if a trusted key/signature scheme is implemented and verified
- `nodes`, `edges`: restricted game-safe fields and count limits

All fields and limits are **proposal only**. No schema parser or signature verifier exists in this package. Threat review required before implementation.
