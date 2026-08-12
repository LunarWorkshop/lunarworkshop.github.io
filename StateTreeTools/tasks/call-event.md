---
title: CallEvent
---

# CallEvent

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Events
**Availability:** StateTree Tools **3.0+**

Calls any static `BlueprintCallable` function by name without needing an actor or component target. This is useful for Blueprint library functions and other static runtime helpers that should be triggered directly from StateTree.

`BlueprintPure` functions are excluded. Delegate-typed parameters are also excluded.

---

## Configuration

### Class
Set this to the class that owns the static function you want to call.

### Event Name
Select the function to call from the dropdown. Only static, non-editor-only, non-pure `BlueprintCallable` functions with supported input parameters are shown.

Functions that take a world context parameter hide that parameter from the generated inputs when the engine can supply it automatically. This includes script-generated hidden world-context parameters.

### Parameters
Auto-populated when **Event Name** is selected. One field appears per supported input parameter of the chosen function. Fill in or bind each field as needed.

---

## When to Fire

By default the function is called when the state is **entered**. You can also call it on **exit**, with separate toggles for which exit reasons trigger the call (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/StateTreeTools/enter-exit-firing) for a full explanation.

---

## Error Handling

If the selected class is invalid, the function can no longer be found, or the function signature no longer matches the generated parameters at runtime, the task will fail. You can control whether that produces **Failed** or **Succeeded** using **Error Means Failure**.

[â† Back to Utilities | Events](/StateTreeTools/tasks/events) Â· [â† Back to home](/StateTreeTools/)
