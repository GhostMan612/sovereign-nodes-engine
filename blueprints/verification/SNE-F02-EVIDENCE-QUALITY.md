# F-02 — Case evidence quality, schema and privacy checks

## Record identity required for any future result

`case_id`, `authorization_id`, private authenticated `scope_digest`, `execution_timestamp`, `game_sha`, `original_pk3_sha256`, `fixture_class`, `fixture_sha256`, `legal_external_iwad_private_ref`, `engine_source_sha`, `engine_binary_sha256`, `device_alias`, `command_or_procedure`, `expected_observation`, `actual_observation`, `negative_control`, `artifact_sha256`, `reviewer_id`, `operator_disposition`.

Do not fill engine fields for static-only tests. A `null` value is more correct than an invented hash. `SOURCE-OBSERVED` ≠ `RUN PASS`; a screenshot of idle FPS ≠ live frame trace; a generated ZIP existing ≠ playable custom map.

## Three evidence layers

1. **Source observation:** exact immutable Git commit, file path, blob SHA-1 and line/symbol. Does not prove installation.
2. **Static artifact:** actual original source-game generated PK3/WAD and SHA-256, legal reference, archive validation logs; no runtime behavior claim.
3. **Runtime:** separately signed `AUTH-T` session, actual engine binary+PK3+IWAD identities, unique custom map proof, negative controls and signed review.

## Redaction and retention

Raw stdout can reveal home directories, user accounts, external WAD paths and private credentials. Keep in approved private storage, publish only minimal sanitized summary, opaque signature/private resource refs and SHA-256. Do not dump private Mantle tree, medical/legal/genealogy data, real `ancestorName`, local screenshots containing personal data or copyrighted IWAD bytes. Expiry does not authorize recursive deletion.

Results in this package: all static and runtime `NOT RUN`, host versions `UNKNOWN`, rights `NOT CLEARED`, external review `PENDING`.
