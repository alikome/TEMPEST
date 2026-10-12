# Quick Demo

[Back to wiki](../README.md)

## Purpose

Quick Demo provides a fast route into mission execution, plus three example target shortcuts.

## ONE-CLICK DEMO

The button checks for a configured key or detected AI backend. If no target is already added, it adds `testphp.vulnweb.com`. If no operators are selected, it selects all of them. It fills a demo mission name if the name is empty, then launches through the unified flow in **autonomous mode**.

This is an execution button. It does not simply preview the interface or run the local Field Drill.

An existing target list is preserved: the first selected target can remain the mission's primary target even though you clicked Demo. Autonomous mode can automatically approve a requested mission-execution receipt.

## Target Shortcuts

The repository offers these presets:

- `testphp.vulnweb.com`: web-application test-site preset.
- `demo.testfire.net`: banking-demo web-application preset.
- `scanme.nmap.org`: host/port-scanning preset.

Clicking a target row adds it to the list, with stored scope/port hints, and skips duplicates. That click alone does not launch a mission.

These names are repository presets. The walkthrough has not verified their current availability or external operators' permitted testing boundaries.

## Source

[Homepage](../../docs/index.html): Quick Demo markup, `DEMO_TARGETS`, `addDemoTarget`, and `launchQuickDemo`.
