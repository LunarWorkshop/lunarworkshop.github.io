---
title: Nearly Equal
---

# Nearly Equal

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Returns `true` if **Left** and **Right** differ by no more than **ErrorTolerance**. This is the preferred way to compare floats for equality when the values may have accumulated small floating-point errors â€” for example when comparing a computed distance to a target distance.

---

## Configuration

### Left
The first float value.

### Right
The second float value.

### ErrorTolerance
The maximum absolute difference that still counts as equal. Defaults to `1e-6`.

### Result
`true` if `|Left - Right| <= ErrorTolerance`, otherwise `false`.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[â† Back to Math \| Float](/StateTreeTools/property-functions/math-float) Â· [â† Back to home](/StateTreeTools/)
