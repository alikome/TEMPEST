# Compact Preflight Indicators

[Back to wiki](../README.md)

## Purpose

Four small indicators start the setup area below Pliny Code Ops. They summarize browser configuration before launching.

| Icon | Meaning |
|---|---|
| Operators | Number of operator roles selected in browser state. |
| Targets | Number of targets added to the browser target list. |
| Key | `OK` when a supported browser key or detected AI backend exists; `NO` otherwise. A connected agent can satisfy this without an API key. |
| Tools | Number of tools selected in the browser Arsenal loadout, or `OPT` when none are selected. |

## Limits

These indicators are setup hints, not a backend capability test. In particular, the Tools indicator counts the selected loadout rather than installed binaries, and the Operators indicator does not count processes currently executing.

The compact checklist considers operator selection, target selection, and the detected AI connection when determining readiness. The launch flow can automatically add/select some missing setup, so an initial zero does not necessarily prevent using HUNT.

The detailed **Capability Preflight** in Pliny Code Ops checks the backend environment and supplies a separate report.

## Source

[Homepage](../../docs/index.html): `check-operators`, `check-targets`, `check-apikey`, `check-tools`, and `updatePreflightChecklist`.
