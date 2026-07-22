# DIPLOMAT Ecosystem — Constitution / Contract Architecture — A5
Core principle: every intelligent node gets exactly two objects.
- **Constitution** = permanent behavior. Almost never changes.
- **Contract** = run-specific instructions. Changes every run.
Knowledge Graph nodes are the exception — they get **Schemas**, not contracts.

================================================================
## MINIMUM CONSTITUTION TEMPLATE (every node)
================================================================
```
Node Identity
Mission
Authority
Inputs
Accessible Graph Scope
Processing Rules
Prohibited Actions
Output Schema
Success Conditions
Failure Conditions
Logging Rules
Version
```

## MINIMUM RUNTIME CONTRACT TEMPLATE (every node)
```
Run ID
Task ID
Artifact ID
Inputs
Objectives
Constraints
Permissions
Deliverables
Completion Criteria
```

================================================================
## NODE: DIPLOMAT (formerly MARA) — top-level orchestration authority
================================================================
**Constitution**
- Identity, Mission, Authority Boundaries, Projection Rules, Candidate Safety Rules, Evidence Rules, Graph Access Rules, Artifact Standards, Escalation Rules, Success Metrics

**Runtime Contract**
- Candidate, Job, Projection Objective, Target Company, Target Industry, Output Artifacts

*Cross-reference: matches the DIPLOMAT constitution fields already extracted in A4 (Identity/Mission/Authority/Scope/Processing Rules/Prohibited Actions/Failure Conditions/Escalation/Logging were 🟢 EXTRACTED from your notebooks — Success Criteria and Version were 🟡 inferred gaps. This new template gives those gaps a proper home.)*

----------------------------------------------------------------
## NODE: AG (Orchestrator)
----------------------------------------------------------------
**Constitution**
- Workflow Rules, State Management Rules, Packet Rules, Retry Rules, Failure Rules, Ordering Rules, Logging Rules, Security Rules

**Runtime Contract**
- Pipeline Definition, Worker List, Packet Definitions, Execution Order, Success Conditions

----------------------------------------------------------------
## NODE: Extractor / Curator
----------------------------------------------------------------
**Constitution**
- Evidence Selection Rules, Translation Rules, Deduplication Rules, Priority Rules, No Hallucination Rules, Output Schema

**Runtime Contract**
- Accessible Graph Nodes, Projection Goals, Required Evidence, Deliverables

----------------------------------------------------------------
## NODE: Writer
----------------------------------------------------------------
**Constitution**
- Writing Standards, Formatting Standards, Tone Rules, Bullet Construction Rules, No Fabrication Rules, No Unauthorized Access Rules, Output Schema
- Core rule: the Writer never asks "is this good?" — only "can I produce this section from my inputs?"

**Runtime Contract**
- Evidence Package, Projection Policy, Formatting Profile, Narrative Goals, Section Assignment

**Design separation:** Knowledge and Presentation are split. Same Evidence Package can render under different Formatting Profiles without touching content logic.

Example Formatting Profile packet (not hardcoded in prompt — delivered as data):
```
Document Type: Resume
Layout: Modern Executive
Section Order: Summary, Experience, Education, Skills
Bullet Style: Achievement-based
Reading Level: Grade 10
```

----------------------------------------------------------------
## NODE: Cover Letter Writer
----------------------------------------------------------------
**Constitution**
- Narrative Rules, Thesis Rules, Voice Rules, Length Rules, No Unsupported Claims Rules

**Runtime Contract**
- Cover Letter Posture, Target Company, Narrative Theme, Call To Action, Supporting Evidence

----------------------------------------------------------------
## NODE: Connector / Translator
----------------------------------------------------------------
**Constitution**
- Skill Mapping Rules, Experience Translation Rules, O*NET Mapping Rules, Industry Translation Rules, No Unsupported Inference Rules

**Runtime Contract**
- Candidate DNA, Job DNA, Projection Goal, Target Industry

