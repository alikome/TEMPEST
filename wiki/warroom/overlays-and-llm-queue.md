# Overlays, Notifications, and LLM Queue

[Back to wiki](../README.md)

## Purpose

These conditional/floating surfaces accompany the War Room rather than occupying a permanent card in its main layout.

## Welcome and Tour

The first-run welcome explains AI setup and offers **Take the guided tour** or **Got it**. Dismissing it saves a browser preference. The tour highlights interface elements and supports forward/back navigation, step selection, and skipping. The header and floating question-mark controls can reopen it.

These orientation controls do not launch missions.

## Tooltips, Dialogs, and Toasts

- Operator hover details explain the selected role and configuration.
- Finding titles open a metadata/evidence dialog.
- Shared modals host approvals, imports, history, help, and Quick Actions.
- Toasts announce actions, warnings, or failures.
- An intel-event tooltip remains in the source for the retired console; it is not another currently visible activity section.

## Critical Alerts

High/critical findings can briefly flash a colored screen border. The handler can also play a sound and use browser notifications when permitted, or request notification permission. Alerts depend on the recorded severity, so an unverified claim can trigger them.

## LLM Queue

The floating queue shows browser-managed model calls and their queued, running, done, error, or cancelled state. Its counter shows active queued/running entries, falling back to the listed entry count when none are active. The log mirrors application notices and retains up to 200 lines.

| Control | Behavior |
|---|---|
| Header / minimize | Collapses or expands the popup. |
| Log button | Shows/hides the live-log panel. |
| Close | Hides the popup; it does not stop a mission or cancel all calls. |
| Call cancellation controls | Request cancellation of the corresponding queued/running browser call. |

The popup can remain visible after activity until manually closed. It is not a complete listing of backend/keyless model calls or worker processes.

## Source

[Homepage](../../docs/index.html): welcome/tour markup, tooltip and modal handlers, `triggerCriticalAlert`, and LLM Queue functions. [Sound alerts](../../docs/sounds.js).
