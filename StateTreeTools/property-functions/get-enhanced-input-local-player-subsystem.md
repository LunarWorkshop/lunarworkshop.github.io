---
title: Get Enhanced Input Local Player Subsystem
---

# Get Enhanced Input Local Player Subsystem

**Plugin:** StateTreeToolsCore
**Category:** Enhanced Input
**Availability:** StateTree Tools **2.0+**

Returns the `UEnhancedInputLocalPlayerSubsystem` for the given player controller. Bind the output into [Add Mapping Context](/StateTreeTools/tasks/add-mapping-context) or [Remove Mapping Context](/StateTreeTools/tasks/remove-mapping-context) to drive Enhanced Input from a StateTree.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

## Configuration

### Player Controller
The player controller whose local player subsystem you want. If invalid, the output is None.

### Output
The `UEnhancedInputLocalPlayerSubsystem` for the given player controller, or None if the controller is invalid or has no local player.

---

[â† Back to Enhanced Input](/StateTreeTools/property-functions/enhanced-input) Â· [â† Back to home](/StateTreeTools/)
