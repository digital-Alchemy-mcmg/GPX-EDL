# Workstation Authority and Reconciliation

**Recorded:** 2026-07-22  
**Status:** Reconciliation incomplete; implementation is gated  
**Canonical repository:** `digital-Alchemy-mcmg/GPX-EDL`

## Authority hierarchy

1. GitHub repository — canonical project and implementation authority.
2. GPT Work local project workspace — managed working copy only.
3. Local engineering repository — `F:\dpilomat-lis-envoy\GPX-EDL-main`.
4. ClickUp workspace — planning, documentation, diagrams, and roadmap references only.
5. Conversation history.
6. Uploaded files.

No lower layer supersedes a higher layer. Conflicts are resolved in favor of the committed GitHub state until a newer approved commit replaces it.

## GitHub state

- Repository URL: `https://github.com/digital-Alchemy-mcmg/GPX-EDL`
- Clone URL: `https://github.com/digital-Alchemy-mcmg/GPX-EDL.git`
- Default branch: `main`
- Audited HEAD before this reconciliation document: `b574ab45302c17857709165ad29aaee4e56359e3`
- Branches: `main` only.
- Open issues found: 0.
- Pull requests found: 0.
- Visibility: public.
- Repository is not archived.

### Audited repository tree

```text
CONTRIBUTING.md
README.md
diplomat/README.md
docs/ARCHITECTURE.md
docs/DIPLOMAT_ENVOY_ARCHITECTURE.md
docs/PIPELINE_CONTRACT.md
docs/ROADMAP.md
docs/milestone-one-constitutional-specification-v0.1.md
docs/architecture/00-system-knowledge-graph.md
docs/architecture/diplomat-constitution-contract-architecture-a5.md
docs/contracts/scout-disk-builder-v2-refactor-contract.md
docs/project/conversation-recovery-manifest.md
envoy/README.md
examples/disk-builder/compiled-machine-payload-PAY-000014.json
examples/disk-builder/disk-cartridge-CRT-000014.json
examples/disk-builder/food-service-disk-definition.json
liaison/README.md
prototypes/scout-disk-builder-v2/index.html
shared/contracts/disk-definition.schema.json
shared/contracts/pipeline-statuses.yaml
shared/contracts/promoted-listing.schema.json
shared/contracts/runner-observation.schema.json
shared/contracts/runner-spec.yaml
shared/contracts/scout-stage-mara.schema.json
shared/fixtures/runner-observation.sample.json
shared/fixtures/scout-stage-mara.sample.json
envoy-scout/DIPLOMAT DISK QUERY MECHANISM.md
envoy-scout/Disk Runner Template (YAML).md
envoy-scout/SCOUT-STAGE MARA PAYLOAD TEMPLATE.md
envoy-scout/NotebookLM Mind Map (2).png
envoy-scout/NotebookLM Mind Map (1).png
envoy-scout/NotebookLM Mind Map.png
envoy-scout/The_Deterministic_Data_Pipeline.png
envoy-scout/The_Deterministic_Data_Pipeline.zip
envoy-scout/cannon extract.txt
envoy-scout/New Text Document.txt
envoy-scout/DIPLOMAT-ENVOY Architecture.md
envoy-scout/policy instructions.txt
```

### Recent authoritative commits

1. `b574ab45302c17857709165ad29aaee4e56359e3` — recover Disk Builder artifacts and Diplomat architecture.
2. `d5b6596bf7013ddbe3620dfcdbc123e02f429999` — preserve architecture and recovery state.
3. `69fb1c30b3433ba5a8263eead513e7417a07717e` — add the frozen Milestone One constitutional specification.
4. `0c77ad7277be954ae908640ac5420178c38d9bf6` — lock the roadmap to canonical freeze and forward-only execution.

## GPT Work project state

- A local GPT Work project is registered as `GPX-EDL-main`.
- Registered project ID/path: `F:\dpilomat-lis-envoy\GPX-EDL-main`.
- It currently overlaps the Local Engineering Repository instead of providing a distinct managed clone.
- Branch: unborn `main`.
- HEAD: none.
- Synchronization with GitHub: **Fetch Blocked** by restricted outbound access to `github.com:443`.
- Existing local metadata is preserved. Implementation remains gated until a successful fetch and checkout establishes the canonical GitHub commit locally.

## Local engineering repository state

- Path: `F:\dpilomat-lis-envoy\GPX-EDL-main`.
- Existence: present.
- Git repository: initialized during reconciliation.
- Remote: `origin = https://github.com/digital-Alchemy-mcmg/GPX-EDL.git`.
- Active branch: unborn `main`.
- Local HEAD: none.
- `origin/main`: unavailable locally because the fetch was blocked.
- Staged files: 0.
- Tracked modified files: 0.
- Preserved untracked path: `GPX-EDL-main/`.
- The untracked nested path is a non-Git repository snapshot containing the audited project tree, recovered artifacts, and recovery manifest.
- Repository cleanliness: not clean.
- Divergence from GitHub cannot be calculated until `origin/main` is fetched.
- No reset, force push, deletion, overwrite, or discard was performed.

