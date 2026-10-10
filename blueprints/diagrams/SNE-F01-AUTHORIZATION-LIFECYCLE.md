# F-01 — Proposal, approval and execution gate graph

```mermaid
flowchart TD
    A[Draft proposed task request] --> B[Freeze exact scope and hash]
    B --> C{Independent preconditions met?}
    C -->|No| H[HOLD or revise request]
    C -->|Yes| D{Operator authenticates approval?}
    D -->|No| H
    D -->|Yes| E{At dispatch: valid unrevoked scope?}
    E -->|No| H
    E -->|Yes| F[Only separately approved future task]
    F --> G[Collect redacted evidence and stop on deviation]
    G --> I[Independent evidence review]
    I --> J[Operator accepts or holds gate]
    J --> K{All required G1 to G7 closed?}
    K -->|No| H
    K -->|Yes| L[Separate signed G8 ADR decision]
    L --> M[Separate Phase 01 request, not automatic]
```

No state is transitioned by reading/extracting this package. In particular, the existence of a `templates/*AUTHORIZATION.json` object is not proof of a signed approval or independent review.
