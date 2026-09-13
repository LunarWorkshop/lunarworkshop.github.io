---
title: Console
---

# Console

The Console tab turns frequently used console objects into a personal, saved control board. It supports console commands, `Exec` commands, and bool, int, and float console variables.

---

## Find and Save a Console Object

The **Console Widget Builder** searches objects registered in the current editor session. Search is case-insensitive and supports fuzzy matching; spaces in the search do not need to appear in the target name.

Results include the name, available help text, and object type. The picker searches:

- console commands
- Blueprint/C++ `Exec` commands
- Bool CVars
- Int32 CVars
- Float CVars

Select a result and click **Create Widget**. Commands and variables share one ordered saved list.

<!-- Screenshot needed: Console Widget Builder search results showing a command, exec command, bool CVar, int CVar, and float CVar. -->

## Console and Exec Commands

Click the main button to run a command. Open the gear menu to configure:

- **Display label**
- whether it can run in **Editor**, **PIE**, or both
- whether PIE execution updates every host
- a **PIE input** keyboard shortcut
- raw or typed parameters when the selected command exposes them

PIE-only controls display a subdued `[PIE]` prefix and remain disabled until PIE is running.

For a normal console command, **Arguments** is raw text appended after the command name. Exec commands can expose typed Bool, Float, Int32, String, Name, Gameplay Tag, and Enum parameter controls.

Keyboard shortcuts run while the PIE viewport has keyboard focus. Debug Tools warns when a key is already used by another saved Debug Tools command or by an Enhanced Input Mapping Context.

## Console Variables

Bool CVars use a checkbox. Int and float CVars use a numeric control that supports dragging and direct text entry. Changes update the live console variable immediately.

For an Int32 CVar, enable **Treat as boolean** to show a checkbox that writes zero or one.

Numeric controls support optional minimum and maximum bounds. The range limits values written through the widget; adding a range does not rewrite an existing live value simply because it falls outside the range.

If a saved console object is missing or has changed to an incompatible type, its control is disabled instead of being deleted.

## Save and Reset CVar Values

The actions menu for a CVar includes:

| Action | Result |
|--------|--------|
| Reset Value | Restore the CVar's registration default |
| Save (Project) | Save the current value in a selected project configuration file |
| Save (Local Override) | Save the current value for this user only |
| Reset to saved | Restore the local override, then project value, then registration default |
| Clear Saved | Remove saved project and local values for this CVar |

When more than one project config file is suitable, **Save (Project)** asks which file to update. Source-controlled files are checked out through the project's configured source-control provider when possible.

The panel's **Reset Console Variables and Debug Options** button resets all CVars in the saved Console list to their registration defaults. Debug Options are reset to their effective saved defaults at the same time.

## Multiplayer Targeting

Commands and CVars can update every available checked PIE host. Disable **Update all hosts** to choose one host from the row's host picker. See [Multiplayer Targeting](/DebugTools/multiplayer-targeting).

## Organize the List

- Drag the `|||` handle to reorder a row.
- Choose **Duplicate** to make an independently editable copy.
- Choose **Delete** to remove a saved row.

The list and its settings are saved automatically. See [User Data and Persistence](/DebugTools/customization/user-data).

[Back to tabs](/DebugTools/tabs/) · [Back to home](/DebugTools/)
