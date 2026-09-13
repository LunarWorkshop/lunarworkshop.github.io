---
title: Debug Options
---

# Debug Options

Debug Options are gameplay-tagged values that can be edited from Debug Tools and read by game logic. Use them for tunable debug behavior such as enabling an overlay, changing movement speed, selecting an encounter, or forcing a test state.

---

## Define Project Defaults

Open **Project Settings -> Plugins -> Debug Tools** and add entries under **Debug Options -> Defaults**.

Each default has:

- **Debug Option Key**: a gameplay tag from the `DebugOptionsCategory` tag category
- **Name**: an optional friendly label
- **Value type**: Bool, Float, Int, String, Name, or Gameplay Tag
- the default value for the selected type

Project defaults are shared through project configuration. A tag without an explicit entry behaves as an implicit Bool option whose default is false.

## Create a Saved Control

1. Open the **Debug Options** tab.
2. Choose a **Debug Option Key**.
3. Confirm or select its **Value type**.
4. Click **Create Widget**.

The saved row uses an appropriate control for its type: a checkbox, numeric control, text field, name field, or gameplay-tag picker.

<!-- Screenshot needed: Populated Debug Options tab showing all six value types. -->

## Configure a Control

The gear menu supports:

- a custom **Name**
- the value type and default value
- **Update all hosts**
- **Enable with option**, which adds a checkbox backed by another Bool Debug Option
- minimum and maximum values for Float and Int controls

The enable option should be configured as Bool. The panel warns when its configured type is different.

## Defaults and Overrides

The row actions distinguish team defaults from personal defaults:

| Action | Result |
|--------|--------|
| Reset to Saved | Restore the local override, project default, or implicit type default |
| Save (Project) | Save the current value as the project's default |
| Save (Local Override) | Save the current value as this user's default in the editor and PIE |
| Clear Override | Remove the local override and reveal the project default |

The panel's **Reset Console Variables and Debug Options** button resets every Debug Option to its effective saved default.

## Runtime and Multiplayer

Game logic can read and change the same values through Blueprint or C++. It can also listen for changes. See [Runtime Debug Options](/DebugTools/runtime/debug-options).

With multiplayer controls enabled, changes can be sent to every host or to one selected host. See [Multiplayer Targeting](/DebugTools/multiplayer-targeting).

## Manage Saved Controls

Drag the `|||` handle to reorder rows. Use the actions menu to **Duplicate** or **Delete** a row. The layout is saved automatically for the current user.

[Back to tabs](/DebugTools/tabs/) · [Back to home](/DebugTools/)
