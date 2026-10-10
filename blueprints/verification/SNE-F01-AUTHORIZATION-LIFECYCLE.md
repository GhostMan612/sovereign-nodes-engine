# F-01 — Permission lifecycle, inheritance prohibition and reviewer separation

## Distinct phases

| Stage | Who acts | Admissible object | Result |
|---|---|---|---|
| 0 Request | planning agent or operator | draft JSON `PROPOSED` | no permission |
| 1 Independent review | qualified separate reviewer for source claims | read-only source report + dissent | source evidence only, not task permission |
| 2 Operator decision | operator | private authenticated signoff bound to digest | category-only permission if approved |
| 3 Dispatch check | future executing actor, with operator confirmation | current approval, pin, device, expiry and revocation | `ALLOW` or `BLOCKED` |
| 4 Authorized execution | distinct approved work order | exact allowed operation | real logs/results, NOT inferred PASS |
| 5 Close/revoke | operator + reviewer | artifact hashes, decision, retention | no residual authority |

## Deny-by-default state transitions

`PROPOSED → APPROVED` requires unique ID, complete frozen scope and authentic private operator decision. `PROPOSED → DENIED`; `APPROVED → REVOKED/EXPIRED/COMPLETED` always stop further action. `DENIED/REVOKED/EXPIRED/COMPLETED → APPROVED` is **not** an allowed edit: new authorization request and signoff required. An out-of-band scope change or missing actor is `BLOCKED`.

## No permission inheritance

- `AUTH-R` source read does **not** imply `AUTH-H` access to local machine, or G7 approval until a reviewer genuinely performs the work.
- `AUTH-H` metadata inventory cannot create a PK3, launch GZDoom, install tools or invoke a graphics benchmark.
- `AUTH-F` permits only its specific synthetic fixture outputs; running that fixture requires `AUTH-T` where game execution is involved.
- `AUTH-B` produces an executable only in its allowed workspace; cannot run, benchmark, package or distribute it without respective approvals.
- `AUTH-T` does not imply `AUTH-P`; `AUTH-P` does not waive game correctness C-001…C-008.
- `AUTH-S` source/legal audit is not distribution clearance (`AUTH-D`); no public license approval absent qualified review.
- `AUTH-I` and `AUTH-D` require later, separately scoped work orders outside F-01.

An operator may ask for a revised proposal without granting it. No unsigned category is activated by publication.
