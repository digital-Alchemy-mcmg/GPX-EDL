# DIPLOMAT / SCOUT — Milestone One Constitutional Specification

**Version:** 0.2 — Frozen Constitutional Contract  
**Milestone:** Milestone One — Contract Enforcement and Human Governance  
**Status:** Constitutional questions Q1–Q8 resolved  
**Constitutional completion:** 100%  
**Implementation status:** Validators, schemas, fixtures, and contract tests remain governed implementation work

## 1. Purpose and Authority

This document formalizes the constitutional contracts required for Milestone One. It governs runner observations, Source Platforms, APRA application-route resolution, Zeta hiring-ecosystem gap detection, accumulated staging rows, operator review, reference archiving, and deterministic enforcement.

The constitutional layer is frozen when these rules are approved. Milestone One implementation is complete only when the frozen rules are represented by machine-readable schemas, deterministic validators, canonical fixtures, and passing contract tests.

## 2. Frozen Operational Chain

Disk Definition → Compiler → Certified Disk Cartridge → Mission → Source-Platform Runner → APRA append → Zeta append → Complete Accumulated Row → Operator Review Gate → SCOUT-STAGE → DIPLOMAT / MARA → Artifact → Liaison.

No downstream stage reconstructs missing evidence backward. The complete accumulated row is the authoritative evidence record. When a fact is absent from the row, the system does not possess that fact.

## 3. Source Platform and Runner Contract

### 3.1 Source Platform

A **Source Platform** is any platform that publishes a hiring inventory for discovery by a runner.

Examples include:

- Indeed
- LinkedIn Jobs
- ZipRecruiter
- Wizehire
- Patrice & Associates
- Goodwin Recruiting
- Gecko Hospitality
- an employer-owned careers platform used as the target of a company-specific disk

Aggregators and recruiters occupy the same architectural class. Their operational difference is whether they own the application or redirect the applicant elsewhere.

Each runner owns exactly one Source Platform or one company-target set defined by its certified Disk Cartridge.

### 3.2 Runner Jurisdiction

A runner discovers, captures, and normalizes observations only within the jurisdiction defined by its certified Disk Cartridge and mission, including:

- geography and radius
- industry and mandatory NAICS scope
- role and employment filters
- inclusion and exclusion rules
- source-of-truth requirements
- structured return contract

A runner must not expand its own source ecosystem, weaken jurisdiction, or infer permission beyond the disk.

### 3.3 Result Ceiling

- Every runner returns a maximum of **15 valid observations per mission**.
- Fifteen is a ceiling and an optimization target, not permission to lower quality.
- The runner should maximize the batch toward 15 qualifying results.
- The mission stops when 15 valid observations have been returned or the bounded search space is exhausted.
- When more than 15 valid observations exist, selection follows the deterministic ranking encoded by the mission or Disk Cartridge.
- No universal ranking may be invented outside the mission contract.
- Scaling occurs through additional runners, disks, or missions, not by increasing the ceiling.

## 4. Observation and Accumulated-Row Contract

Each runner observation is a posting-level, evidence-backed record. It preserves required structured fields and evidence without inference or narrative drift.

Minimum observation fields include:

- Observation ID
- Mission ID
- Disk ID
- Source Platform
- Employer
- Job Title
- Geography
- Posting URL
- Collection timestamp
- NAICS
- required SOT codes and source fields
- evidence supporting every returned field
- normalized structured fields required by the mission

APRA and Zeta append their authorized findings to this same row. The row advances forward as one accumulated record. SCOUT-STAGE receives that record as authoritative input and does not reconstruct prior stages.

## 5. APRA — Application-Path Resolution Authority

### 5.1 Purpose

APRA determines the authoritative application authority for an observation.

APRA answers only:

> Apply here.

APRA follows the route only far enough to identify the platform or organization that owns the application. It does not submit applications, complete forms, create accounts, execute Liaison work, or create new runners.

### 5.2 Stopping Boundary — Q1

APRA stops immediately when the authoritative application authority is identified.

Examples:

- Employer careers site → stop at employer authority
- Patrice & Associates → stop at Patrice & Associates
- Goodwin Recruiting → stop at Goodwin Recruiting
- Gecko Hospitality → stop at Gecko Hospitality
- Indeed-native application → stop at Indeed
- Redirect from Indeed to Workday → stop at Workday

APRA records the authority and movement completion. Discovery of a useful recruiter does not expand the runner ecosystem. Only the operator may later form a new disk assigning that recruiter as a Source Platform.

