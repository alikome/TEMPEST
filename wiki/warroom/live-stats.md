# Live Stats

[Back to wiki](../README.md)

## Purpose

Four cards provide compact counts beneath Config and Quality.

| Card | What it counts |
|---|---|
| Targets | Entries in the browser target list. |
| Creds | Entries in the browser credential collection. |
| Access | A legacy access counter initialized to zero; no update of this element was found in the inspected source. |
| Phases | Compatibility progress counter for five phase categories, updated by `updateKillChain`. |

## Interpretation

Target and credential counts describe local collections, rather than proving that assets were contacted or credentials validated.

The phase counter uses an older five-phase model: recon, scanning, exploitation, post-exploitation, and exfiltration. SITREP uses seven attack-phase labels; Hunt Pulse uses seven investigation stages. Their denominators and meanings differ.

The compatibility phase counter advances on phase-completion notifications handled by its browser function. It is not an independent check that every phase was performed successfully against a live target.

Do not use Access remaining at zero to conclude that no access-related finding exists; inspect the finding details and backend evidence instead.

## Source

[Homepage](../../docs/index.html): Live Stats markup, `updateStats`, `addCredential`, `updateKillChain`, and `resetKillChain`.
