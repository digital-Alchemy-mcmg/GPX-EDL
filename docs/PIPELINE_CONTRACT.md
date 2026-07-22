# GPX-EDL Deterministic Pipeline Contract

## Canonical operating chain

```text
Human intent
→ Disk Definition
→ Validate Structure
→ Resolve Taxonomies
→ Assign Rings
→ Apply Policies
→ Compile Machine Payload
→ Validate Cartridge Integrity
→ Certify Disk Cartridge
→ Envoy 1: Collection Runner
→ Normalized Runner Observations
→ Envoy 2: SCOUT-STAGE
→ MARA-ready semantic payload
→ Zeta review
→ Operator approval and selection
→ Diplomat artifact preparation
→ Liaison stub
```

## Component boundaries

### Disk Builder
Authors the human-readable Disk Definition. It does not expose compiler internals as editable authoring fields.

### Compiler
Transforms the Disk Definition into an immutable machine payload. It validates structure, resolves authoritative taxonomies, assigns rings, expands policies, generates canonical identifiers, emits the compilation report, and produces the cartridge.

The Compiler must not invent missing taxonomy codes, ring assignments, or mission requirements.

### Cartridge Integrity Validator
Validates schema, identifiers, enumerations, cross-references, contradictions, deterministic execution requirements, and the cartridge hash. It may repair only correctable interface defects. It does not redesign the mission or optimize the search strategy.

### Envoy 1 — Collection Runner
Executes one certified cartridge. The compiled machine payload is the sole execution authority. The Runner must not broaden territory, add synonyms, infer criteria, change limits, rank results unless explicitly authorized, or modify the Disk.

### Envoy 2 — SCOUT-STAGE
Receives normalized observations from Envoy 1. It preserves structured fields exactly, decomposes job prose into one-fact atomic statements, and groups those statements into supported semantic categories by exact string reference.

SCOUT-STAGE does not collect, verify, rank, recommend, score, compare, generate artifacts, or improve search quality.

### Zeta
Presents outputs for operator examination. Zeta does not silently approve or promote observations.

### Operator approval gate
Only explicitly approved and selected listings may be promoted to Diplomat.

### Diplomat
Consumes approved listings and candidate context to prepare submission artifacts. Diplomat does not source listings or bypass the operator approval gate.

### Liaison
Stubbed in the initial delivery. It accepts a submission-ready artifact package and returns a deterministic stub receipt. It performs no live submission.

## Core invariants

1. The same certified cartridge and same source state should produce the same normalized result set.
2. Every candidate passes the evaluation gates in the defined order.
3. A failed mandatory rule or blocking exclusion cannot be overridden by a positive match.
4. The Runner emits only the authorized observation fields, in the authorized order, with no narrative.
5. SCOUT-STAGE emits exactly one output observation per input observation and preserves observation order.
6. Structured fields are never rewritten by SCOUT-STAGE.
7. Every semantic-category entry must exactly match an atomic statement.
8. Promotion requires explicit operator approval.
9. Liaison remains non-operational until its real execution contract is separately approved.

## Immediate delivery target

```text
Create Disk
→ compile and certify cartridge
→ execute Envoy 1 sourcing mission
→ inspect Envoy 2 / Zeta output
→ approve and select listings
→ prepare Diplomat artifact
→ pass package to Liaison stub
```
