---
title: Has Any Matching Gameplay Tags
---

# Has Any Matching Gameplay Tags

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Tags

Returns true if the bound actor's Ability System Component has **at least one** tag from the specified container. Use this when any one of several conditions being active is sufficient â€” for example, entering a disabled state if the actor has a "Stunned", "Frozen", or "Sleeping" tag.

Returns false if the actor has no Ability System Component or the container is empty.

---

## Configuration

### Actor
Bind this to the actor whose Ability System Component you want to check.

### Gameplay Tags
The container of tags to check. At least one tag from the container must be present on the ASC for the condition to pass. Each tag follows Unreal's standard tag hierarchy rules â€” a more specific tag satisfies a parent tag check.

### Invert
When enabled, the result is flipped â€” the condition passes when the actor has **none** of the tags. Default is off.

---

[â† Back to Gameplay Tags](/StateTreeTools/conditions/gameplay-tags) Â· [â† Back to home](/StateTreeTools/)
