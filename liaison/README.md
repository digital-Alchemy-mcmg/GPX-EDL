# Liaison

Liaison is stubbed during the initial milestone.

It accepts a validated submission package and emits a deterministic receipt proving that the Envoy → Diplomat pipeline reached the submission boundary.

## Initial behavior

- validate the package envelope;
- record the package identifier and receipt time;
- return `accepted_by_stub` or a deterministic rejection;
- perform no external submission.
