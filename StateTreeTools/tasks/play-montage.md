---
title: Play Montage
---

# Play Montage

**Plugin:** StateTreeToolsCore
**Category:** Animation

Plays an animation montage on a Skeletal Mesh Component and keeps the task running until the montage ends. Output delegate dispatchers fire for each montage lifecycle event â€” Completed, Interrupted, BlendOut, and BlendedIn â€” so downstream states or transitions can react to each phase.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Skeletal Mesh Component you want to animate. The component is resolved automatically based on the Setup.

### Setup
Editor-only helper that stores the actor class and the name of the Skeletal Mesh Component to use. The actor class is auto-populated from the Actor binding; the component picker filters to `USkeletalMeshComponent`.

### Montage To Play
The `UAnimMontage` asset to play.

### Play Rate
Playback speed multiplier. Default is `1.0`.

### Start Position
Time offset in seconds at which playback begins within the montage. Default is `0.0`.

### Start Section
The montage section to jump to when playback starts. Leave as `None` to start from the beginning.

### Stop All Montages
When enabled, all other montages playing on the same Anim Instance are stopped before this one starts. Default is `true`.

### Stop Montage On Exit
When enabled the montage is stopped and blended out when the task exits (e.g. because a higher-priority transition fired). Default is `true`. When disabled the montage continues playing after the state exits.

### Interruption Means Failure
When enabled the task completes with **Failed** status if the montage is interrupted. Default is `false`.

### On Completed / On Completed Event
Fires when the montage plays through to its natural end. Bind the `FStateTreeDelegateDispatcher` output to other parts of the tree, or configure the `OutputEventAction` to dispatch a StateTree event automatically.

### On Interrupted / On Interrupted Event
Fires when the montage is interrupted (for example by another montage). Configure the `OutputEventAction` to dispatch a StateTree event if needed.

### On Blend Out / On Blend Out Event
Fires when the montage begins blending out. Configure the `OutputEventAction` to dispatch a StateTree event if needed.

### On Blended In / On Blended In Event
Fires when the montage finishes blending in and is fully active. Configure the `OutputEventAction` to dispatch a StateTree event if needed.

---

## Unreal Engine Version Notes

### UE 5.6 and later
- Task completes asynchronously the instant the montage ends â€” no per-frame tick is needed.
- All four delegate dispatcher outputs (**On Completed**, **On Interrupted**, **On Blend Out**, **On Blended In**) fire at the exact moment each montage lifecycle event occurs.
- All four `OutputEventAction` fields dispatch their configured StateTree events immediately when each callback fires.
- Any StateTree compiled in UE 5.5 must be recompiled after upgrading to 5.6 for correct behaviour.

### UE 5.5
- Task completes via a per-frame tick that polls a shared completion flag. There is a one-frame delay between the montage ending and the task completing.
- Any StateTree compiled in UE 5.6 must be recompiled after downgrading to 5.5 for correct behaviour.
- **Delegate dispatcher outputs** (**On Completed**, **On Interrupted**, **On Blend Out**, **On Blended In**) appear in the details panel but are non-functional â€” `FStateTreeDelegateDispatcher` does not exist before UE 5.6 and these fields compile as no-op placeholders.
- **On Completed Event** and **On Interrupted Event** still dispatch their configured StateTree events (fired from the tick).
- **On Blend Out Event** and **On Blended In Event** do **not** fire on UE 5.5. These callbacks are not tracked in the 5.5 code path.

---

## Error Handling

If the Actor is invalid, the Skeletal Mesh Component is not found, or the montage cannot be played, the task will fail. The task inherits **Error Means Failure** from `FStateTreeTools_TaskCommon`.

[â† Back to Animation](/StateTreeTools/tasks/animation) Â· [â† Back to home](/StateTreeTools/)
