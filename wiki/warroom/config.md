# Config

[Back to wiki](../README.md)

## Purpose

Config sets the mission name and browser reasoning preferences, offers configuration templates, and contains two launch buttons.

## Fields and Toggles

| Control | Intended behavior |
|---|---|
| Template | Applies a preset operator selection, OPSEC choice, coordination values, and review toggles. Can fill an empty mission name; does not launch. |
| Op Codename | Names the mission. |
| Stealth / Normal / Aggressive | Sets a browser-pipeline preference for quiet, balanced, or louder operation. |
| Cognitive Mode | Adaptive, Parallel, Sequential, Debate, or Best-of-N browser coordination. |
| Tastemaker | Enables model-assisted operator selection for phases in the browser pipeline. |
| Reflection | Enables output self-critique/refinement in the browser pipeline. |
| Strict QA | Requests stricter output-quality review in the browser pipeline. |
| Autonomous (Blitz) | Allows automatic approval of requested mission execution in the unified backend launch flow. |

Available templates are Web App Assessment, Network Pentest, Quick Recon, Full Kill Chain, and Stealth Recon. These configure preferences; the template name does not establish that every named phase is implemented.

## Launch Controls

**ENGAGE** uses the unified standard launch flow. **BLITZ** uses that same launcher with autonomous mode. It does not invoke the retired browser strike engine, despite legacy tooltip wording.

Both launch controls use the current targets/operator selection and AI configuration. The unified flow can automatically fill missing target/operator selection and enforce requested approvals.

## Backend versus Browser Settings

The explanatory note in this section states that OPSEC, cognitive mode, and reasoning toggles tune the browser pipeline. Backend/keyless missions use configured prompts/defaults; their launch request does not send these settings as general runtime controls.

The autonomy checkbox is an exception relevant to backend receipt handling: it is checked when deciding whether to approve a requested execution receipt automatically. It does not grant blanket target scope or install missing capabilities.

## Source

[Homepage](../../docs/index.html): Config markup, `MISSION_TEMPLATES`, `applyMissionTemplate`, `updateArchFromDashboard`, `launchMission`, and `launchAutonomousMission`.
