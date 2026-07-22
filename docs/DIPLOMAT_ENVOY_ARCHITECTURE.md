# DIPLOMAT / ENVOY Architecture

**Canonical Freeze — 2026-07-22 (v2)**

This document is the single architectural source of truth for GPX-EDL. Conflicting prior descriptions are deleted or subordinated.

## Pipeline

```text
Disk Definition
    ↓
Compiler → Certified Disk Cartridge
    ↓
Mission
    ↓
Envoy 1 (Collection Runner)
    └── identical deterministic binaries (Alpha/Bravo/Charlie/…)
          └── execute certified machine_payload only
    ↓
Normalized Observation + evidence
    ↓
Envoy 2 (SCOUT-STAGE)
    └── dual-path: preserve structured fields + atomic decomposition
    ↓
MARA-ready Semantic Observation
    ↓
Zeta
    └── deterministic enrichment + gap seeking + Ding-Dong Dash
    ↓
Human Promotion (mandatory)
    ↓
MARA / Diplomat
    ↓
Artifact
    ↓
Liaison (stubbed — user-executed only)
```

## 1. Disk System

- **Disk Definition** — human-authored mission containing territory, NAICS, SOC, Rings, inclusion/exclusion rules, and execution profile.
- **Compiler** — resolves taxonomies, assigns Rings, expands policies, and emits `machine_payload`. It never invents codes or criteria.
- **Cartridge Integrity Validator** — certifies schema, cross-references, hash, and deterministic readiness. It may perform minimal repair of interface defects only.
- **Certified Disk Cartridge** — the single executable object. Signature and hash are owned by the target-side certification contract.
- **Mission** — runtime binding of one certified cartridge to one or more Runners.

The Disk is a bounded executable instruction object, not a prompt.

## 2. Envoy 1 — Collection Runner

Runners are operatives of Envoy. They are identical deterministic binaries. Named slots differ only by the Mission, Cartridge, and adapters they receive.

### Constitution

Runners may:

- load a certified cartridge;
- collect;
- capture evidence;
- apply the exact compiled filters;
- emit normalized observations.

Runners may not:

- reason;
- infer;
- guess;
- rank;
- score;
- recommend;
- rewrite;
- summarize;
- expand keywords;
- broaden territory;
- invent criteria;
- discard valid observations.

The Compiled Machine Payload is the only execution authority.

Runner internal module contracts and failure models are explicitly resolved elsewhere and must not be redefined here.

## 3. Envoy 2 — SCOUT-STAGE

SCOUT-STAGE sits immediately after the Runner and before Zeta.

### Path A — Structured Preservation

Every Runner-supplied structured field is copied exactly. No capitalization changes, spelling fixes, format conversion, or inference of missing values are allowed.

### Path B — Semantic Decomposition

Job-description prose is reduced to atomic statements and indexed into supported semantic categories.

### Atomic-statement rules

- Exactly one explicit fact per statement.
- No pronouns.
- No interpretation or inference.
- No marketing language.
- No narrative.
- Preferences and requirements remain distinct.
- Explicit specificity is preserved.
- Duplicates are removed.

### Supported semantic categories

`employment_type`, `schedule`, `compensation`, `benefits`, `experience`, `education`, `certifications`, `leadership`, `operations`, `physical_requirements`, `working_conditions`, `skills`, `responsibilities`, `other`

Only categories containing at least one statement may be emitted.

Every category entry must be an exact string match to an entry in `atomic_statements`. Categories are an index, not a rewriting layer.

### Output contract

SCOUT-STAGE emits exactly one output observation per input observation.

Payload shape:

```text
{
  run,
  observations[]
}
```

Each observation contains only:

- `structured_fields`
- `atomic_statements`
- `semantic_categories`

No scores, rankings, recommendations, commentary, or confidence values are permitted.

SCOUT-STAGE never collects, validates Disks, ranks, scores, recommends, or enriches with external information.

## 4. Zeta

Zeta is the deterministic enrichment and differential-discovery layer.

### Authority

- Duplicate detection.
- Differential discovery and gap seeking.
- Observation comparison.
- Redirect resolution through Ding-Dong Dash.
- Application-type classification, including company-site, Workday, Indeed, and other destinations.

### Prohibitions

Zeta performs no:

- scoring;
- ranking;
- recommending;
- inference;
- rewriting;
- ATS exploration;
- artifact generation;
- automatic promotion.

### Promotion rule

Human promotion is mandatory for every observation entering MARA / Diplomat.

The promotion-object schema is owned by the receiving side and is not defined by Zeta.

## 5. MARA / Diplomat

- Receives only human-promoted observations.
- Owns projection and outward-facing artifact generation, including resumes, cover letters, profiles, and application payloads.
- Never modifies original evidence.
- Diplomat is the presentation and synthesis face of this stage.

## 6. Liaison

- Currently stubbed.
- Will be designed from primitives after Envoy and Diplomat are complete.
- Present state is a post-artifact branch executed manually by the user.
- No autonomous send, submission, or ATS interaction is live.
- Liaison primitives remain deliberately open until design begins.

## Explicitly resolved elsewhere

Do not redefine here:

- Runner internal module contracts.
- Disk certification hash and signature details.
- Promotion-object schema, owned by the receiving target.

## Still open by design

- Exact Liaison primitives.
- Future logging and event-schema refinements.
- Representation of an observation when no job description is supplied or no atomic facts can be extracted.
