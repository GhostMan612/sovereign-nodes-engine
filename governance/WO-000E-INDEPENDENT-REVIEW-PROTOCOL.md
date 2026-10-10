# WO-E — Real independent architecture review handoff

## Appointment requirement

A reviewer must not be the author of the A–E package or an agent simply restating its conclusions. A distinct qualified person/team (or independently conducted audit with distinct evidence collection, explicitly labeled limitations) must examine primary source, installed overlay, test protocols, rights and residual risks. If none exists, mark **PENDING**, not 'independent review complete'. The operator remains final acceptance authority.

## Scope and assigned tests

1. Verify random sample and all high-risk source citations against immutable Git files, especially GZDoom sprite prefix, game handoff ScanInt and BiasedDoom conditional feature flags.
2. Challenge the preliminary GZDoom control-first hypothesis. Identify strongest evidence that would make UZDoom or BiasedDoom preferable.
3. Confirm current WO-D commands are merely gated prototypes and do not leak secrets, install globally or conflate CMake generators.
4. Inspect asset/CDN/submodule dependency/source license and branding risks; identify missing transitive SBOM rows.
5. Evaluate target UHD 620 benchmark fairness, VSync, power/thermal, shader warmup and gameplay fixture proof.
6. Check every G1–G8 gate can close only with independently reviewable evidence and operator approval.
7. Challenge logical continuity W1/W2 vs simultaneous W4 and rollback feasibility.

## Evidence standards

For each finding record: reviewer's identity/qualification (stored privately if desired), date, pinned source link/path, finding severity, assertion, observed data, correction requested, owner disposition, dissent, and revisit status. Use `templates/SNE-000E-REVIEW-RECORD.json`; redact personal identifiers before any public repo copy. A counterclaim should link concrete source/run evidence.

## Independence stops

Self-review cannot close G7; an unverified third-party statement cannot satisfy G2/G3; a missing or deferred reviewer is a HOLD. Independent approval of *documentation quality* is not actual Windows/game/graphics proof, and operator cannot implicitly authorize engine implementation by accepting the packet.
