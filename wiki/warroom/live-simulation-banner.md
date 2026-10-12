# Live / Simulation Banner

[Back to wiki](../README.md)

## Purpose

This conditional banner identifies the mission's execution route. It is hidden while idle.

| Label | Meaning |
|---|---|
| LIVE — real tools probing the target | The browser selected backend dispatch, which can run real operators and tools. |
| SIMULATION — an LLM is narrating, no packets sent | The target-testing workflow is browser-side LLM narration, without real tool execution. |

“No packets” describes target probing in this simulated path. Hosted-model calls can still send network requests to the provider.

## Important Interpretation

The LIVE banner is set when dispatch is attempted, before mission launch has been confirmed. Check mission status and recorded tool evidence to establish what actually ran. A LIVE label alone is not exploit proof.

When a backend attempt fails, the fallback logic can allow labeled simulation for recognized loopback/lab targets and refuse to substitute simulation for a failed external-target dispatch. Standalone browser execution is also labeled simulation.

Completion, failure, declined approval, and confirmed stop reset the launch UI and hide the banner.

## Source

[Homepage](../../docs/index.html): `fidelityBanner`, `setFidelity`, `startMissionFromDashboard`, and `resetEngageUI`.
