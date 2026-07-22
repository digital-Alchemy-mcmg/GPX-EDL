# GPX-EDL Forward Implementation Roadmap

## Governing authority

`docs/DIPLOMAT_ENVOY_ARCHITECTURE.md` — **Canonical Freeze 2026-07-22 v2** is the single source of truth.

The architecture is complete and authoritative. Roadmap work must implement or add to the frozen design. It must not reopen, reinterpret, or replace settled component definitions.

## Locked pipeline

```text
Disk Definition
→ Compiler
→ Certified Disk Cartridge
→ Mission
→ Envoy 1 (Collection Runner)
→ Normalized Observation + evidence
→ Envoy 2 (SCOUT-STAGE)
→ MARA-ready Semantic Observation
→ Zeta
→ Human Promotion
→ MARA / Diplomat
→ Artifact
→ Liaison
```

## Roadmap rules

1. New work is additive only.
2. Stage order, ownership, authority, and prohibitions are fixed.
3. No task may introduce automatic promotion or bypass the human promotion gate.
4. No task may merge Envoy 2 with Zeta or assign Zeta artifact-generation authority.
5. Envoy is the formal name; SCOUT survives only in the locked name `SCOUT-STAGE` and historical references explicitly marked as legacy.
6. Do not reintroduce ARL Zeta, Layer-0 kernels, Truth Gravity, email-as-bus, or related retired architecture.
7. Do not redefine Runner internal contracts, Disk certification hash/signature details, or the receiving-side promotion schema where ownership is already resolved elsewhere.
8. Unknown implementation details must remain unresolved until their owning contract is supplied. They must not be filled through architectural invention.

## Milestone 1 — Contract enforcement

- Make the canonical architecture document the governing repository reference.
- Validate schemas against the locked stage boundaries.
- Add deterministic Envoy 1 and Envoy 2 fixtures.
- Add tests for stage order, immutable fields, observation ordering, category integrity, and the mandatory promotion gate.
- Add a retired-concept scan for active code and documentation.

### Exit gate

The repository rejects payloads and flows that contradict the freeze.

## Milestone 2 — Disk and Mission execution

- Accept and validate a Disk Definition.
- Resolve taxonomies, assign Rings, apply policies, and compile the machine payload deterministically.
- Validate cartridge integrity and certify the Disk Cartridge.
- Bind one certified cartridge to one or more Runner slots through a Mission.

### Exit gate

A certified cartridge can be bound to a Mission without exposing compiler internals as Runner discretion.

## Milestone 3 — Envoy 1 operational

- Load the certified machine payload as the sole execution authority.
- Execute exact compiled filters through assigned adapters.
- Capture source evidence.
- Emit normalized observations in the governed shape.
- Preserve target-side failure and rejection contracts.

### Exit gate

The same certified cartridge and source state produce the same normalized result set, subject only to explicitly represented source-state changes.

## Milestone 4 — Envoy 2 / SCOUT-STAGE operational

- Preserve every Runner-supplied structured field exactly.
- Decompose source prose into one-fact atomic statements under the locked rules.
- Index statements into supported semantic categories by exact string match.
- Emit exactly one semantic observation per input observation.
- Preserve input order.

### Exit gate

Fixture comparison proves deterministic preservation, decomposition, and category integrity.

## Milestone 5 — Zeta and Human Promotion operational

- Implement duplicate detection.
- Implement differential discovery and gap seeking.
- Implement observation comparison.
- Implement redirect resolution through Ding-Dong Dash.
- Implement application-type classification.
- Enforce all Zeta prohibitions.
- Require an explicit human promotion action before MARA / Diplomat intake.

### Exit gate

No observation reaches MARA / Diplomat without a recorded human promotion action.

## Milestone 6 — MARA / Diplomat operational

- Accept only human-promoted observations.
- Combine promoted observations with governed candidate source material.
- Produce requested outward-facing artifacts.
- Preserve original evidence unchanged and traceable.
- Validate artifact completeness and evidence support.

### Exit gate

A promoted observation produces a traceable artifact without changing preserved evidence.

## Milestone 7 — Locked-chain integration

- Connect every stage through its governed input/output contract.
- Preserve identifiers, field values, observation order, semantic statements, categories, and evidence across handoffs.
- Reject missing certification, malformed observations, invalid semantic payloads, absent promotion, and invalid artifact inputs.
- Stop at the Liaison user-executed boundary.

### Exit gate

A bounded end-to-end run completes:

```text
Disk Definition
→ Certified Disk Cartridge
→ Mission
→ Envoy 1 output
→ Envoy 2 output
→ Zeta enrichment
→ Human Promotion
→ MARA / Diplomat artifact
→ Liaison boundary
```

## Future milestones

Future work may extend adapters, deterministic tests, Zeta enrichment capabilities within its frozen authority, MARA / Diplomat artifact types, observability, or Liaison primitives after joint design.

Every future milestone must state:

- which locked stage it extends;
- which existing input/output contract it preserves;
- what new additive capability it introduces;
- what human approval boundary applies;
- how regression against retired architecture is prevented.

Exploratory branches on settled architecture are not roadmap work.