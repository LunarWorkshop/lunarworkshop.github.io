---
title: WaitForWidgetDelegate
---

# WaitForWidgetDelegate

**Plugin:** StateTreeToolsCore
**Category:** UI
**Availability:** StateTree Tools **3.0+**

Waits for one Blueprint-assignable multicast delegate on a bound `UUserWidget`. When the selected delegate fires, the task copies supported payload values into fixed generic outputs and completes.

WaitForWidgetDelegate does not tick. On Unreal versions where StateTree supports async task completion, it stays active and is considered for state completion until the delegate fires.

> âš ï¸ **StateTree tick required**
>
> WaitForDelegate and WaitForWidgetDelegate only work if the owning StateTree keeps ticking.
> These tasks complete asynchronously, but transition processing still happens inside StateTree update passes.
> If the StateTree is not ticking (for example while paused without tick-when-paused), the delegate can fire and the task can mark completion, but transitions will not be processed.

---

## Configuration

### Widget
Bind this to the widget whose delegate you want to wait for.

### Widget Class
Set this to the Blueprint class of the widget. This is used in the editor to populate the delegate dropdown and validate that the selected delegate still exists.

### Delegate Name
Select the delegate to wait for from the dropdown.

Only Blueprint-assignable inline multicast delegates with supported signatures are shown. Sparse delegates are not supported.

### Delegate Outputs Used
Read-only multiline legend showing which delegate parameters are copied into which output properties.

Example:

```text
ClickedWidget -> UserWidgetOutput1
ButtonIndex -> IntOutput1
```

Unsupported parameters are ignored and are not listed in the legend.

---

## Outputs

WaitForWidgetDelegate exposes fixed generic outputs. The selected delegate determines which ones are populated.

Supported generic output types:
- `BoolOutput1`, `BoolOutput2`
- `FloatOutput1`, `FloatOutput2`
- `IntOutput1`, `IntOutput2`
- `NameOutput1`, `NameOutput2`
- `StringOutput1`, `StringOutput2`
- `TextOutput1`, `TextOutput2`
- `ActorOutput1`, `ActorOutput2`
- `ActorComponentOutput1`, `ActorComponentOutput2`
- `UserWidgetOutput1`, `UserWidgetOutput2`
- `HitResultOutput`

For primitive payloads, one-parameter delegates and every ordered two-parameter combination of `bool`, `float`, `int32`, `FName`, `FString`, and `FText` are supported.

Common widget, actor, component, hit result, enum, and engine event payload signatures are also supported. Enum and other unsupported parameters can still be accepted for completion, but they are ignored for outputs unless they map to one of the generic output types above.

---

## Runtime Behaviour

When the state enters, WaitForWidgetDelegate resolves the widget, binds to the chosen delegate, and returns Running.

When the delegate fires:
- Supported payload values are copied into the generic outputs.
- The task unbinds from the delegate.
- The task finishes successfully.

If the state exits before the delegate fires, the task unbinds cleanly.

The task completes only once, even if the underlying delegate fires multiple times.

---

## Error Handling

If the widget is invalid, the delegate has been renamed or deleted, or the delegate signature is unsupported, the task fails. You can control whether a failure causes the task to return Failed or Succeeded using **Error Means Failure**.

The editor validates the selected delegate when Widget Class is set, so renamed or deleted delegates are caught at compile time when possible.

[â† Back to UI](/StateTreeTools/tasks/ui) Â· [â† Back to home](/StateTreeTools/)
