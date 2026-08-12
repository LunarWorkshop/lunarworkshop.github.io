---
title: Call Pure Function (Double)
---

# Call Pure Function (Double)

**Plugin:** StateTreeToolsCore
**Category:** Utilities \| Float

Calls a `BlueprintPure` function on an actor (or one of its components) at runtime and exposes the return value as a bindable `double` output. Use this when full double-precision is needed â€” for example for large world coordinates or high-precision timing values.

The Setup section provides a custom details panel: select an **ActorClass** to populate a dropdown of compatible pure functions, then choose the function and the specific output parameter to read.

---

## Configuration

### Actor
The actor instance to call the function on. Bind this to the actor you want to query.

### Setup

#### ActorClass
The class of actor used to populate the function picker. Set this to the class that defines the function you want to call.

#### ComponentName
Optional. If set, the function is called on the named component of the actor rather than the actor itself.

#### FunctionName
The `BlueprintPure` function to call. Only functions with a return value compatible with `double` are shown in the dropdown.

#### ReturnValueName
The output parameter of the function to read. This is usually `ReturnValue` for single-output functions.

### Value
The `double` result returned by the called function.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[â† Back to Call Pure Function](/StateTreeTools/property-functions/call-pure-function) Â· [â† Back to home](/StateTreeTools/)
