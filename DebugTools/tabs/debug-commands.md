---
title: Debug Commands
---

# Debug Commands

Debug Commands turn Blueprint-callable functions into saved buttons. They are useful for actions that need typed parameters, Actor selection, output values, or latent completion and would be awkward to expose as console commands.

---

## Create a Debug Command

1. Open the **Debug Commands** tab.
2. Leave **Target class** empty to choose a global/static function, or select an Actor class to choose an instance function.
3. Select a function from **Function**.
4. Enter an optional **Display label**.
5. Click **Create Saved Widget**.

The function picker shows supported `BlueprintCallable` functions. When a source Blueprint or C++ class can be opened, the saved row provides a shortcut to its definition.

<!-- Screenshot needed: Debug Command Builder with an Actor class and BlueprintCallable function selected. -->

## Parameters and Results

Saved commands expose editable controls for supported input parameters:

- Bool
- Float
- Int32
- String
- Name
- Gameplay Tag
- Enum

Return values and output parameters are shown as transient result text when the function finishes. Latent functions keep the command busy until latent execution completes, preventing the same row from being started repeatedly while it is already running.

Functions with unsupported parameter requirements are not runnable and explain why in the control's tooltip.

## Static and Instance Commands

With no Target class, Debug Tools calls a supported static/global Blueprint-callable function.

With a Target class, Debug Tools finds matching Actor instances in the selected world. **Instance reduction** controls what happens when more than one exists:

| Mode | Behavior |
|------|----------|
| Singleton | Run only when exactly one matching Actor exists |
| First available | Run on the first valid matching Actor |
| All | Run on every matching Actor |

## Execution and Shortcuts

Use **Run in** to enable the command for the Editor world, PIE, or both. A PIE-only command is disabled until PIE starts and displays a `[PIE]` prefix.

The **PIE input** field assigns a keyboard shortcut that runs while the PIE viewport has keyboard focus. Debug Tools warns when the same key is assigned to another saved command or appears in an Enhanced Input Mapping Context.

## Multiplayer Targeting

When **Update all hosts** is enabled, a PIE command runs on every checked host that can execute it. Disable it to choose one host from the row's host picker.

See [Multiplayer Targeting](/DebugTools/multiplayer-targeting).

## Manage Saved Commands

Drag the `|||` handle to reorder rows. The actions menu can **Duplicate** or **Delete** a saved command. Changes are saved automatically for the current user.

[Back to tabs](/DebugTools/tabs/) · [Back to home](/DebugTools/)
