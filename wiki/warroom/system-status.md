# System Status

[Back to wiki](../README.md)

## Purpose

This strip separates application-server availability from AI availability and connected-agent health.

| Cell | Meaning |
|---|---|
| Backend | Reports operational server health and whether backend mission dispatch has been detected. An offline label describes the browser's latest check. |
| AI Backbone | Summarizes the configured local model, connected agent, browser key, or server provider. Missing/stale connections are called out. |
| Local Agents | Lists registered connected agents with live or stale ping results. Click to manage them in Settings. |

The server being online does not establish that the model is reachable. Similarly, having an agent registered does not establish that its latest health check succeeded.

## Updates and Interpretation

The War Room refreshes this status approximately every four seconds while the page is active. Checks use backend health, local-agent status, and mission status.

AI Backbone is a configuration/health summary. Launch-time provider resolution and validation decide the actual backend; a displayed configured provider is not proof of a successful model response.

When the application is in Docker, its server must be able to reach the agent or model. A coding agent installed on the host is not automatically connected to the container.

## Source

[Homepage](../../docs/index.html): `systemStatusBar`, `refreshSystemStatus`, backend health detection, and agent-routing helpers.
