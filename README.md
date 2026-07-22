# GPX-EDL

Canonical implementation repository for the DIPLOMAT / ENVOY architecture.

The governing architecture is frozen in `docs/DIPLOMAT_ENVOY_ARCHITECTURE.md`. Other repository documents must conform to it and may not redefine resolved boundaries.

## Canonical pipeline

```text
Disk Definition
→ Compiler
→ Certified Disk Cartridge
→ Mission
→ Envoy 1: Collection Runner
→ Normalized Observation + evidence
→ Envoy 2: SCOUT-STAGE
→ MARA-ready Semantic Observation
→ Zeta
→ Human Promotion
→ MARA / Diplomat
→ Artifact
→ Liaison stub / user-executed branch
```

## Immediate objective

1. Create and compile a Disk Definition.
2. Bind the certified cartridge to a Mission.
3. Execute Envoy 1 and emit normalized observations with evidence.
4. Execute Envoy 2 and emit MARA-ready semantic observations.
5. Run Zeta enrichment and differential discovery.
6. Promote selected observations through the mandatory human gate.
7. Prepare an outward-facing artifact through MARA / Diplomat.
8. Stop at the Liaison stub for manual user execution.

## Repository boundaries

- `envoy/` — Envoy 1 collection execution and Envoy 2 SCOUT-STAGE transformation. Zeta follows Envoy 2 as a separate deterministic enrichment layer.
- `diplomat/` — receiving-side intake of human-promoted observations, candidate projection, and outward-facing artifact generation.
- `liaison/` — deliberately stubbed post-artifact branch; no autonomous external action.
- `shared/contracts/` — accepted inter-component schemas. Contracts resolved elsewhere must be imported, not reconstructed.
- `shared/fixtures/` — deterministic test payloads.
- `docs/` — accepted architecture and operating documentation.
- `tests/` — contract and end-to-end tests.

## Governing rules

- The compiled machine payload is the sole execution authority for Envoy 1.
- SCOUT-STAGE preserves structured fields exactly and performs no enrichment.
- Zeta enriches and seeks gaps but does not score, rank, recommend, rewrite, or promote.
- Human promotion is mandatory before MARA / Diplomat.
- Original evidence is never modified.
- Liaison remains non-autonomous until separately designed and approved.
- The repository receives accepted architecture. It is not the place where unresolved semantics are silently normalized or invented.