----------------------------------------------------------------
## NODE: Verifier — the auditor, gets the widest access of any node
----------------------------------------------------------------
**Constitution**
- Evidence Verification Rules, Policy Verification Rules, Traceability Rules, Hallucination Detection Rules, Artifact Acceptance Rules, Rejection Rules

**Runtime Contract**
- Projection Contract, Candidate Graph, Job Graph, Artifact, Verification Objectives

**Access:** Candidate Graph + Job Graph + Projection Contract + Evidence Packages + Final Artifact — full visibility, because the Verifier's question is categorically different from the Writer's:
> Writer asks: "Can I produce this section from my inputs?"
> Verifier asks: "Should this artifact leave the factory?"

**Verification Stack (Verifier likely splits into sub-verifiers):**
1. **Evidence Verification** — every claim → is it supported by evidence?
2. **Policy Verification** — did the Writer violate Diplomat's posture?
3. **Job Alignment Verification** — did the artifact fulfill the *projection objective*, not keyword-match the posting. Example: job requires Leadership / Budget Management / Operational Excellence → projection policy positions candidate as Operations Executive → verifier checks each requirement has supporting evidence, not that every keyword appears. This is distinct from ATS matching.
4. **ATS Verification** — separate node, keyword/parseability only
5. **Formatting Verification** — separate node, layout/export only

Likely real-world split: **Evidence Verifier, Policy Verifier, ATS Verifier, Formatting Verifier, Narrative Verifier** — five distinct sub-nodes rather than one monolithic Verifier.

----------------------------------------------------------------
## NODE: ATS Verifier
----------------------------------------------------------------
**Constitution**
- Parseability Rules, Formatting Rules, Section Rules, Keyword Rules, Compatibility Rules

**Runtime Contract**
- Target ATS Profile, Artifact, Job Requirements

----------------------------------------------------------------
## NODE: Formatting Agent
----------------------------------------------------------------
**Constitution**
- Layout Rules, Typography Rules, Document Standards, Export Standards

**Runtime Contract**
- Formatting Profile, Artifact Type, Output Type

----------------------------------------------------------------
## NODE: Company / FirmStep Liaison
----------------------------------------------------------------
**Constitution**
- Research Rules, Company Analysis Rules, Mission Extraction Rules, Communication Rules

**Runtime Contract**
- Company Profile, Job Posting, Projection Policy, Requested Artifact

================================================================
## KNOWLEDGE GRAPH NODES — Schemas, not Contracts
================================================================
No constitution, no contract. These are pure data structures the intelligent nodes read from.

**Candidate DNA Schema**
```
Identity, Experience, Skills, Metrics, Certifications, Preferences, Traits, Interests
```

**Job DNA Schema**
```
Requirements, Skills, Responsibilities, Culture Signals, Industry Signals
```

**O*NET Schema**
```
Skills, Abilities, Knowledge, Work Activities, Technology, Interests, Work Styles
```

================================================================
## SYSTEM SHAPE
================================================================
```
DIPLOMAT
    ↓
Projection Contract
    ↓
AG (Orchestrator)
    ↓
Workers (Extractor, Writer, Cover Letter Writer, Connector, FirmStep Liaison)
    ↓
Verification Stack
        ├── Evidence
        ├── Policy
        ├── Job Alignment
        ├── ATS
        └── Formatting
```

**First-class citizen rule:** every Node = `Constitution + Contract`. Once that pairing is consistent across all nodes, AG can orchestrate any of them the same way — same invocation pattern, same packet shape, regardless of which worker it's calling.

================================================================
## OPEN ITEMS CARRIED FROM A4 SYNTHESIS
================================================================
- Diplomat / Envoy root version numbers — still unfilled, plug into `Version` field above
- Success Criteria for Diplomat/Envoy — inferred proposals from A4 need your approval, then plug into `Success Conditions`
- The L1–L4 post-MARA lifecycle layer (state machine, SQL triggers, tick loop) found in your notebooks doesn't map to any single node here — it looks like AG's Constitution (State Management Rules / Packet Rules) plus its own Runtime Contract, worth confirming as its own node or folding into AG
