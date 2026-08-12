---
title: Try Activate Ability By Class
---

# Try Activate Ability By Class

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Abilities

Activates a gameplay ability by class on the bound actor's Ability System Component and keeps the task running until that specific ability instance ends. The task handles both `InstancedPerActor` and `InstancedPerExecution` instancing policies correctly. `NonInstanced` abilities (deprecated since UE 5.5) are not supported and will cause the task to fail with an error.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Ability System Component should activate the ability.

### Ability Class
The `UGameplayAbility` subclass to activate.

### Allow Remote Activation
When enabled the activation request is also forwarded to remote clients (non-authority). Default is `true`.

### Use Timeout
When enabled the task automatically fails after **Timeout Seconds** if the ability has not ended on its own. Default is `false`.

### Timeout Seconds
The maximum time to wait for the ability to end, in seconds. Only active when **Use Timeout** is enabled. Default is `10.0`.

### Cancellation Means Failure
When enabled the task completes with **Failed** status if the ability is cancelled rather than completing normally. Default is `false`.

### Cancel Ability On Exit
When enabled the task cancels the tracked ability instance when the state exits before the ability ends (for example due to a higher-priority transition). Default is `false`.

---

## Unreal Engine Version Notes

### UE 5.6 and later
- Task completes asynchronously the instant the ability ends â€” no per-frame tick is needed.
- The `OnAbilityEnded` callback fires and immediately signals task completion via the async execution context.
- The timeout timer (when enabled) also uses the async execution context to complete immediately.
- Any StateTree compiled in UE 5.5 must be recompiled after upgrading to 5.6 for correct behaviour.

### UE 5.5
- Task completes via a per-frame tick that polls a shared result flag set by the `OnAbilityEnded` callback or the timeout timer. There is a one-frame delay between the ability ending and the task completing.
- Any StateTree compiled in UE 5.6 must be recompiled after downgrading to 5.5 for correct behaviour.

---

## Error Handling

If the actor has no Ability System Component, the ability class is invalid, or the ability uses the `NonInstanced` policy, the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option inherited from `FStateTreeTools_TaskCommon`.

[â† Back to Abilities](/StateTreeTools/tasks/abilities) Â· [â† Back to home](/StateTreeTools/)
