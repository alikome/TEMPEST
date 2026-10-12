# Findings & Loot

[Back to wiki](../README.md)

## Purpose

The table collects the browser's current mission findings. “Loot” refers to entries categorized as credentials or access, alongside vulnerability and informational entries.

Columns show **Severity**, **Type**, **Finding**, **Target**, and **Phase**. The count covers all recorded entries, including unverified claims.

## Controls

| Control | Behavior |
|---|---|
| ALL / CRIT / HIGH / MED / LOW | Filters displayed rows by severity, or shows all rows. |
| CREDS | Filters by credential type rather than severity. |
| Finding title | Opens a detail dialog with metadata, provenance, detail, and available evidence. |
| Copy icon | Copies that finding's title, severity, target, phase, time, detail, and evidence text. |
| REPORT | Downloads a Markdown report from the browser's current mission findings. |

The row sorter places tool-backed entries first and then orders by severity. New findings can change the visible order.

## Proof and Severity

Rows lacking both tool provenance and attached evidence receive **model-asserted · unverified** labeling. Findings may be populated from backend events/status, restored records, or keyword extraction from activity messages. A severity badge is therefore not independent confirmation of a vulnerability.

The detail dialog makes the available provenance and evidence inspectable. Tool-backed display labeling still does not replace root-cause review and retesting.

High/critical entries can trigger a visual flash, sound, and browser-notification handling even when unverified.

## Report versus Bundle

REPORT downloads a `.md` file with counts and available finding detail/evidence. It includes legacy console entries only when that console exists; it does not automatically export the current System Events terminal. The handler does not carry every backend provenance/control record into the report.

The backend **Bundle** action packages a broader investigation context with ledgers, approvals, reproduction material, and gaps. A severity filter does not limit REPORT to the visible rows.

Starting a new mission clears this browser findings list. Backend ledgers and browser history are separate.

## Sources

[Homepage](../../docs/index.html): `findingsPanel`, `addFinding`, `renderFindingsRow`, `showFindingDetail`, `_extractFindings`, and `exportMissionReport`. [Row sorting](../../docs/findings-sort.js).
