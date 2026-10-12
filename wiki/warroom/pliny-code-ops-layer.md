# PLINY CODE OPS LAYER

[Back to wiki](../README.md)

## Purpose

This is the War Room's detailed investigation workbench. It turns a plain-language objective into a mission contract, proposed agent lanes, tool plans, hypotheses, work orders, evidence, findings, retests, and learning proposals.

Some controls prepare plans or refresh status; others create or update backend records. Several visual panels describe intended roles or derive progress from record counts. They do not independently establish that agents are running or that vulnerabilities have been verified.

## Header Badges and Readiness Strip

| Label | Meaning |
|---|---|
| Catalog tools | Tools described by the browser's catalog. |
| Wired | Backend adapters represented in the returned Arsenal information. |
| Installed | Command-ready tools reported available to the backend. In Docker, availability concerns the backend environment, not simply your host machine. |
| 20 slash cmds | A static capability label; it is not a live command-discovery result. |
| Agent memory | Indicates the reviewed-learning feature. |
| Egress gated | Indicates scope controls on outgoing tool activity. It is not proof that the entire container is network-isolated. |

The strip summarizes **Scope**, **Target**, **Tools**, **Mode**, **Agents**, **Evidence**, and **Receipt**. Some values describe draft structure: “3 lanes” can mean three proposed lanes, and evidence-gate counts can describe planned requirements rather than collected artifacts.

## Tool Approvals & Spicy-Action Audit

Shows approved-tool chips, recent allowed/denied decisions, and a warning strip for credential or dangerous actions.

The tool-approval controller gates tools stamped with intrusive, credential, or dangerous risk tiers. An approved tool can remain approved for that controller's session; credential and dangerous calls still produce audited warnings. Tool approval remains separate from target scope and mission-execution receipts.

This panel does not contain a general approve-all control. Its introductory text should not be read as a guarantee that every built-in probe requires this particular gate: the code documents optional built-in risk stamping via `T3MP3ST_GATE_BUILTINS=1`, with egress scope controls remaining separate.

## Zero-Day Hunt Pulse

Summarizes the target, mission family, queued work, hypotheses, evidence, findings, and retests. Its stages are **Scope → Split → Swarm → Probe → Repro → Validate → Learn**.

The proof strip counts recorded items. The decision strip suggests the current move, leading blocker, and learning follow-up. “Lit” stages are derived from loaded plans and records; they are not a count of completed attacks.

## Specialist Swarm

Displays eight specialist categories: Web/API, AI/Agent, Packages, Infra/Cloud, Crypto, Reverse, OSINT, and Report.

The selected mission family and existing records determine which squads appear as **lead**, **watch**, or **standby**. Selecting a squad changes its brief: focus, proof, readiness, and suggested next move. It does not spawn that squad or connect a new model.

## Swarm Cognition Loop and Reasoning Bus

The loop shows **Intent → Decompose → Route → Hunt → Argue → Decide → Remember**. Four supporting cards summarize Mission Brain, Task Splitter, Tool Planner, and Proof Engine.

The Reasoning Bus summarizes roles such as Human, Admiral, Specialists, Skeptic, JUDG3, and Memory. Both displays are assembled from mission context and record counts. The bus is not a transcript of live conversations between those roles or a model's private reasoning.

## Setup and Context Panels

| Panel | What it does |
|---|---|
| Guided Starts | Presets such as an owned web app, AI-agent testing, repository hardening, CVE prioritization, or a leadership report. Selecting one fills the directive, family, mode, and recommended resources. It does not launch a mission. |
| Knowledge Atlas | Lists relevant reference packs, including OWASP, MITRE, and vulnerability datasets. **load/loaded** toggles reference metadata in the draft; **source** opens the reference website. Loading does not fetch the complete website or establish target authorization. |
| Agent Prompt Packs | Displays family-specific role instructions and evidence expectations included in draft context. “Active” describes displayed packs, not running agents. |
| Forefront Radar | Curated investigation themes, such as agent command-injection or browser privilege boundaries. Selecting a theme fills planning fields. This is not a live news feed or automatic target scan. |
| Team Preview | Opens the review guide, installation matrix, and scope documentation. The doctor/demo text provides pointers; it does not execute those commands. |

## Capability and Tool Panels

**Capability Preflight:** the **preflight** button fetches the backend's capability report and score. It checks readiness, not vulnerabilities in your target.

**Tool Adapter Forge:** **sync arsenal** refreshes tool availability; **plan tools** builds proposed steps with evidence requirements and gates; **activation** displays the activation plan. These controls do not automatically write adapters or install the missing tools.

## Evidence and Hypothesis Panels

**Evidence Ledger:** lists recorded artifacts and their provenance strength. **log evidence** creates a scope/source-context note from the current draft. It does not upload a screenshot or run a scanner; a context note should not be mistaken for exploit proof.

**Hypothesis Graph:** summarizes suspected issues and links to supporting or contradicting evidence. **hypothesis** seeds a claim from the contract, creating a context note if needed; **graph** refreshes records and links; **promote** attempts to create a finding from a hypothesis. The promotion shortcut can mark a hypothesis supported before requesting promotion. This is a record-management action, not an independent exploit validation.

