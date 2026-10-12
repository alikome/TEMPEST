# MISSION SPINE

[Back to wiki](../README.md)

## Purpose

Mission Spine gathers the mission's checkpoints, evidence, tasks, target setup, training controls, and approval receipts into one expandable view. Its subtitle describes these as “Recorder, proof, tasks, target intake, and training range folded into one operator surface.”

The section starts collapsed. Expand reveals six panels.

## Header Controls

| Control | What it does |
|---|---|
| Expand / Collapse | Shows or hides the six panels. It does not start or stop execution. |
| Refresh | Redraws Mission Spine using the currently loaded browser state. This button does not itself fetch fresh backend records or refresh scope receipts. |
| Bundle | Requests a structured mission handoff bundle from the backend and updates the bundle/reproduction displays. It also invokes an automatic self-heal pass. The handler does not automatically download a ZIP or report file. |
| Field Drill | Runs a workflow smoke check through the backend, creating practice records and testing gates. It is an action, not a passive status refresh. |

## Flight Recorder

This panel displays six checkpoints in a fixed order:

| Checkpoint | What it summarizes |
|---|---|
| Scope | The current target, or a request to clarify it. |
| Route Preview | Whether a mission draft is present and which family it uses. |
| Tool Plan | How many planned specialist/tool steps are loaded. |
| Evidence | Evidence and finding counts. |
| Retest | Passed and unresolved retest counts. |
| Gate | The current gate status and score out of 100. |

Despite the name, this display is a checkpoint summary, not a timestamped history of every command. Its gate status uses the same snapshot logic as the Operator Clarity Layer, including a provisional browser summary when no backend gate result has been loaded.

## Evidence Workbench

This is a compact preview of findings and supporting artifacts. The item count includes both findings and evidence records.

The preview shows up to three findings, followed by enough evidence entries to fill four rows. Findings display a title, status or severity, and an available proof reference. Evidence entries display a title and available type/source information.

With no entries, the panel asks you to collect a log, diff, screenshot, canary, or fixture. The preview does not open artifacts or verify their contents. A green finding row or the fallback text “evidence linked” is not independent proof that a finding has been validated.

## Work Order Board

The board summarizes tasks in four categories:

| Category | Meaning |
|---|---|
| Open | Work orders whose status is neither completed nor blocked. |
| Receipt | Work orders marked as needing a receipt or requiring approval. |
| Running | Work orders marked running, active, or in progress. |
| Done | Work orders marked completed. The supporting text can also mention blocked items. |

These counts overlap: a running task is also open, and a receipt-requiring task can appear in another category. Do not add the four numbers to calculate total tasks. The board is a status display; it has no task-execution or drag-and-drop controls.

## Target Intake

This panel summarizes the selected target, mission family, current authority/gate issue, and Arsenal readiness.

| Button | Behavior |
|---|---|
| Target | Focuses and scrolls to the main target field. |
| Stage | Prepares a mission draft and route preview. It does not launch a hunt. |
| Receipt | Requests a mission-execution approval receipt. Approval is a separate decision. |

The `scoped` label means the snapshot sees a target other than the default `local-lab`. It does not independently establish permission to test that target. The Authority row shows the snapshot's leading issue, which can concern planning or evidence as well as authorization.

## Training Range

This panel provides a local practice setup and explains the available drill and CTF surfaces.

| Button | Behavior |
|---|---|
| Arm Local | Sets the target to `local-lab`, selects the code/supply-chain family, and replaces the directive with a local-only training objective. It updates the draft and triggers the normal state refresh/self-heal handling. It does not start a mission or provision Docker challenge containers. |
| Drill | Runs the same workflow check as the header's Field Drill button. |
| Range | Navigates to the CTF Range page. It does not launch a challenge. |

The `armed` label reflects selection of `local-lab`; it is not confirmation of a running lab service. The CTF Range page explicitly labels its browser container controls and solves as local simulation/illustrative, separate from execution-based benchmarks.

## What Field Drill Actually Checks

The drill exercises API health, capability information, resources, prompt packs, runbooks, planning, evidence/hypothesis/work-order records, findings, retests, learning proposals, bundles, and approval gates.

It creates practice records, marks a practice retest passed, and requests/approves a short-lived receipt for a local `file package.json` command. It also submits requests intended to confirm that shell control characters and unapproved LAN reconnaissance are blocked. These are workflow checks, not evidence of a discovered vulnerability or a completed external hunt. The drill uses the current draft context rather than automatically selecting `local-lab` first.

The result lists passed and failed checks and can identify missing capabilities in the running container.

## Scope Receipts

This panel lists recent backend approval records, including their status, ID, action, target, and reason. The header counts pending records; the list shows up to twelve recent records, so approved or rejected receipts can remain visible when the pending count is zero.

Pending entries have **approve** and **reject** buttons. These record a decision for that receipt. The buttons do not themselves start or resume a mission. The fetched list is backend-wide, rather than filtered exclusively to the displayed mission.

## What Bundle Contains

The bundle assembles the mission draft, operation context, capability preflight, runbook, reference resources, prompt packs, evidence, hypotheses, work orders, findings, retests, and relevant approvals. It includes reproduction material, evidence/control gaps, suggested next actions, and a handoff summary. The backend applies secret redaction to the response.

## Source References

- [Homepage and browser handlers](../../docs/index.html): `missionCockpit`, `renderMissionCockpit`, `armLocalTrainingRange`, `exportPlinyMissionBundle`, `runPlinyFieldDrill`, and `renderScopeReceipts`.
- [Backend bundle generation](../../src/server.ts): `buildMissionBundle` and `POST /api/mission-bundles`.
- [Operator Clarity Layer](operator-clarity-layer.md): shared gate/snapshot concepts and related controls.

This explanation comes from inspected source. No controls, drills, or approvals were activated during this introductory walkthrough.
