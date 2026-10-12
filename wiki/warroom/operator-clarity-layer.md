# OPERATOR CLARITY LAYER

[Back to wiki](../README.md)

## Purpose

This section turns mission information into a practical summary: what needs your attention, what is holding progress, and how much supporting proof exists. Its subtitle, “Current truth, next move, and proof pressure for the active hunt,” refers to status, suggested actions, and the need to verify claims.

The visible layout has a toolbar, a strip of status badges, and three panels: **Operator Inbox**, **Gate Snapshot**, and **Proof State**.

## Toolbar

| Control | Behavior |
|---|---|
| Compact / Comfort | Switches between compact and comfortable spacing. The preference is saved in this browser. It changes presentation, not execution. |
| Copy Snapshot | Copies a plain-text summary: gate status/score, target, mission family, evidence/findings/passed retests, tool readiness, next issue, and open actions. |
| First Blocker | Scrolls to and highlights the first displayed blocker or priority item. It does not resolve that item. |
| updated … | Shows when this section was last rendered. It is not a guarantee that every backend record was freshly fetched. |
| snapshot idle / snapshot copied | Indicates the copy control's state. This is separate from a scope-approval receipt. |

## Status Badges

The strip summarizes blocker presence, open tasks, evidence count, pending memory reviews, and tool readiness. “Tools syncing” means the section has no readiness value yet. A percentage describes tool availability for the selected mission family, not investigation completion or likelihood of finding a vulnerability.

“No hard block” means this summary detected no explicit target/receipt blocker. It can still coexist with warnings, incomplete proof, or a gate on hold.

## Operator Inbox

The inbox builds suggestions from the current draft and loaded records. Items appear when their corresponding condition exists; not every item is always visible.

| Item / button | Meaning and actual button behavior |
|---|---|
| Set target / Target | Target is unclear or still the default `local-lab`. Focuses the main target field. |
| Approve scope / Receipt | Work orders require approval. Requests a mission-execution receipt; requesting it does not necessarily approve it. |
| Stage route / Stage | No tool-plan steps are loaded. Prepares a mission draft and route preview; staging alone does not launch the hunt. |
| Run queue / Queue | Open work orders need attention. The button refreshes the work-order list; it does not execute all queued tasks. |
| Retest claims / Repro | Findings have outstanding retest records. Builds reproduction packs; it does not itself run those retests. |
| Review memory / Memory | Proposed lessons await review. Refreshes learning status, memory entries, and proposals; it does not accept lessons. |
| Close tool gaps / Sync | Expected command-ready tools are missing. Refreshes Arsenal availability; it does not install tools. |
| WOLF check / Check | Requests a diagnostic pass for stale state and gate consistency. This shortcut requests diagnosis with automatic repairs disabled. |

**block** marks a target or receipt issue; **priority** marks suggested follow-up work; **ok** marks the diagnostic suggestion. The open count excludes the WOLF check. The default view shows up to six inbox items, so the count can exceed the displayed rows.

## Gate Snapshot

This panel displays the gate status and a score out of 100, the first locally derived issue, evidence/finding counts, and tool readiness/gaps.

When a backend mission-gate result has been loaded, its status and score are used. Otherwise, the browser supplies a provisional summary from target, plan, evidence, finding, and passed-retest counts. That fallback defaults to `hold`, or `ready` when passed retests exist.

The score is a readiness/proof summary, not a vulnerability probability or security rating. A `ready` label does not replace action-specific approvals. The issue text and gate status can differ because they come from separate checks.

| Shortcut | Behavior |
|---|---|
| Stage | Prepares the mission draft and route preview. |
| Watch | Fetches existing Watch Loop status/signals; it does not arm continuous monitoring. |
| WOLF | Runs the diagnostic pass with automatic repairs disabled. |
| Ledgers | Refreshes evidence, hypotheses, work orders, findings, and retests. If the current draft has no records, this refresh can adopt the latest recorded mission context. |

## Proof State

This panel displays the intended progression from investigation to reviewed learning:

| Stage | Meaning |
|---|---|
| Idea | The target or starting investigation intent. |
| Hypothesis | A specific suspicion to test; shows how many hypotheses are recorded. |
| Work Order | A task to investigate a suspicion; shows open versus total tasks. |
| Evidence | Recorded supporting artifacts, such as logs, diffs, screenshots, or fixtures. |
| Finding | A claim promoted into the findings ledger. |
| Retest | Replay or validation records; shows passed versus total retests. |
| Memory | Proposed lessons awaiting review for future investigations. |

The visual states are derived from counts. A completed-looking stage means records exist, not that every task or claim has passed validation. In particular, the Memory indicator can advance from passed retests even when no accepted lesson is shown.

## Example at First Launch

With no configured target, plan, or proof, the section can show **Set target**, **Stage route**, a gate on **hold**, and zero evidence. These describe the current setup gaps. After records are loaded, suggestions change to reflect the work still needed.

## Source References

[Homepage and browser logic](../../docs/index.html): `operatorDesignLab`, `buildOperatorQolSnapshot`, `buildOperatorQolInbox`, `buildQolEvidenceLadder`, `renderOperatorQolDesign`, and the associated action handlers.

This explanation comes from inspected source. No controls were activated during the introductory walkthrough.
