# SCOUT Disk Builder v2 — Refactor Contract

## Baseline preserved

The application remains the existing SCOUT-family Disk Compiler with four screens: Disk Gallery, Disk Builder, Ring Mapper, and NAICS / SOC Explorer. No new top-level domain or navigation item is introduced. Existing gallery, ring colors, dark shell, chips, taxonomy exploration, and contextual ring concepts remain.

## Architectural replacement

The old Disk Builder treated the Disk object and MachinePayload JSON as editable or preview-oriented data. v2 replaces that contract with a compiler boundary:

`Disk Definition → Deterministic Compiler → Disk Cartridge`

The operator can author only the Disk Definition. No machine payload, ring result, policy expansion, compilation report, metadata, or internal compiler object is editable.

## Disk Definition schema

- Identity
  - name
  - generated slug
  - description
- Territory
  - intensity
  - ZIP codes
  - radius miles
- Industry
  - locked official NAICS selections
- Roles
  - locked official SOC selections
- Keywords
  - include
  - exclude
- Execution Profile
  - profile name
  - advanced-mode flag
  - explicit overrides

## Compiler-owned pipeline

### Stage 1 — Validate

Validates definition shape, identity, territory, taxonomy selection presence, keywords, and profile validity. Warnings are allowed; errors stop the build.

### Stage 2 — Resolve Taxonomies

Rehydrates every selected code from an authoritative provider. A selection that is absent from the provider snapshot fails. The compiler never trusts a title or code supplied only by the authoring state.

### Stage 3 — Assign Rings

Passes confirmed NAICS and SOC codes to a Ring Resolver adapter. Results are displayed read-only. Resolver provider and version are written into cartridge metadata.

### Stage 4 — Apply Policies

Expands the selected Execution Profile from a versioned policy registry. Advanced Mode applies explicit overrides after profile expansion and raises a compilation warning.

### Stage 5 — Compile Machine Payload

Produces the collector-executable payload. Arrays are deduplicated and sorted. The object is deeply frozen before being returned to the UI.

### Stage 6 — Emit Disk Cartridge

Emits the aggregate executable artifact:

1. Disk Definition snapshot
2. Compilation Report
3. Compiled Machine Payload
4. Metadata

## Adapter boundaries

### TaxonomyProvider

Required operations:

- searchIndustry(query)
- searchRoles(query)
- getIndustry(code)
- getRole(code)

The included provider uses local official snapshots. A Census/BLS service adapter can replace it without UI modification.

### RingResolver

Required operation:

- resolve(naicsCodes, socCodes)

Required metadata:

- providerId
- version

An external Ring Mapping service can replace the local mapping class without UI modification.

### PolicyResolver

Required operation:

- resolve(profileName, advancedMode, overrides)

Profiles are registry data, not UI logic.

### IdProvider

Required operation:

- allocate()

The UI does not create canonical identifiers. A Builder Studio ID service can replace the local sequence provider.

## Deterministic compilation rules

- Canonical object-key ordering
- Sorted and deduplicated arrays
- Versioned taxonomy/provider/resolver/policy inputs
- No invented taxonomy codes
- No editable compiled output
- Stable SHA-256 hash over deterministic content
- Volatile build-instance metadata excluded from the content hash

## Compilation Report contract

The report contains:

- compilation ID
- success status
- identity check
- territory check
- NAICS count
- SOC count
- unique ring count
- keyword check
- execution profile
- warnings array
- errors array

## Output ownership

Collectors receive and execute only `compiled_machine_payload`. They do not consume the authoring definition or infer missing compiler decisions.

The full Disk Cartridge is the archival, inspectable, and transferable build artifact.

## Existing-source patch map

When applying this package to the production source rather than the standalone prototype:

1. Keep the existing shell, routes, gallery cards, mapper, explorer, and reusable visual components.
2. Replace the old Disk Builder local state with Disk Definition state only.
3. Remove editable JSON and editable internal object controls.
4. Replace “Compile Payload” with the six-stage compiler runner.
5. Add Definition and Compiled Machine Payload tabs inside Disk Builder.
6. Bind existing NAICS and SOC search controls to TaxonomyProvider.
7. Bind the read-only ring panel to RingResolver output.
8. Bind execution controls to profile selection and gated Advanced Mode.
9. Persist only definitions and emitted cartridges; do not persist mutable payload drafts.
10. Send only `compiled_machine_payload` to collector execution endpoints.
