# START A ZERO-DAY HUNT

[Back to wiki](../README.md)

## Purpose

This section is the War Room's main starting point. It lets you choose a target and launch a security-testing mission, either directly or through guided setup.

“Zero-day hunt” describes the objective. A completed mission does not necessarily discover a previously unknown vulnerability.

## Visible Controls

| Element | What it does |
|---|---|
| Introductory text | Describes collecting information with real tools, AI reasoning over results, and attaching evidence to findings. It identifies later attack phases as partially scaffolded and reminds users to test authorized targets. |
| Run keyless / Settings link | Opens configuration for the AI connection that drives missions. A connected coding agent or configured model provider supplies that connection. Docker runs the application server; a working AI connection is still required. |
| Target input | Accepts the target you want investigated. The placeholder suggests a GitHub repository, package name, hostname, or IP address. |
| HUNT | Starts the direct mission-launch flow. Pressing Enter in the target field does the same thing. |
| Guided | Opens the Op Admiral setup wizard. Opening it alone does not start a hunt. |
| AUTONOMOUS MODE | Requests fewer approval interruptions. In the direct launch flow, it automatically approves a requested mission-execution receipt. Scope and backend controls still apply. |
| Example targets | Fill the input field when clicked. Clicking an example does not launch a mission or establish authorization. |

## What Happens When You Press HUNT

1. The app checks for a target and an available AI connection. If the AI connection is missing, it directs you toward Settings.
2. It makes the entered target the current mission target, replacing the previous target selection.
3. It selects operators automatically if none are selected.
4. With the backend available, it requests mission execution from the server.
5. Normal mode can ask you to approve an external target before proceeding. Recognized loopback/lab targets and autonomous mode can have the mission receipt approved automatically.
6. The War Room displays mission status, events, and findings as execution proceeds.

## What Guided Setup Adds

The wizard collects:

- **Target type:** web/API, network host, source repository/package, smart contract, robotics/OT, or CTF.
- **Target and authorization:** what to investigate and confirmation that you may test it.
- **Depth:** Quick, Standard, or Deep.
- **Autonomy:** Guided or Autonomous.
- **Review:** a summary before launch.

It also offers an AI-assisted target suggestion option, framed around training labs, public CTFs, or open-source projects for source-only investigation.

## Interpreting the Target Field

The direct input is a quick launcher. Although it advertises repository and package targets, this route does not automatically attach repository source for analysis. Guided setup collects more context about the intended investigation.

Real execution also depends on tools being available to the backend. The banner's mention of a tool such as nmap does not confirm that it is installed in your running container.

## Source References

- [Homepage and browser launch logic](../../docs/index.html): `zeroDayHuntHero`, `startZeroDayHunt`, `startMissionFromDashboard`, and `openAdmiralWizard`.
- [Backend mission handling](../../src/server.ts): `POST /api/mission/start`.
- [Docker configuration](../../docker-compose.yml) and [Docker image definition](../../Dockerfile).

This page explains the inspected source; no hunt was launched during the introduction.
