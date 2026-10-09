# Phase 00 detailed risk register

| ID | Risk | Likelihood | Impact | Mitigation | Status |
|---|---|---|---|---|---|
| R-SNE-001 | custom fork diverges from upstream | High | High | isolate patches, pin upstream, track merge cost | OPEN |
| R-SNE-002 | ZScript/MAPINFO compatibility silently fails | Medium | Critical | C-001..C-009 custom map proof, not generic boot | OPEN |
| R-SNE-003 | ZDaemon target diverges from desktop runtime | High | High | split targets and compatibility contracts | OPEN |
| R-SNE-004 | integrated Intel GPU chokes on shadows/postFX | High | High | measured quality profiles; no invented FPS | OPEN |
| R-SNE-005 | GPL/third-party obligations overlooked | Medium | Critical | pinned dependency/license audit | OPEN |
| R-SNE-006 | BiasedDoom moves away from ZScript | Medium | High | no dependency on future roadmap; keep compatibility baseline | OPEN |
| R-SNE-007 | embedded Python executes unsafe code | Medium | Critical | opt-in, trust boundary, deny untrusted scripts | OPEN |
| R-SNE-008 | Godot handoff has schema/path mismatch | Medium | High | synthetic E2E producer-consumer test | OPEN |
| R-SNE-009 | living-person data leaks into game | Medium | Critical | synthetic-only data, explicit export scope | OPEN |
| R-SNE-010 | package overwrites operator edits | Medium | High | manifest-driven overwrite and Git diff review | MITIGATED BY PROCESS |
| R-SNE-011 | physical seamless level scope expands | High | High | logical transitions first, separate R&D | OPEN |
