---
title: Root Widget Overrides
---

# Root Widget Overrides

Debug Tools supports a single project-selected root widget override.

This lets a project replace the main content area of the Debug Tools panel with a custom **User Widget Blueprint** while still keeping the shared plugin-owned panel frame and built-in tabs.

---

## How it works

The plugin provides a base widget class named `DebugToolsRootWidget`.

Create a **User Widget Blueprint** that subclasses `DebugToolsRootWidget`, then assign it in:

**Project Settings -> Plugins -> Debug Tools**

using **Root Panel Widget Class**.

Once assigned:

- Opening the Debug Tools panel uses your widget as the root content area
- Changing the setting refreshes any open Debug Tools panels immediately
- Recompiling the selected Blueprint also refreshes any open Debug Tools panels

---

## If nothing is assigned

If no override is configured, Debug Tools falls back to the built-in placeholder root widget. That placeholder exists to keep the panel usable and to explain how to install a project override.

---

## What stays shared

Even with a custom root widget, the shared Debug Tools frame remains in place. Built-in plugin tabs, such as **Console**, continue to appear as part of the shared panel shell.

[← Back to customization](/DebugTools/customization)
