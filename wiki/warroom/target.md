# Target

[Back to wiki](../README.md)

## Purpose and Controls

This section manages the browser's target list, which is separate from just typing a target into a field.

| Control | Behavior |
|---|---|
| Host input | Accepts a hostname, IP, or target text. |
| Host / Net / Web / API | Stores the target's category as host, network, webapp, or API. |
| Ports | Stores optional port text, such as `80,443,8080`. |
| + | Adds a target with the selected category and ports, saves browser state, and clears the host/ports inputs. |
| Bulk Import | Opens a paste prompt and imports delimited host/port or network entries, skipping duplicates. |
| From File | Reads a local `.txt`, `.csv`, or `.json` file into the target list. |
| × on a target | Removes that target from the browser list. |

Cards show the host, stored ports/category, and a target count. Adding a target does not scan it or approve execution.

## Import Formats

For text imports, prefer simple entries such as:

```text
owned-app.local
10.0.0.5
```

Bulk paste also handles simple `host:port` entries. The file reader splits text/CSV on line breaks, commas, and semicolons; it is not a full quoted-CSV parser.

JSON expects an array of strings or objects with `host`, `ip`, or `target`. Object port/scope metadata is not preserved by this importer. URL and IPv6 parsing are not uniformly supported across these simple import paths.

## Launch-Time Interpretation

The current backend dispatch serializes the list as host values. Stored scope categories and port text are not passed by this browser dispatch method, so their display is not proof of an enforced scan range or port restriction.

The browser uses the first entry as its primary target for several mission displays; backend dispatch receives all entries. The hero HUNT launcher replaces the list with its entered target. Clearing target cards does not stop an already-running mission.

## Source

[Homepage](../../docs/index.html): `addTarget`, `renderTargetCards`, `removeTarget`, `bulkImportTargets`, `importTargetsFromFile`, and `BackendDispatch.startMission`.