## Hunt Queue

Displays work orders, their status, kind, and tool hints.

- **decompose:** creates work orders from a selected hypothesis, seeding a hypothesis first if necessary.
- **complete:** selects an open work order and submits a completion result with a system-generated note. This shortcut records completion; it does not itself execute the task's suggested scanner or reproduce the suspected bug.
- **sync:** refreshes the work-order list.

## Watch Loop and The Fixer

**Watch Loop** checks mission-record gaps and follow-up needs. **pulse** runs one cycle without spawning tasks; **nudge** can create follow-up work orders; **arm** runs recurring pulses every 30 seconds while the browser timer is active, and becomes **pause** to stop them. This monitors workflow state rather than continuously scanning the target.

**The Fixer**, labeled WOLF, diagnoses stale state, outstanding retests, open queues, receipt requirements, missing tools, and pending memory reviews. **diagnose** reports issues; **repair** requests applicable safe state repairs. The inspected implementation can refresh a stale Watch Loop cycle. It leaves substantive tasks, approvals, installations, and retests as operator follow-up; it does not patch the target's code.

Several record-management actions also invoke an automatic self-heal refresh after completing.

## Findings / Retest and Repro Packs

**Findings / Retest:** **log finding** creates an initial, templated claim requiring validation, linked to available evidence or a new context note. **retest** queues a retest for an unresolved finding, creating an initial finding if needed. Queuing does not execute validation.

**Repro Packs:** **build** assembles reproduction/readiness material from recorded findings and proof. **bundle** assembles the wider mission handoff described in [Mission Spine](mission-spine.md). Packaging is separate from running a replay.

## Pressure Paths

Provides planning and local checks intended to challenge claims and identify follow-up tests:

| Button | Behavior |
|---|---|
| plan | Builds candidate pressure paths from reproduction material. |
| canary | Runs the selected path's local simulator check and can record evidence/retest results. |
| duel | Applies hunter-versus-skeptic checks to the path and its available proof; can record results and a follow-up work order. |
| mutate | Generates local-only variants and follow-up tasks. |
| chain | Composes mutation paths into proposed local-only chains and tasks. |
| repro | Rebuilds reproduction packs. |
| bundle | Builds the mission handoff bundle. |

The inspected duel implementation evaluates structured checks; its debate-style output is not evidence of two live models arguing. Local canary results and generated chains do not establish exploitation of the external target.

## Next Moves

Shows the family-specific runbook and handoff gaps. **runbook** fetches the guide; **gate** evaluates current mission readiness and triggers a self-heal pass; **bundle** assembles the handoff. A gate score describes readiness and proof completeness, not probability that the target is vulnerable.

## Learning Capsule

Shows proposed and accepted lessons for later investigations. **sync** refreshes learning records; **review run** asks the backend to generate learning proposals from the investigation. Proposal controls support accepting or rejecting lessons. Refreshing or generating proposals does not silently accept them.

## Mission Contract

The textarea holds your plain-language objective. The **mission family** selector chooses the domain, or requests automatic routing from the directive. The browser's initial auto-routing uses keyword matching. The **agent mode** selector records Human wizard, Agent lanes, Expert console, or Best-of-N race intent in the draft; selecting a mode does not itself launch workers or a model race.

The `/audit web`, `/agent probe`, `/repo review`, and `/report` buttons are planning shortcuts that fill fields and preview the draft. **receipt** requests mission-execution approval; **stage** prepares a backend mission draft/route preview when available; **field drill** runs the workflow check described in Mission Spine.

The JSON preview makes the contract inspectable: target, scope, allowed/forbidden actions, lanes, reference context, evidence gates, and reporting outputs. Changing contract fields can reset the browser's scoped investigation state.

## Agent Lanes and Evidence Gates

**Agent Lanes** is a static role guide: Codex for code/repository work, Claude for long-context review/reporting, Hermes for local tools, and Browser for visual checks. These labels do not confirm connected or running agents.

**Evidence Gates** is a static checklist: Scope, Proof, Judge, Receipt, and Range. The S3R4PH1M, JUDG3, ScopeGuard, and CRUCIBLE labels name intended roles or boundaries. The panel's fixed colors are not live pass/fail results; use loaded records and gate evaluations for actual status.

## Source References

- [Homepage and browser handlers](../../docs/index.html): `plinyCodeOpsLayer`, `buildPlinyOperationDraft`, `renderPlinyHuntPulse`, `renderPlinyCognition`, and the related `Pliny` action handlers.
- [Backend workflows](../../src/server.ts): Arsenal, preflight, ledger, Watch Loop, self-heal, pressure-path, learning, and mission-bundle endpoints.
- [Tool approval controller](../../src/arsenal/approval.ts).
- [Mission Spine](mission-spine.md) and [Operator Clarity Layer](operator-clarity-layer.md) for shared snapshot, receipt, and bundle concepts.

This walkthrough explains inspected source. No controls were activated and no investigation records were created during the introduction.
