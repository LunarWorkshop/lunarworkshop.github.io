---
title: Getting Started
---

# Getting Started

## Supported Versions

StateTree Tools supports Unreal Engine 5.1 through 5.7. Most features are available on all supported versions.

| Feature | UE 5.1 | UE 5.2 | UE 5.3 | UE 5.4 | UE 5.5 | UE 5.6 | UE 5.7 |
|---------|--------|--------|--------|--------|--------|--------|--------|
| Tasks | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ |
| Conditions | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ |
| Components | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ | âœ“ |
| Property Functions | â€” | â€” | â€” | â€” | âœ“ | âœ“ | âœ“ |
| Demo content | â€” | â€” | â€” | â€” | â€” | âœ“ | âœ“ |

---

## Install the plugin

Purchase StateTree Tools on Fab and add it to your engine version from the Epic Games Launcher. The plugin comes with precompiled binaries so no source compilation is needed.

## Enable the plugin

Open your project in Unreal Engine, then go to **Edit â†’ Plugins**. Search for **StateTree Tools** and enable whichever sub-plugins you need:

- **StateTree Tools Core** â€” tasks, property functions, and components for general use
- **StateTree Tools Gameplay Ability System** â€” GAS-specific tasks, conditions, property functions, and components. This sub-plugin only becomes available when Unreal's built-in **Gameplay Abilities** plugin is enabled.

Restart the editor when prompted.

## Enable dependencies

StateTree Tools Core requires the **GameplayStateTree** plugin. StateTree Tools Gameplay Ability System additionally requires **Gameplay Abilities**. Both are built-in Unreal plugins â€” enable them in the same Plugins window if they are not already on.

If **Gameplay Abilities** is disabled, StateTree Tools still loads normally, but the **StateTree Tools Gameplay Ability System** sub-plugin and all GAS-specific nodes stay unavailable.

## Start building

Create a StateTree asset (**Content Browser â†’ Add â†’ StateTree**) and add a `StateTreeComponent` to an actor. StateTree Tools nodes will appear in the task, condition, and property function pickers inside the StateTree editor alongside the built-in ones.

[â† Back to home](/StateTreeTools/)
