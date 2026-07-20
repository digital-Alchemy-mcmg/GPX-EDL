# Architecture Boundary

## Pipeline

```text
Disk Definition
  -> Envoy validation and compilation
  -> listing sourcing
  -> normalized observations
  -> Zeta outputs
  -> operator approval and selection
  -> promoted listing artifact
  -> Diplomat candidate projection
  -> submission-ready artifact
  -> Liaison stub
```

## Module independence

Envoy and Diplomat must each run independently against canonical fixtures. Their integrated mode must use the same contracts as standalone mode.

## Human authority

Listing approval, selection, and promotion remain explicit operator decisions. No module may infer approval.

## Liaison milestone boundary

Liaison accepts a validated submission package and returns a deterministic stub receipt. It does not submit applications during the initial milestone.
