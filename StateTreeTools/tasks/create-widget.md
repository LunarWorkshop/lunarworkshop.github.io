---
title: Create Widget
---

# Create Widget

**Plugin:** StateTreeToolsCore
**Category:** UI
**Availability:** StateTree Tools **2.0+**

Creates a `UUserWidget` from a widget class, optionally adds it to the viewport, and outputs the created widget so other nodes can reference it.

---

## Configuration

### Widget Class
The widget class to instantiate.

### Player Controller
Optional owning player for the widget. Bind this when the widget should belong to a specific local player or player controller context.

### Expose On Spawn Properties
Automatically populated from the selected **Widget Class**. Any widget properties marked **Expose on Spawn** appear here and can be filled in directly or bound from elsewhere in the StateTree.

StateTree Tools **2.0+** adds array support for expose-on-spawn properties, so array-valued widget inputs can be supplied directly through this section.

### Add To Viewport
When enabled, the created widget is immediately added to the viewport.

### ZOrder
Only shown when **Add To Viewport** is enabled. Higher values appear in front of lower values.

### Remove From Parent On Exit
When enabled, the task calls `RemoveFromParent()` on the created widget when the state exits.

### Widget
Output reference to the created widget. Other StateTree nodes or game code can bind this output. **If something else keeps a strong reference** to the same `UUserWidget` instance, the object can remain allocated even when it is not shown in the viewport.

---

## Runtime Behaviour

### UE 5.6 and later
The task creates the widget and then **stays running** until the **`UUserWidget` is destroyed** (the engine calls `OnNativeDestruct` / `Destruct` as part of teardown). It completes asynchronously without using per-frame tick.

**Completion is not the same as “removed from screen.”** Taking the widget out of the viewport — for example with `RemoveFromParent`, or clearing the slot that held it — **does not necessarily destroy** the `UUserWidget`. It is a `UObject`; if **any** strong reference remains (another `UObject` field, a stored `TObjectPtr`, a Blueprint variable, a delegate that pins the object, etc.), the instance can stay **alive off-screen** while your task is still **Running**, because destruction (and thus the normal completion path for this task) has not happened yet.

**Practical guidance:**
- Clear or avoid long-lived strong references to the output widget when the UI should be fully dismissed, or use **weak** references (`TWeakObjectPtr`) from consumers that only need to test validity.
- If you must not rely on destruction timing, drive state completion with an **explicit** signal (e.g. a button callback or custom event) instead of assuming the task will finish as soon as the widget disappears from the viewport.

### UE 5.5 and earlier
The task creates the widget and succeeds immediately after creation. Earlier StateTree versions do not support the same async completion path used by newer engine versions.

---

## Error Handling

If the widget class is invalid, widget creation fails, or the expose-on-spawn properties no longer match the selected widget class at runtime, the task will fail. You can control whether that produces **Failed** or **Succeeded** using **Error Means Failure**.

[← Back to UI](/StateTreeTools/tasks/ui) · [← Back to home](/StateTreeTools/)
