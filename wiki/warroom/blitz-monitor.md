# Blitz Monitor

[Back to wiki](../README.md)

## Purpose and Current Visibility

This legacy telemetry strip is present after Pliny Code Ops but hidden by default. It describes the older browser strike engine.

The current **BLITZ** launch button routes through the unified mission launcher in autonomous mode. It does not call the retired browser kill-chain function that used to reveal this strip. Consequently, this panel may remain hidden during a normal backend mission.

## Fields and Controls

The retained strip contains **STRIKES**, **HITS**, **CRITS**, **HIT%**, **EVIDENCE**, and a row of strike markers.

- **Proof Chain:** opens records in the legacy browser `ProofChain` collection. Available records can expose request/response details and verification controls.
- **Export:** downloads a Markdown report from that same collection.

These are separate from the backend evidence ledger, reproduction packs, and mission bundles. Their presence does not mean current backend results populate the legacy collection.

## How to Interpret It

For a current backend mission, use System Events, mission status, and the evidence/retest records described elsewhere in this wiki. Treat this strip as retained compatibility UI rather than another required launch step.

## Source

[Homepage](../../docs/index.html): `blitzMonitor`, `launchAutonomousMission`, `_retiredClientKillchain`, `showProofChain`, and `exportProofReport`.
