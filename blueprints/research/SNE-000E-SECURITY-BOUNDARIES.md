# WO-E — Red-team security review of gaming integration

## Attack surfaces to isolate

| Surface | Adversarial scenario | Required control evidence |
|---|---|---|
| Temporary handoff JSON | stale/replayed/future-schema file or path collision | deterministic synthetic run ID, schema/version validation, bounded parse and stale-state rejection |
| ZScript scalar parser | `true`, `false`, malformed number, nested object, overlong string | truth table and safe fail, no wrong HUD state |
| PK3/WAD/model contents | archive traversal, oversized decompression, malformed voxel/glTF | trust classification, bounded parser and observable failure |
| Embedded BiasedDoom CPython | untrusted mod reads user files or calls OS/network APIs | disabled/trusted-only; never advertise sandbox |
| Engine logs and crash dumps | private path, usernames, tokens or genealogy leaked | redaction and no real Mantle input fixture |
| Mantle integration | game script touches real graph, event ledger or vault | no direct game-privileged access; separate opt-in read-only export boundaries |
| Networking/ZDaemon | auth/mod/server surface assumed equivalent to GZDoom | separate explicitly scoped network threat model |

## Default threat posture

Offline-first by default, synthetic testing only, deny direct Mantle access, no dynamic trusted-code loading from unreviewed mods, no self-updater or third-party install script, no public logs that contain personal data. A saved JSON handoff currently lacks cryptographic integrity guarantees; do not claim signed or protected storage until actual design, key ownership and negative tests exist.

## Acceptance

Any critical control failure blocks candidate selection or any corresponding feature; non-critical scope limitations require reviewer and explicit operator risk decision. WO-E is a threat-model document and no security test is reported executed.
