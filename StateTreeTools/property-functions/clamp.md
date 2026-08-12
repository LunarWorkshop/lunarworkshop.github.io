---
title: Clamp
---

# Clamp

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Constrains **Value** to lie within the range `[Min, Max]`. If **Value** is below **Min** it is raised to **Min**; if it is above **Max** it is lowered to **Max**; otherwise it is returned unchanged. Use this to enforce safe limits on parameters such as speed, volume, or animation blend weight.

---

## Configuration

### Value
The float value to clamp.

### Min
The lower bound. Defaults to `0`.

### Max
The upper bound. Defaults to `1`.

### Result
**Value** constrained to `[Min, Max]`.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[â† Back to Math \| Float](/StateTreeTools/property-functions/math-float) Â· [â† Back to home](/StateTreeTools/)
