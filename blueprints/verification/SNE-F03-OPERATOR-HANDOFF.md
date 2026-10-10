# F-03 — Future operator/agent work handoff requirements

## Pre-dispatch answer contract

A prospective build agent must return a short **ADMISSION: BLOCKED or ELIGIBLE** response with authenticated private authorization ID, category `AUTH-B`, frozen scope hash, expiry/non-revocation, named candidate source SHA and approved paths/commands. The agent must **not** infer approval from an `APPROVED` string in a public JSON form.

An eligible scope states explicit source/submodule/dependency checkout references; VS/MSVC/Windows SDK; CMake generator/architecture and flags; network offline/allowlisted host policy; approved CMake output tree; max duration/storage; logs/private evidence location; permitted cleanup and failure stops. A missing element is BLOCKED.

## Work package completion

Evidence from actual separate work order, if ever authorized: redacted command+exit code for configure/build; source tree status before/after; versioned dependency manifest; resource and executable SHA-256; phase-specific result classification; two independent attempt records for reproducibility; reviewer discrepancy list. A build-agent self-report does not alone constitute independent G4 PASS.

`AUTH-B` does not permit gameplay or benchmark, nor code repair if compile fails. Unexpected dependency/install activity requires a new scope; do not broaden old approval.
