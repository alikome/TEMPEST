# Command Header

[Back to wiki](../README.md)

## Purpose and Fields

The command strip keeps mission identity, status, timing, counters, and execution controls together.

| Field | Meaning |
|---|---|
| Mission | Current mission name or a state such as STANDBY, MISSION COMPLETE, or MISSION FAILED. |
| Status | Launch, execution, pause, stop, failure, or approval information. |
| Elapsed | Wall-clock time since the browser recorded mission start; it is not a count of productive tool time. |
| API | Browser-side LLM call count. Backend/keyless work can be active while this remains zero. |
| Findings | Entries in the browser's current findings list, including unverified claims. |
| Quality | Browser-side output-review rate. Backend quality gates are evaluated separately. |
| LOW badge | A fixed initial threat label in the inspected markup; no dynamic update of this field was found. |

## Mission Controls

**ENGAGE** uses the same unified launch flow as the other launch controls. It can add a target from the setup field and select operators when none are selected.

**Pause** requests confirmation from the backend scheduler. After confirmation, its button becomes **Resume**. Work already in flight may finish. Pause/resume is unavailable for browser simulations.

**Abort / ×** asks to stop the scheduler when a mission is running. It waits for backend confirmation and reports failures to confirm. It does not guarantee immediate termination of existing subprocesses. When idle, it resets the mission display.

Successful lifecycle completion is not proof that a novel vulnerability was discovered or that every advertised attack phase is implemented.

## Source

[Homepage](../../docs/index.html): command markup, `startMissionFromDashboard`, `controlMission`, `abortMission`, `updateMissionTimer`, and `updateQualityDisplay`.
