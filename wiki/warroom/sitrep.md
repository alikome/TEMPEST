# SITREP

[Back to wiki](../README.md)

## Purpose

SITREP means situation report. This panel summarizes the mission's reported phase and current activity in a headline.

Its seven-stage pipeline is **RECON → WEAPON → DELIVER → EXPLOIT → INSTALL → C2 → ACTIONS**. C2 means command and control; Actions refers to the mission's objectives.

## What the Display Means

The panel starts on STANDBY with “Awaiting orders.” During a mission, backend status polling and live phase/situation events update it.

The current stage is highlighted. Earlier stages are styled as progressed based on their position before the reported phase. This is a phase display, not independent verification that every preceding stage succeeded or that a real exploit occurred.

The headline may carry a richer situation assessment from the backend or a phase-based fallback.

## Related Displays

This is the visible kill-chain phase view. The old separate five-stage kill-chain bar was removed, although compatibility code and the Live Stats phase counter remain.

The seven-stage Hunt Pulse inside Pliny Code Ops describes an investigation workflow, so its Scope/Split/Swarm stages have different meanings from SITREP's attack-phase labels.

## Source

[Homepage](../../docs/index.html): `sitrepStatus`, `sitrepHeadline`, `SITREP_STAGES`, `renderSitRepPipeline`, `updateSitRep`, and `refreshSystemStatus`.
