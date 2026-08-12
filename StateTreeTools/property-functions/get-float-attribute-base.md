---
title: Get Float Attribute Base
---

# Get Float Attribute Base

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Attributes

Returns the base value of a Gameplay Attribute on an actor's Ability System Component â€” the value before any transient gameplay effects are applied. Use this when you need to read an attribute's underlying permanent value rather than its current modified state, for example to display an unmodified stat or to compare a base value against a threshold for a persistent transition.

---

## Configuration

### Actor
The actor whose Ability System Component holds the attribute. Bind this to the actor you want to query.

### Attribute
The `FGameplayAttribute` to read. Select the attribute from the picker in the details panel.

### AttributeValue
The base value of **Attribute** on **Actor**'s Ability System Component, before transient modifiers are applied.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[â† Back to Gameplay Attributes](/StateTreeTools/property-functions/gameplay-attributes) Â· [â† Back to home](/StateTreeTools/)
