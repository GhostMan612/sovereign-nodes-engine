# F-01 — Blank operator/reviewer records, deliberately unsigned

All `.json` files in this folder with prefix `SNE-F01` are **examples/blank requests**. They are not grant records, not evidence of a completed audit and not executable workflow instructions.

| Template | Purpose | Initial state |
|---|---|---|
| `SNE-F01-AUTHORIZATION.json` | one category-scoped future operator request | `PROPOSED`, `BLOCKED`, signature NULL |
| `SNE-F01-AUTHORIZATION.schema.json` | validate shape and guard missing fields | syntactic only, cannot authenticate signer |
| `SNE-F01-SCOPE-FREEZE.json` | record future digest, read/write path and guard checks | DRAFT, no execution |
| `SNE-F01-CHANGE-REQUEST.json` | request new authorization for wider/changed scope | new approval PROPOSED |
| `SNE-F01-REVOCATION.json` | record future operator stop/revoke | unfilled; not an actual revocation |
| `SNE-F01-REVIEW-ATTESTATION.json` | genuinely distinct reviewer and dissent source refs | reviewer/acceptance PENDING |

A JSON Schema PASS means structural conformance, **not** operator permission, legal adequacy, current validity or truthful evidence. It cannot check a private signature, symlinks, local OS state or active revocation. A future executor must confirm scope with the operator and reject missing/expired/modified consent. Never commit a filled record containing private system identifiers or signature data to public source control. A `scope_sha256` must cover only the canonical `scope` object; the signing method and protected reference must be separately verified.
