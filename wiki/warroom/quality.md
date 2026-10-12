# Quality

[Back to wiki](../README.md)

## Purpose

This compact panel displays outcomes from browser-side output review.

| Counter | Meaning |
|---|---|
| OK | Outputs approved by the review pipeline. |
| REV | Outputs revised. |
| REJ | Outputs rejected. |
| ESC | Outputs escalated for additional attention. |

These are review outcomes, not vulnerability counts or confirmed exploit results.

## How to Read It

The command header's Quality percentage uses approved plus revised outputs divided by approved plus revised plus rejected outputs. Escalations are displayed separately.

Backend/keyless missions have separate server-side gates. Their activity may not populate these browser counters, so zero values or `--` in the header do not establish that no server-side review occurred.

The panel's ACTIVE label and full-width colored bar are initial markup. No dynamic update of those two display elements was found in the inspected source, so they should not be treated as a successful quality certification.

Read individual findings' provenance, evidence, and retest state when evaluating proof quality. A favorable output-review rate does not verify each claim.

## Source

[Homepage](../../docs/index.html): Quality markup, `updateDashboardQualityMetrics`, and `updateQualityDisplay`.
