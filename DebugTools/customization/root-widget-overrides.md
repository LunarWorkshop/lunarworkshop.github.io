---
title: Root Widget Overrides
---

# Root Widget Overrides

A Root Widget Override adds a project-specific Editor Utility Widget to the Debug Tools panel. Use it for a curated dashboard of the controls most important to your game.

The custom content appears above the shared **Console**, **Debug Commands**, **Debug Options**, **Save Game**, and **Show Debug** tabs; it does not remove those tools.

---

## Create the Widget

1. Create an **Editor Utility Widget Blueprint**.
2. Choose `DebugToolsRootWidget` as its parent class.
3. Design the dashboard in the UMG Designer.
4. Open **Project Settings -> Plugins -> Debug Tools**.
5. Assign the Blueprint to **Root Panel Widget Class**.
6. Open or return to the Debug Tools panel.

The panel refreshes when the setting changes and when the selected Blueprint recompiles.

<!-- Screenshot needed: UMG Designer for a DebugToolsRootWidget Blueprint containing several Debug Tools palette widgets. -->

## Add Controls

The UMG palette includes ready-made Debug Tools widgets for console commands, console variables, Debug Commands, Debug Options, and custom save-data structs. See [Dashboard Widgets](/DebugTools/customization/dashboard-widgets).

Ordinary UMG layout widgets, text, images, and project-specific Editor Utility Widget logic can be used around them.

## Fallback Behavior

When no Root Panel Widget Class is assigned, Debug Tools displays a built-in message explaining how to create one. If the assigned class cannot be loaded or is not a valid `DebugToolsRootWidget` subclass, the panel falls back to that built-in content and displays a warning.

[Back to customization](/DebugTools/customization/) · [Back to home](/DebugTools/)
