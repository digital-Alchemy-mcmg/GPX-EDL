# GPX-EDL

Canonical implementation repository for the Envoy, Diplomat, and Liaison architecture.

## Immediate objective

Within the initial 24–48 hour execution window, make Envoy and Diplomat independently runnable and operational as a connected pipeline:

1. Create a Disk that defines a listing-sourcing mission.
2. Source and normalize listings through Envoy.
3. Examine Zeta outputs.
4. Approve and select listings through an explicit operator gate.
5. Prepare a submission-ready artifact through Diplomat.
6. Hand the artifact to a stable Liaison stub.

## Repository boundaries

- `envoy/` — Disk compilation, sourcing orchestration, observation intake, Zeta projection, and promotion preparation.
- `diplomat/` — approved-listing intake, candidate projection, and submission-artifact preparation.
- `liaison/` — stubbed submission boundary; no autonomous submission in the initial milestone.
- `shared/contracts/` — canonical inter-module schemas and state contracts.
- `shared/fixtures/` — deterministic test payloads.
- `docs/` — accepted architecture and operating documentation.
- `tests/` — contract and end-to-end tests.

## Governing rule

The repository receives accepted architecture. It is not the place where unresolved semantics are silently normalized or invented.
