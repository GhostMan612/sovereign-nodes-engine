# WO-F — Evidence closure and gate promotion flow

```mermaid
flowchart TD
    A[Independent source recheck] --> B{Operator approval for task scope?}
    B -- No --> H[HOLD: no execution]
    B -- Yes --> C[Capture unchanged game and engine identities]
    C --> D[Fixture controls and C-001 custom map proof]
    D --> E{Baseline correct and recognizable?}
    E -- No --> I[Isolate original game or fixture defects]
    I --> H
    E -- Yes --> F[C-002 through C-008 per candidate]
    F --> G{Real logs and negative controls pass?}
    G -- No --> J[FAIL or BLOCKED with root-cause evidence]
    J --> H
    G -- Yes --> K[Only then: reproducible build and UHD P0 traces]
    K --> L[Licensing and security and maintenance review]
    L --> M[Independent verification and dissent resolution]
    M --> N{P00-G1 through G7 accepted?}
    N -- No --> H
    N -- Yes --> O[Operator foundation ADR decision]
    O --> P[Phase 01 separately requested]
```

The diagram describes conditional future work; it neither launches tests nor marks any G1–G8 as satisfied. `G8` remains HOLD until operator signoff.
