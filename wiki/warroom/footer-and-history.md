# Footer, Shortcuts, Sound, and History

[Back to wiki](../README.md)

## Keyboard Controls

| Shortcut | Behavior |
|---|---|
| Enter | Launches from the active War Room when not typing in a form. Enter in the hero target field uses HUNT's handler. |
| Ctrl/Cmd + Enter | Goes to the War Room and invokes launch when idle and handled outside form typing. |
| Esc | Closes the generic modal if open, otherwise requests mission abort when running. |
| D | Selects all operator roles. |
| K | Clears visible console/System Events entries. It does not delete backend evidence. |
| Number keys 1–9 | Navigate to the mapped application pages. |
| ? | Opens keyboard help. |

Handlers generally avoid ordinary shortcuts while typing in input, textarea, or select controls. The footer also advertises **/ Search**, but console search was removed and no current War Room search handler was found. That label is a legacy hint.

## Sound Controls

The footer speaker toggles the inline browser-pipeline sound cues. A separate floating bottom-left speaker, added by `sounds.js`, controls backend lifecycle alerts and saves its preference in browser storage. These are independent controls.

Browser audio policies can require interaction before sounds play. Sound alerts communicate lifecycle events; they do not certify findings.

## History

**History** opens locally saved mission summaries with dates, elapsed time, targets, finding counts, and severity totals. Selecting an entry restores available finding/display data; it does not restart the backend mission. **Clear History** removes those browser history records after confirmation.

The history writer retains up to twenty missions, with up to fifty findings per snapshot and legacy console entries when available. This browser history is separate from server persistence and is not a complete audit export. The retired console's absence limits old log restoration.

## Sources

[Homepage](../../docs/index.html): footer markup, keyboard handlers, `toggleSoundCues`, `saveMissionToHistory`, `showMissionHistory`, and `loadMissionFromHistory`. [Backend sound alerts](../../docs/sounds.js).
