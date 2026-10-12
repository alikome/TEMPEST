# AI Connection Prompt

[Back to wiki](../README.md)

## Purpose

The “No agent or API backend connected” prompt appears when the browser's connection checks find no usable AI connection. It sits between the hunt launcher and Operator Clarity Layer.

Its **Connect in Settings** button opens agent configuration in Settings. The hunt launch flow can also direct you there when it cannot identify an AI backend.

## What It Means

Running the web application and supplying its AI backend are separate requirements. An operational Docker container can serve the War Room while no model or connected coding agent is available.

The prompt suggests connecting an already-authenticated coding agent or configuring a provider key. Local-model configuration is another supported route in the application.

This is an onboarding/status prompt. Clicking it does not authenticate an agent automatically, run a mission, or change target authorization. A missing prompt likewise does not guarantee that the next model call will succeed; launch-time checks can still detect a stale or unavailable connection.

## Sources

[Homepage](../../docs/index.html): `noBackendNudge`, `nudgeToSettings`, `openAgentSettings`, local-agent boot logic, and the hunt launch checks. See also [System Status](system-status.md).
