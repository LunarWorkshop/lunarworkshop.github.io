---
title: Select Float
---

# Select Float

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Returns one of two float values based on a boolean condition. When **bPickLeft** is `true` the result is **Left**; when `false` the result is **Right**. Use this as an inline conditional to choose between two parameter values without needing a separate transition â€” for example selecting a fast speed or a slow speed depending on an alert flag.

---

## Configuration

### Left
The value returned when **bPickLeft** is `true`.

### Right
The value returned when **bPickLeft** is `false`.

### bPickLeft
The selector. When `true`, **Left** is returned; when `false`, **Right** is returned. Defaults to `true`.

### Result
Either **Left** or **Right** depending on **bPickLeft**.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[â† Back to Math \| Float](/StateTreeTools/property-functions/math-float) Â· [â† Back to home](/StateTreeTools/)
