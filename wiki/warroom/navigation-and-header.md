# Navigation and Page Header

[Back to wiki](../README.md)

## Purpose

These shared controls surround the War Room and remain part of the application shell when you switch pages.

## Sidebar

The sidebar groups destinations into Main, Ranges, Toolkit, Command, and System. It links to War Room, Live Scan, Scope Receipts, Operatives, Evidence Vault, CVE Vault, OBSIDIVM, CTF Range, Arsenal, Terminal, Config Library, Op Admiral, Self-Improvement, Settings, and About.

Clicking a destination changes the active page; it does not automatically launch its advertised activity. Badges show pending receipts, browser-selected operators, or range state according to the relevant feature.

The API status indicator and reconnect arrow check server health. The footer connection indicator reports connection state. Theme swatches select Storm, Ember, Crimson, or Void and save the preference in browser storage. Themes change appearance.

## Header Controls

| Control | Behavior |
|---|---|
| Mobile menu | Opens/closes the sidebar on smaller screens. |
| War Room title | Names the active page. |
| IP badge | Displays the backend's egress-IP check; clicking requests another check. It can show direct/proxied results, a configured-proxy leak indication, or `n/a` if checking fails. |
| ? | Starts the guided tour. |
| Actions | Opens shortcuts for operator selection and navigation to other pages. The “Run Benchmarks” shortcut navigates to that page rather than immediately running a benchmark. |
| War Room button | Returns to the War Room. |

The IP badge reports a particular network check. It does not independently establish that every application request follows the same proxy route. In Docker, the check originates from the backend environment.

## Sources

[Homepage](../../docs/index.html): sidebar/header markup, `openQuickActions`, `refreshEgressIp`, and theme/tour logic. [Application shell](../../docs/app-shell.js): navigation and readiness handling.
