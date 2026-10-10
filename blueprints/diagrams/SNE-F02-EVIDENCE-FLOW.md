# F-02 — Evidence and authorization dependency graph

```mermaid
flowchart TD
    A[F-01 templates published] --> B{Authenticated operator approval?}
    B -->|No| STOP[BLOCKED / no work]
    B -->|AUTH-R| R[Pinned source recheck]
    B -->|AUTH-H| H[Read-only host / original artifact inventory]
    H --> C{Verified B0 PK3 and legal IWAD reference?}
    C -->|No| HOLD[BLOCKED for runtime]
    C -->|Yes| T{Separate AUTH-T?}
    B -->|AUTH-F| F[Disposable B1 / B2 fixture creation]
    F --> T
    T -->|No| N[NOT RUN]
    T -->|Yes + lawful inputs| X[Future C-series runtime controls]
    X --> V[Independent review and negative controls]
    V --> G[G1/G3/G6 evidence ledger]
    R --> V
    G --> Z[ADR remains HOLD until G1–G7 complete]
```

A source claim, a static package layout, an independently signed review and a gameplay result are distinct types of evidence. This diagram is a proposed process, not an executed graph.
