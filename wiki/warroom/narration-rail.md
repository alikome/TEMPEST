# Narration Rail

[Back to wiki](../README.md)

## Purpose

This conditional panel translates mission events into plain-language progress messages. It appears during launch and is hidden when the mission's launch UI resets.

The heading follows the reported phase with descriptions such as “Looking at your target,” “Mapping weak spots,” “Testing for ways in,” or “Wrapping up.”

## What Appears in the Feed

Backend events can produce messages about deployed operators, assigned tasks, completed or failed probes, findings, credentials, detections, and situation assessments.

Entries include a display timestamp; newest messages appear first. The counter counts narrated steps. This is not a percentage-complete indicator or a record of every subprocess.

The narration uses predefined language for event categories. For example, a failure may be described as re-aiming. Interpret that as a summary of the received event, not independent confirmation that a new approach has already executed.

## Relationship to Other Panels

System Events provides a more technical activity stream. Findings & Loot provides claim details and attached evidence. The narration rail makes those activities easier to follow without establishing their proof quality itself.

## Source

[Homepage](../../docs/index.html): `narrationRail`, `NARRATE_PHASE`, `narrateReset`, `narrateState`, `narrate`, and backend event handlers.
