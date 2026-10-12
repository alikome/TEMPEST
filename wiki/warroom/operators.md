# Operators

[Back to wiki](../README.md)

## Purpose

The grid selects operator roles for the next launch. Roles cover reconnaissance, scanning, exploitation, infiltration, exfiltration, stealth/persistence, coordination, and analysis.

## Controls

| Control | Behavior |
|---|---|
| Operator tile | Adds/removes that role from browser selection. |
| Hover tooltip | Shows role details, phase, configured capabilities, and selection status. |
| Formation | Selects Adaptive, Parallel, Sequential, Debate, or Best-of-N coordination in the browser pipeline. It synchronizes the Config cognitive-mode selector. |
| Deploy All | Selects all listed roles and saves the selection. |
| Recall | Clears all selected roles after confirmation when applicable. |

The count and illuminated tiles reflect browser selection. Although the interface uses “ACTIVE,” “deploy,” and “terminate” language, these selection handlers do not themselves spawn or kill backend workers. Actual operators are spawned when a backend mission launches. Recall is not the mission Abort control.

## Coordination Modes

Adaptive chooses a strategy according to phase; Parallel asks roles to work together; Sequential builds on prior output; Debate compares approaches; Best-of-N compares independent attempts. These are the intended browser-pipeline modes.

The page explicitly states that backend/keyless missions use configured operator prompts and defaults rather than consuming all these browser coordination settings. For actual executing-worker status, use backend mission status or the separate Live Scan page.

## Source

[Homepage](../../docs/index.html): `swarmGrid`, `renderSwarmGrid`, operator selection handlers, `changeFormation`, and `setCognitiveMode`.