### 5.3 Route Outcomes

- **Native:** the source platform owns the application.
- **Redirect:** the source platform transfers the applicant to another application authority.
- **Company Direct:** the employer owns the application.
- **Recruitment Authority:** a recruiter owns the application.
- **Unresolved:** the authority cannot be established within bounded execution.

### 5.4 Retry and Failure Policy — Q2

APRA performs bounded route resolution only. It may use the retry allowance encoded by the mission or runtime contract. It must not loop indefinitely or invent a destination.

When the route remains blocked, unavailable, or ambiguous after the bounded allowance, APRA appends an **Unresolved** status and supporting note. The absence of route resolution does not create an automatic promotion decision; it is presented to the operator at Q7.

### 5.5 Required APRA Fields

- APRA Route Type
- APRA Application Authority
- APRA Destination
- APRA Status
- APRA Checked At
- APRA Note or flag when unresolved or inconsistent

## 6. Zeta — Hiring Ecosystem Gap Detector

### 6.1 Canonical Purpose

Zeta is not a general coverage verifier. Zeta identifies employers that are hiring but are absent from, or materially underrepresented in, the certified Source Platform ecosystem used by the mission.

Conceptually:

**Companies Hiring − Companies Visible Through Certified Source Platforms = Zeta Gap**

Zeta prevents employers from being forgotten merely because they do not advertise primarily through aggregators or currently certified recruiter platforms.

### 6.2 Exclusion Identity — Q3

Zeta compares hiring identities against the accumulated runner returns for the same mission.

The constitutional identity is the employer or hiring identity within the bounded mission geography. A company represented by the certified Source Platform returns belongs to the exclusion set. An employer not represented becomes a gap candidate.

The comparison does not require an exhaustive corporate identity graph. It uses only evidence available from the bounded result and the mission-defined normalization rules.

### 6.3 Multi-Location Rule — Q4

Within the mission radius, multiple locations belonging to the same hiring identity constitute **one Zeta investigation**.

Example:

Burger King locations in Dearborn, Redford, Livonia, and Taylor within the mission radius are one investigation.

One qualifying location is sufficient to establish that the employer belongs in the hiring-ecosystem gap. Zeta does not exhaustively enumerate every branch. Separate investigation is justified only when returned evidence establishes a materially distinct hiring identity, such as a different franchise operator or independently controlled application system.

### 6.4 Zeta Return Contract

Zeta returns the same operational structure required to form a disk. It does not return a narrative report and does not browse beyond what is necessary to extract the available result fields.

The return includes, when supported by the result:

- employer or hiring identity
- geography
- mandatory NAICS
- SOT codes
- source fields
- source URL
- other disk-compatible mission fields

A Zeta return without NAICS is not disk-compatible.

### 6.5 Company-Targeted Disks

The operator may assign a Zeta gap result the **Form Disk** disposition.

That decision creates a new company-target set. New runners then search the identified companies—such as Valve or Corewell—instead of searching an aggregator. These runners remain subject to the same certified disk, jurisdiction, evidence, and 15-result constraints as all other runners.

### 6.6 Zeta Result Ceiling — Q8

Zeta has the same constraints as the rest of the runners and maximizes toward **15 valid gap results**.

Zeta stops when:

- 15 qualifying gap results have been returned, or
- the bounded search space has been exhausted and fewer than 15 qualifying results exist.

Zeta does not need to exhaustively classify every employer in the market before the mission can complete.

## 7. APRA Outcomes and Promotion Blocking — Q5

APRA does not promote, reject, defer, or automatically block a row. APRA appends evidence and status to the accumulated row.

No APRA outcome independently determines disposition. An unresolved, blocked, inconsistent, or successful APRA result is presented to the operator at the review gate. Deterministic validators may flag malformed or contract-invalid data, but the operational disposition remains human-controlled.

## 8. Selection Above 15 — Q6

When a runner or Zeta encounters more than 15 valid candidates, it returns the best deterministic 15 according to ranking rules encoded in the certified Disk Cartridge or mission.

The constitution does not impose one universal ranking model across all disks. A mission that lacks a deterministic ranking rule is incomplete and must not silently substitute model preference, source order, or narrative judgment.

## 9. Q7 — Operator Review Gate

Q7 occurs only after the runner, APRA, and Zeta have completed their authorized appends and the complete accumulated row is available.

