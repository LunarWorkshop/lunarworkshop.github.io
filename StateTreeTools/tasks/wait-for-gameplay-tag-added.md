---
title: Wait For Gameplay Tag Added
---

# Wait For Gameplay Tag Added

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Tags

Keeps the task running until the specified gameplay tag is added to the bound actor's Ability System Component. When the tag is detected the **On Tag Changed** delegate dispatcher fires and the configured **Output Event** is dispatched, then the task succeeds.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Ability System Component should be monitored for the tag.

### Tag
The `FGameplayTag` to watch for. The task succeeds when this tag is added to the ASC.

### On Tag Changed *(output)*
A `FStateTreeDelegateDispatcher` that fires when the tag is added. Bind this output to other parts of the tree if you need to react to the change outside of normal task completion.

### Output Event
A `FStateTreeTools_OutputEventAction` that configures an optional StateTree event to dispatch automatically when the tag is added.

---

## Unreal Engine Version Notes

### UE 5.6 and later
- Task completes asynchronously the instant the tag is added â€” no per-frame tick is needed.
- The **On Tag Changed** delegate dispatcher fires at the exact moment the tag change is detected.
- The **Output Event** is dispatched immediately when the callback fires.
- The task is considered for StateTree completion tracking and finishes from the async callback, so **On State Completed** transitions can advance when the tag change is detected.
- Any StateTree compiled in UE 5.5 must be recompiled after upgrading to 5.6 for correct behaviour.

### UE 5.5
- Task completes via a per-frame tick that polls a shared flag set by the tag-change callback. There is a one-frame delay between the tag being added and the task completing.
- Any StateTree compiled in UE 5.6 must be recompiled after downgrading to 5.5 for correct behaviour.
- The **On Tag Changed** delegate dispatcher output appears in the details panel but is non-functional â€” `FStateTreeDelegateDispatcher` does not exist before UE 5.6 and the field compiles as a no-op placeholder.
- The **Output Event** still dispatches its configured StateTree event (fired from the tick).
- The task uses standard completion tracking (`bConsideredForCompletion = true`).

---

## Error Handling

If the actor is invalid or has no Ability System Component the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[â† Back to Abilities](/StateTreeTools/tasks/abilities) Â· [â† Back to home](/StateTreeTools/)