## ClickUp state

- Workspace ID: `90141253952`.
- Relevant space: `mara` (`90146156010`).
- Relevant list: `24–48 Hour Envoy + Diplomat Roadmap` (`901418281617`).
- Relevant parent task: `Implement Locked Envoy → Diplomat Pipeline` (`86bb0k4e7`).
- Seven phase tasks were found, all in `to do`.
- Recorded task dependencies: 0.
- GPX-specific diagrams or whiteboards found by search: 0.
- One constitutional specification attachment was found; its content hash was not available for comparison.

### ClickUp reconciliation

| Record | Classification | Reason |
|---|---|---|
| Phase 1 — Lock Contracts and Deterministic Fixtures | Conflicting | Cites obsolete repository `digital-Alchemy-mcmg/scout-envoy` and commit `608f25c...`, not GPX-EDL. |
| Phase 2 — Implement Envoy 1 Collection Runner | Aligned planning reference | Matches the committed deterministic Runner boundary. |
| Phase 3 — Implement Envoy 2 / SCOUT-STAGE | Aligned planning reference | Matches committed preservation and semantic payload contracts. |
| Phase 4 — Implement Zeta and Mandatory Human Promotion | Conflicting | Assigns redirect resolution and general enrichment to Zeta; GitHub defines Zeta as the Hiring Ecosystem Gap Detector and APRA owns application-authority resolution. |
| Phase 5 — Implement MARA / Diplomat Artifact Generation | Aligned planning reference | Respects human promotion and non-submission boundaries. |
| Phase 6 — Connect the Locked End-to-End Chain | Conflicting | Places SCOUT-STAGE before Zeta and omits the committed APRA accumulation sequence. |
| Phase 7 — Verify Canon Compliance and Operational Exit | Aligned planning reference | Treats GitHub canon compliance and deterministic verification as exit gates. |
| Implement Locked Envoy → Diplomat Pipeline | Conflicting | Its declared chain omits APRA and places SCOUT-STAGE before Zeta. |
| Constitutional specification attachment | Unverified | Filename matches GitHub, but no content hash was available. |

ClickUp summary: 4 aligned planning records, 4 conflicting or unsupported records, and 1 unverified attachment. ClickUp does not establish implementation state.

## Synchronization status

| Layer | State | Classification |
|---|---|---|
| GitHub | Canonical `main` available | Canonical |
| GPT Work project | Registered, no local commit; metadata preserved | Fetch Blocked |
| Local engineering repository | Unborn `main`, origin configured; metadata preserved | Fetch Blocked |
| Nested local snapshot | Preserved untracked copy | Pending reconciliation |
| ClickUp | Mixed aligned and conflicting planning records | Reference only |

External dependency: the execution environment denies outbound Git transport to `github.com:443`. The managed and local repositories are therefore classified as **Fetch Blocked**, not missing or incomplete. GitHub → GPT Work and GitHub → local synchronization could not be completed or verified. The three repositories do not yet reference the same commit.

## Divergence and missing-artifact report

- Missing canonical artifacts in GitHub: 0 identified.
- Known recovered artifacts missing from GitHub: 0.
- Unrecovered non-canonical item recorded by the recovery manifest: `ChatGPT-DIPLOMAT ! SCOUT Architecture.md`; its unreadable prior upload is not canon.
- Local uncommitted artifacts: 1 untracked nested directory containing the preserved snapshot.
- Local branch divergence: unknown until fetch succeeds.
- ClickUp conflicts: 4.
- ClickUp unverified records: 1.

## Recovery requirements

1. Enable outbound Git transport or perform an authenticated fetch outside the restricted execution environment.
2. Fetch `origin/main` without force.
3. Preserve `GPX-EDL-main/` as untracked content until its files are compared with the fetched checkout.
4. Check out local `main` tracking `origin/main` without overwriting untracked files.
5. Compare the nested snapshot to the canonical checkout and obtain operator approval before moving or deleting anything.
6. Verify GPT Work HEAD, local HEAD, and `origin/main` are identical.
7. Correct the four conflicting ClickUp records to reference GPX-EDL and the committed APRA/Zeta/SCOUT-STAGE ordering.

## Current milestone

**Milestone One — Contract Enforcement and Human Governance.**

The constitutional specification is frozen at v0.2. Schemas, deterministic validators, canonical fixtures, and cross-stage contract tests remain governed implementation work.

## Next governed action

Complete GitHub-to-local synchronization and correct the conflicting ClickUp references. No implementation or architectural redesign may begin until the managed project and local repository both resolve to GitHub `main` and the preserved nested snapshot is reconciled without data loss.
