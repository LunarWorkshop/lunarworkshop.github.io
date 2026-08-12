---
title: Enter / Exit Firing
---

# Enter / Exit Firing

Many StateTree Tools tasks can fire their action when a state is **entered**, when it is **exited**, or on **both**. This is controlled by a pair of options on the task: **Call On Enter State** and **Call On Exit State** (the exact names vary by task).

---

## Firing on Enter

When **Call On Enter State** is enabled, the action fires immediately as the state is entered. If exit firing is not also enabled, the task completes right away and does not hold the state open.

This is the default for most tasks and is the right choice for fire-and-forget actions â€” playing a sound, triggering an animation, sending an event.

## Firing on Exit

When **Call On Exit State** is enabled, the task stays **Running** for as long as the state is active, then fires the action as the state is leaving. Because the task holds a Running status, it will appear as an active task in the StateTree debugger for the duration of the state.

When only exit firing is enabled, nothing happens on enter â€” the task simply waits.

### Exit Conditions

When exit firing is on, three additional options let you control *which* kind of exit triggers the action:

| Option | Default | Description |
|--------|---------|-------------|
| On Exit â€” Stopped | Off | Fire when the state is interrupted or the StateTree is stopped externally |
| On Exit â€” Succeeded | On | Fire when the state exits because it succeeded normally |
| On Exit â€” Failed | Off | Fire when the state exits because it failed |

You can enable any combination of these. If none are enabled, the action will never fire on exit â€” the editor will warn you about this when the StateTree is compiled.

## Firing on Both

When both enter and exit firing are enabled, the action fires twice: once on enter and once on exit (subject to the exit conditions above). The task stays Running between the two.

---

## State Completion Behaviour

StateTree Tools separates tasks into two completion styles:

| Style | Behaviour | Examples |
|-------|-----------|----------|
| **Completion-aware wait tasks** | Stay **Running** until the external operation they started or subscribed to finishes. On UE 5.8+, these tasks participate in StateTree's native task-completion tracking, so **On State Completed** transitions can advance when the waited operation completes. | StartActionAndWait, PlayMontage, SpawnSound2D, SpawnSoundAtLocation, SpawnSystemAtLocation, SpawnSystemAttached, Create Widget, TryActivateAbilityByClass, WaitForDelegate, WaitForWidgetDelegate, Wait For Gameplay Tag Added/Removed |
| **Instant side-effect tasks** | Fire once and immediately succeed. They do not hold the state open and are not treated as completion-relevant tasks. | CallActorEvent, CallComponentEvent, CallActorDelegate, CallComponentDelegate, SetActorProperty, SetComponentProperty, SendStateTreeEvent, PlaySound2D, PlaySoundAtLocation, input-mode tasks, debug helpers |

A useful rule of thumb: if StateTree Tools can observe the thing ending, the task can be completion-aware. If the engine API only fires a one-shot side effect and gives the task nothing to observe, the task remains instant.

This matters most for **On State Completed** transitions in parent or leaf states. Use completion-aware tasks when the state should wait for work to finish; use instant tasks when the state should just perform a side effect and let another condition, delegate, event, or transition decide what happens next.

## At a Glance

The task's label in the StateTree editor reflects the current setting:

| Label | Meaning |
|-------|---------|
| **(Enter)** | Fires on enter only |
| **(Exit)** | Fires on exit only |
| **(Enter\|Exit)** | Fires on both |

---

## Compile Validation

If a task is configured such that it would never fire â€” enter is off, and either exit is also off or all exit conditions are disabled â€” the StateTree editor will report a compile error on that task.
