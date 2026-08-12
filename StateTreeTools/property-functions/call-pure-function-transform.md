---
title: Call Pure Function (Transform)
---

# Call Pure Function (Transform)

**Plugin:** StateTreeToolsCore
**Category:** Utilities \| Transform

Calls a `BlueprintPure` function on an actor (or one of its components) at runtime and exposes the return value as a bindable `FTransform` output. Use this to retrieve a full transform (location, rotation, and scale) computed by Blueprint logic â€” for example a spawn transform or a socket transform.

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
The `BlueprintPure` function to call. Only functions with a return value compatible with `FTransform` are shown in the dropdown.

#### ReturnValueName
The output parameter of the function to read. This is usually `ReturnValue` for single-output functions.

### Value
The `FTransform` result returned by the called function.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[â† Back to Call Pure Function](/StateTreeTools/property-functions/call-pure-function) Â· [â† Back to home](/StateTreeTools/)
