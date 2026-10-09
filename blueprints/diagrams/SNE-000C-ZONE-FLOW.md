# SNE-WO-000C — World continuum stages

```mermaid
flowchart LR
    M1[MAP01 GapNode] -->|MAPINFO next| M2[MAP02 Breach]
    M2 -->|MAPINFO next| M3[MAP03 Warren]
    M1 -.-> S[Versioned logical transition snapshot]
    M2 -.-> S
    M3 -.-> S
    S -.-> Z[Proposed Zone Registry]
    Z -.-> P[Proposed prefetch/fade presentation]
    P -.-> C[Future multi-zone renderer + simulation ADR]
```

Solid arrows are **source-declared map links**, not tested progress. Dotted arrows are **design proposals**. Continuous physics/render state between maps is not an inherited guarantee.
