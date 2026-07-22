# Envoy

Envoy is the collection and normalization system. It has two ordered stages followed by Zeta.

```text
Mission + Certified Disk Cartridge
→ Envoy 1: Collection Runner
→ Normalized Observation + evidence
→ Envoy 2: SCOUT-STAGE
→ MARA-ready Semantic Observation
→ Zeta
```

## Envoy 1 — Collection Runner

Runners are identical deterministic binaries. Named slots such as Alpha, Bravo, Charlie, and Delta differ only by the Mission, certified cartridge, and adapters assigned to them.

### Input

- Mission
- certified Disk Cartridge
- assigned source adapters

### Output

- normalized observations
- captured evidence

### Authority

Envoy 1 may load the certified cartridge, execute the compiled machine payload, collect, capture evidence, apply exact compiled filters, normalize, and emit.

Envoy 1 may not reason, infer, guess, rank, score, recommend, rewrite, summarize, expand keywords, broaden territory, invent criteria, alter the Disk, or discard valid observations.

The compiled machine payload is the sole execution authority.

Runner internal module contracts and failure models are resolved elsewhere and must not be redefined in this repository without their authoritative source.

## Envoy 2 — SCOUT-STAGE

SCOUT-STAGE receives normalized observations immediately after Envoy 1 and before Zeta.

### Input

- normalized Runner observation
- source job-description prose when supplied

### Output

Exactly one MARA-ready semantic observation per input observation, containing only:

- `structured_fields`
- `atomic_statements`
- `semantic_categories`

### Authority

SCOUT-STAGE copies all Runner-supplied structured fields exactly. It decomposes explicit source prose into one-fact atomic statements and indexes those statements into supported semantic categories by exact string match.

SCOUT-STAGE never collects, validates Disks, enriches externally, ranks, scores, recommends, compares, rewrites structured fields, or generates artifacts.

## Zeta boundary

Zeta is not another name for Envoy and is not merely an inspection projection. It follows SCOUT-STAGE as the deterministic enrichment and differential-discovery layer.

Zeta may perform duplicate detection, differential discovery, observation comparison, redirect resolution, and application-type classification. It may not automatically promote an observation.

Every observation entering MARA / Diplomat requires explicit human promotion.
