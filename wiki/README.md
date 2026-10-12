# TEMPEST Wiki

An introduction to T3MP3ST and its War Room, built section by section as we explore the application. Each page explains what the visible controls do and what to expect from them.

These explanations reflect the repository source inspected during our walkthrough. They do not certify the running Docker image, tool availability, or benchmark results.

## Introduction

- [Repository overview](repository-overview.md) — purpose, architecture, and development conventions.

## War Room Homepage

The complete walkthrough follows the page's source order. Shared application controls come first; conditional and floating surfaces are included.

1. [Navigation and page header](warroom/navigation-and-header.md)
2. [Command Header](warroom/command-header.md)
3. [System Status](warroom/system-status.md)
4. [SITREP](warroom/sitrep.md)
5. [System Events](warroom/system-events.md)
6. [Live / Simulation banner](warroom/live-simulation-banner.md)
7. [Narration Rail](warroom/narration-rail.md)
8. [START A ZERO-DAY HUNT](warroom/start-zero-day-hunt.md)
9. [AI connection prompt](warroom/ai-connection-prompt.md)
10. [OPERATOR CLARITY LAYER](warroom/operator-clarity-layer.md)
11. [MISSION SPINE](warroom/mission-spine.md)
12. [PLINY CODE OPS LAYER](warroom/pliny-code-ops-layer.md)
13. [Blitz Monitor](warroom/blitz-monitor.md)
14. [Compact preflight indicators](warroom/compact-preflight.md)
15. [Quick Demo](warroom/quick-demo.md)
16. [Target](warroom/target.md)
17. [Operators](warroom/operators.md)
18. [Config](warroom/config.md)
19. [Quality](warroom/quality.md)
20. [Live Stats](warroom/live-stats.md)
21. [Findings & Loot](warroom/findings-and-loot.md)
22. [Footer, shortcuts, sound, and history](warroom/footer-and-history.md)
23. [Overlays, notifications, and LLM Queue](warroom/overlays-and-llm-queue.md)

The War Room ends after the footer. Live Scan, Scope Receipts, Operatives, Evidence Vault, and other sidebar destinations are separate pages. The source's retired Live Console, Mission Log, old kill-chain bar, and hidden compatibility elements are accounted for in the corresponding pages above; they are not additional visible sections.

## Growing This Wiki

Add each newly explained section as a separate Markdown page and link it here. Use descriptive kebab-case filenames; keep War Room pages under `warroom/`. Cover the section's purpose, visible controls, expected behavior, and relevant limitations. Add relative links to the source files used to verify the explanation.

This walkthrough is introductory. Documenting a control does not launch missions or change application settings.
