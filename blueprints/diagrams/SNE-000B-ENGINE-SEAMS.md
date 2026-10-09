# SNE-WO-000B — Engine boundaries, not yet implementations

```mermaid
flowchart LR
  Fps[Existing FPS WAD PK3] --> Compat[Inherited Doom compatibility]
  Compat --> Actor[ZScript actor and HUD runtime]
  Actor --> R[Existing renderer and model API]
  Vox[VOXELDEF and voxel assets] --> R
  Gltf[Conditional glTF importer proof] --> R
  Light[GLDEFS actor light association] --> R
  Hub[Godot synthetic handoff] --> Zone[Logical zones and transitions]
  Zone --> Compat
  Safe[Redacted synthetic Mantle snapshot] --> Zone
  R --> GL[Baseline OpenGL renderer]
  R -. future evaluated .-> VK[Other backend]
```

## Diagram limitations

Logical interfaces are planning boundaries. Nothing in this diagram proves an engine can load physically adjacent WAD maps without a transition, that rendering backends are interchangeable, or that a Mantle bridge currently exists.
