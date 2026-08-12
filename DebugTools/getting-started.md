---
title: Getting Started
---

# Getting Started

## What Debug Tools adds

Once enabled, Debug Tools adds a **Debug Tools** entry to the **Tools** section of Unreal Editor's **Tools** menu. Opening it creates a dockable panel similar to other built-in editor panels such as Gameplay Tag Manager or Class Viewer.

The panel has two layers:

- A shared plugin-owned frame that always exists
- An optional project-owned root widget override that can fill the main content area

The shared frame currently includes a built-in **Console** tab for searching and saving console commands.

---

## Enable the plugin

Open **Edit -> Plugins**, search for **Debug Tools**, and enable it. Restart the editor if Unreal prompts you to do so.

---

## Open the panel

Open **Tools -> Debug Tools**.

If no project override has been configured yet, the panel opens with the built-in placeholder root and the shared Console tab.

---

## Use the Console tab

The Console tab lets you:

- Search all enabled console commands in the project
- Use case-insensitive sloppy matching while searching
- Save selected commands as clickable buttons
- Reorder and remove saved buttons
- Reuse those saved buttons across editor restarts

See [Console](/DebugTools/tabs/console) for details.

---

## Replace the root area with your own widget

If you want a project-specific debug dashboard:

1. Create a **User Widget Blueprint** subclass of `DebugToolsRootWidget`
2. Open **Project Settings -> Plugins -> Debug Tools**
3. Assign your widget to **Root Panel Widget Class**

The panel refreshes when that setting changes, and it also refreshes when the selected Blueprint recompiles.

See [Root Widget Overrides](/DebugTools/customization/root-widget-overrides) for the full workflow.

[← Back to home](/DebugTools/)

