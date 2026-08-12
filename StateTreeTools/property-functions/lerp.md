---
title: Lerp
---

# Lerp

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Linearly interpolates between **Left** and **Right** by the factor **Alpha**. At `Alpha = 0` the result equals **Left**; at `Alpha = 1` the result equals **Right**. Values of Alpha outside `[0, 1]` extrapolate beyond the endpoints. Use this to blend between two float parameters â€” for example fading a volume or blending between two speeds based on a normalized input.

---

## Configuration

### Left
The value returned when **Alpha** is `0`.

### Right
The value returned when **Alpha** is `1`. Defaults to `1`.

### Alpha
The interpolation factor. Typically in `[0, 1]`.

### Result
`Left + (Right - Left) * Alpha`.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[â† Back to Math \| Float](/StateTreeTools/property-functions/math-float) Â· [â† Back to home](/StateTreeTools/)
