# F-03 — Conditional build-gate dependency graph

```mermaid
flowchart TD
    A[Published F02 blueprint] --> B{Signed AUTH-H?}
    B -->|No| HOLD[STOP / BLOCKED]
    B -->|Yes| I[Read-only host inventory]
    I --> R{Toolchain facts and dependency rights known?}
    R -->|No| HOLD
    R -->|Yes| G{Independent source review objections reconciled?}
    G -->|No| HOLD
    G -->|Yes| P{Separate signed AUTH-B for one candidate?}
    P -->|No| HOLD
    P -->|Yes| C[Isolated CMake configure]
    C --> D[Compiler / link / resource evidence]
    D --> E[Repeat build in isolated tree]
    E --> F{Review G4 evidence}
    F -->|Incomplete| HOLD
    F -->|Complete| NEXT[Request separate AUTH-T for F04]
    NEXT --> ADR[ADR remains HOLD until all G1-G7 and operator G8]
```

Arrows represent **conditional prerequisites**, not permission or commands for an agent. Independent reviewer must be distinct from author; a source-claim review does not replace a measured G4 review.
