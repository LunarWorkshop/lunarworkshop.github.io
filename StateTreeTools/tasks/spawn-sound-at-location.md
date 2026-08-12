---
title: Spawn Sound At Location
---

# Spawn Sound At Location

**Plugin:** StateTreeToolsCore
**Category:** Audio

Spawns a spatialized audio component at a world-space location and keeps the task running until the sound finishes naturally, at which point the task succeeds. If the state exits before the sound ends the audio component is stopped and destroyed. The spawned component is written to the **Spawned Sound Component** output so other tasks or conditions can reference it.

---

## Configuration

### Sound
The sound asset to play.

### Sound Attenuation *(optional)*
An attenuation settings asset that controls how the sound falls off with distance. Leave empty to use the sound's default attenuation settings.

### Sound Concurrency *(optional)*
A concurrency settings asset that controls how this sound behaves when multiple instances are requested. Leave empty to use the sound's default concurrency rules.

### Location
The world-space position at which the sound is spawned.

### Rotation
The initial world-space rotation of the audio component.

### Volume Multiplier
Scales the sound's base volume. Default is `1.0`.

### Pitch Multiplier
Scales the sound's base pitch. Default is `1.0`.

### Start Time
Playback start offset in seconds. Default is `0.0`.

### Auto Destroy
When enabled the audio component destroys itself after playback ends. Default is `true`.

### Spawned Sound Component *(output)*
Receives the `UAudioComponent` that was created. Bind downstream tasks or conditions to this output to control or query the playing sound.

---

## Unreal Engine Version Notes

### UE 5.6 and later
- Task completes asynchronously the instant the sound finishes â€” no per-frame tick is needed.
- The `OnAudioFinished` callback fires and immediately signals task completion via the async execution context.
- Any StateTree compiled in UE 5.5 must be recompiled after upgrading to 5.6 for correct behaviour.

### UE 5.5
- Task completes via a per-frame tick that polls a shared completion flag set by the `OnAudioFinished` callback. There is a one-frame delay between the sound ending and the task completing.
- Any StateTree compiled in UE 5.6 must be recompiled after downgrading to 5.5 for correct behaviour.

---

## Error Handling

If the Sound asset is not set the task will fail at compile time. The task inherits **Error Means Failure** from `FStateTreeTools_TaskCommon`.

[â† Back to Audio](/StateTreeTools/tasks/audio) Â· [â† Back to home](/StateTreeTools/)
