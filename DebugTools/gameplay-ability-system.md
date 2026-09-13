---
title: Gameplay Ability System
---

# Gameplay Ability System

When Unreal's **Gameplay Abilities** plugin is enabled, Debug Tools adds a **Gameplay Ability System** choice to the [Show Debug tab](/DebugTools/tabs/show-debug).

The rest of Debug Tools remains available when Gameplay Abilities is disabled.

---

## Enable the Integration

1. Open **Edit -> Plugins**.
2. Enable Unreal's **Gameplay Abilities** plugin.
3. Ensure **Debug Tools** is enabled.
4. Restart the editor when prompted.

Start PIE and choose **Gameplay Ability System** from the Show Debug dropdown.

## Categories

| Category | Shows |
|----------|-------|
| Attributes | Ability System attributes and their current values |
| Effects | Active Gameplay Effects |
| Abilities | Granted abilities and ability state |

Selecting a category sends the corresponding Ability System debug category command.

<!-- Screenshot needed: Gameplay Ability System Show Debug view with Attributes, Effects, and Abilities category buttons. -->

## Choose a Target

Select an Actor in the World Outliner while the view is active. Debug Tools maps the editor selection to its PIE counterpart and looks for the relevant Ability System Component.

You may select:

- an Actor that owns an Ability System Component directly
- an avatar whose Ability System Component belongs to another Actor, such as a Player State
- the owning Actor itself

Debug Tools resolves avatar-to-owner relationships before assigning the Show Debug target. If the selected Actor has no related Ability System Component, the view remains active but has no valid GAS target to display.

[Back to Show Debug](/DebugTools/tabs/show-debug) · [Back to home](/DebugTools/)
