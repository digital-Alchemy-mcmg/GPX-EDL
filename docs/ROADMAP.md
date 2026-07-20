# 24–48 Hour Roadmap

## Exit gate

The milestone passes when a Disk can initiate sourcing, Zeta outputs can be inspected, a listing can be explicitly approved and selected, Diplomat can generate a submission-ready artifact, and Liaison can accept it through a stable stub contract.

## Phase 1 — Repository and contracts

- Establish module boundaries.
- Freeze shared identifiers, statuses, and rejection states.
- Add deterministic fixtures and contract-test harness.

## Phase 2 — Envoy standalone

- Accept and validate a Disk Definition.
- Compile a deterministic Disk Cartridge.
- Accept normalized listing observations.
- Produce inspectable Zeta output.
- Emit promotion candidates only after operator approval.

## Phase 3 — Diplomat standalone

- Accept a promoted listing artifact and candidate source profile.
- Produce a candidate projection.
- Generate a submission-ready artifact package.
- Reject incomplete or unapproved inputs deterministically.

## Phase 4 — Integrated pipeline

- Run Envoy to promotion.
- Hand the promoted artifact to Diplomat without field rewriting.
- Send the completed submission package to Liaison stub.
- Record a complete trace for the run.
