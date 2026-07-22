# GPX-EDL Deterministic Pipeline Contract

This contract implements the governing architecture in `docs/DIPLOMAT_ENVOY_ARCHITECTURE.md`.

## Canonical operating chain

```text
Disk Definition
→ Validate Structure
→ Resolve Taxonomies
→ Assign Rings
→ Apply Policies
→ Compile Machine Payload
→ Validate Cartridge Integrity
→ Certify Disk Cartridge
→ Mission
→ Envoy 1: Collection Runner
→ Normalized Observation + evidence
→ Envoy 2: SCOUT-STAGE
→ MARA-ready Semantic Observation
→ Zeta deterministic enrichment
→ Human Promotion
→ MARA / Diplomat
→ Outward-facing Artifact
→ Liaison stub
```

## Component boundaries

### Disk Builder

Authors the human-readable Disk Definition containing territory, NAICS, SOC, Rings, inclusion/exclusion rules, and execution profile. It does not expose compiler internals as editable authoring fields.

### Compiler

Transforms the Disk Definition into an immutable executable machine payload. It validates structure, resolves authoritative taxonomies, assigns Rings, expands policies, generates canonical identifiers, and emits the compilation report.

The Compiler must not invent missing taxonomy codes, ring assignments, criteria, or mission requirements.

### Cartridge Integrity Validator

Validates schema, identifiers, enumerations, cross-references, contradictions, deterministic readiness, and cartridge integrity. It may repair only correctable interface defects. It does not redesign the mission or optimize the search strategy.

### Certified Disk Cartridge

The single executable instruction object. It is bounded and immutable after certification. It is not a prompt.

### Mission

Binds one certified cartridge to one or more Runners with the required territory, limits, schedule, and adapters.

### Envoy 1 — Collection Runner

Executes one certified cartridge. The compiled machine payload is the sole execution authority.

A Runner may load, collect, capture evidence, apply exact compiled filters, normalize, and emit.

A Runner may not reason, infer, guess, rank, score, recommend, rewrite, summarize, expand keywords, broaden territory, invent criteria, or discard valid observations.

Runner internal module contracts and failure models are governed elsewhere and are not redefined by this repository document.

### Envoy 2 — SCOUT-STAGE

Receives normalized observations from Envoy 1.

It performs two paths:

1. Exact structured-field preservation.
2. Atomic decomposition of source prose into one-fact statements indexed into supported semantic categories.

SCOUT-STAGE emits exactly one output observation per input observation. Every semantic-category value must exactly match an entry in `atomic_statements`.

SCOUT-STAGE does not collect, validate Disks, compare observations, enrich from external information, rank, recommend, score, or generate artifacts.

### Zeta

Zeta is the deterministic enrichment and differential-discovery layer.

Its authority is limited to:

- duplicate detection;
- differential discovery and gap seeking;
- observation comparison;
- redirect resolution through Ding-Dong Dash;
- application-type classification.

Zeta does not score, rank, recommend, infer, rewrite, explore ATS systems, generate artifacts, or promote automatically.

### Human promotion gate

Every observation entering MARA / Diplomat requires explicit human promotion. Zeta does not own the receiving-side promotion-object schema.

### MARA / Diplomat

Receives only human-promoted observations. This stage owns projection and outward-facing artifact generation, including resumes, cover letters, profiles, and application payloads.

Original evidence remains immutable. Diplomat is the presentation and synthesis face of the MARA stage.

### Liaison

Liaison is currently stubbed. The present branch is user-executed after artifact generation. No autonomous send, submission, ATS interaction, or external communication is live.

## Core invariants

1. The Disk is a bounded executable instruction object, not a prompt.
2. The Compiled Machine Payload is the Runner's only execution authority.
3. Named Runner slots are identical binaries and differ only by Mission, Cartridge, and adapters.
4. The Runner cannot broaden or reinterpret the mission.
5. SCOUT-STAGE preserves every structured field exactly.
6. SCOUT-STAGE emits exactly one output observation per input observation.
7. Every semantic-category entry exactly matches an atomic statement.
8. Zeta enriches and compares deterministically but never performs semantic judgment.
9. Human promotion is mandatory before MARA / Diplomat.
10. Original evidence is never modified.
11. Liaison remains non-operational until separately designed and approved.

## Resolved elsewhere

The following are authoritative but intentionally not redefined here:

- Runner internal module contracts and failure models.
- Disk certification hash and signature details.
- Promotion-object schema owned by the receiving side.

## Open by design

- Exact Liaison primitives.
- Future logging and event-schema refinements.
- SCOUT-STAGE representation when no job description exists or no atomic facts can be extracted.

## Immediate delivery target

```text
Create Disk Definition
→ compile and certify cartridge
→ bind Mission
→ execute Envoy 1 sourcing run
→ transform through Envoy 2
→ enrich and inspect in Zeta
→ human-promote selected observations
→ prepare Diplomat artifact
→ pass artifact to Liaison stub for manual execution
```
