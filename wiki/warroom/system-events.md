# System Events

[Back to wiki](../README.md)

## Purpose

This is the War Room's scrolling activity feed. It combines received backend events with browser-generated notices about launches, approvals, controls, errors, and planning actions.

Lines have a display timestamp and color corresponding to their event category. The feed keeps up to 120 displayed entries and shortens individual messages for this compact view. Its counter tracks entries received by the display, rather than only the rows currently retained.

## Controls

| Control | Behavior |
|---|---|
| Pause / play | Stops or resumes adding entries to this display. It does not pause the mission. Entries arriving while display capture is paused are skipped, not buffered for replay. |
| CLR | Clears displayed rows. It does not delete backend records, findings, or reset the event counter. |
| COPY | Copies the text currently displayed in the terminal, including its truncation. It is not a full backend-log export. |

## Related Features

The old Live Console and Mission Log panels were removed. System Events is the current visible event feed; compatibility functions remain in the source for older callers.

Some messages can also be mirrored into the floating LLM Queue log. Evidence and approval ledgers remain separate from this short activity display.

## Source

[Homepage](../../docs/index.html): `sysEventTerminal`, toolbar handlers, `pushSysEvent`, and `addIntel`.