The operator reviews that row and assigns exactly one operational disposition:

1. **Promote**  
   Advance the row to SCOUT-STAGE and the DIPLOMAT / MARA chain.

2. **Form Disk**  
   Use the row's employer, NAICS, geography, SOT codes, sources, and other supported fields as input to a new disk-building workflow.

3. **Reject — Error**  
   Reject because the row is invalid, corrupted, improperly collected, unsupported, or contract-noncompliant.

4. **Reject — No Error**  
   Reject a valid row because it is unwanted, out of scope, redundant, already covered, or otherwise not actionable.

5. **Pending / Standby**  
   Preserve the row without advancing it until the operator makes a later decision.

No component may infer the operator's disposition.

### 9.1 Reference Archive

Every reviewed row is archived for reference by default.

The only reference override is:

- **Do Not Archive for Reference**

When checked, the row follows its operational disposition but is excluded from the reference corpus.

Operational disposition and reference archival are independent dimensions.

### 9.2 Notes

Each reviewed row includes a **Notes** field.

The operator may enter short text identifying anything specific that should be examined when the row is later used:

- as reference material
- as an approved or rejected example
- for learning from the observation
- for interpreting an unusual decision

Notes are operator-authored guidance. They do not alter, rewrite, or replace the source evidence.

## 10. Deterministic Validator Contract

Milestone One requires deterministic enforcement of:

- object schema validity
- required-field presence
- mandatory NAICS where required
- runner and Zeta maximum of 15
- jurisdictional compliance
- evidence presence and structural validity
- observation preservation across appends
- accumulated-row integrity
- Zeta exclusion-set integrity
- hiring-identity deduplication
- APRA bounded execution and field validity
- operator-only disposition authority
- archive-default and exclusion-override behavior
- cross-stage contract compatibility
- deterministic error reporting

Validators enforce contracts. They do not replace operator judgment or reconstruct missing facts.

## 11. Canonical Fixtures and Contract Tests

Implementation must include valid and invalid fixtures covering:

- normal runner returns
- fewer than 15 valid results
- more than 15 valid results with deterministic ranking
- malformed observations
- missing evidence
- missing NAICS
- duplicate hiring identities
- branch-heavy chains
- distinct franchise operators
- APRA native, redirect, company-direct, recruiter-owned, blocked, and unresolved routes
- attempted APRA expansion of the runner ecosystem
- Zeta gap and covered-employer cases
- company-targeted disk formation
- every Q7 disposition
- default reference archival
- Do Not Archive for Reference override
- Notes preservation
- attempted downstream reconstruction
- attempted promotion without operator authority

## 12. Milestone One Acceptance Criteria

1. Runner, Source Platform, Observation, accumulated-row, Zeta, APRA, Q7, archive, and validator contracts are written and versioned.
2. Constitutional questions Q1–Q8 are resolved.
3. Machine-readable schemas exist for governed objects.
4. Deterministic validators exist for each governed contract.
5. Canonical valid and invalid fixtures exist.
6. Cross-stage contract tests pass.
7. No component can promote or reject outside the Operator Review Gate.
8. No component reconstructs absent evidence backward.
9. A milestone enforcement gate blocks nonconforming implementations.

## 13. Constitutional Resolution Register

| Question | Resolution |
|---|---|
| Q1 — APRA stopping boundary | Stop at the first identified authoritative application authority. |
| Q2 — APRA retry and failure | Bounded by mission/runtime allowance; unresolved after exhaustion; no invention or infinite looping. |
| Q3 — Zeta exclusion identity | Employer or hiring identity within the mission, using bounded normalized evidence. |
| Q4 — Multi-location exception | One hiring identity within the radius equals one investigation unless evidence proves materially distinct hiring control. |
| Q5 — Promotion blocking | APRA never determines disposition; all outcomes go to operator review. |
| Q6 — Selection above 15 | Use deterministic disk/mission ranking; no universal inferred ranking. |
| Q7 — Operator decision taxonomy | Promote, Form Disk, Reject—Error, Reject—No Error, Pending/Standby; archive by default; optional Do Not Archive override; Notes field. |
| Q8 — Zeta ceiling | Same 15-result ceiling and bounded-exhaustion stopping rule as other runners. |

## 14. Immediate Next Action

Implement or update the machine-readable schemas, deterministic validators, fixtures, and contract tests against this frozen constitutional contract. Any implementation conflict must be returned for operator reconciliation rather than resolved through inference.