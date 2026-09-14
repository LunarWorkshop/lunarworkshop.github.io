---
title: Project
---

# Project

The Project tab is the first tab in Debug Tools. It contains the Editor Utility Widget dashboard selected by the project, giving the team a curated home for game-specific debug controls.

![Project tab with a project-authored console variable and Debug Option dashboard](../assets/screenshots/project-dashboard.png)

---

## Add Project Content

Create an Editor Utility Widget Blueprint derived from `DebugToolsRootWidget`, build the dashboard in UMG, and assign it under:

**Project Settings -> Plugins -> Debug Tools -> Root Panel Widget Class**

The open Debug Tools panel refreshes when the setting changes or when the selected Blueprint recompiles.

See [Root Widget Overrides](/DebugTools/customization/root-widget-overrides) for setup and [Dashboard Widgets](/DebugTools/customization/dashboard-widgets) for reusable controls.

## Without a Project Widget

When no valid project widget is assigned, the Project tab displays setup instructions. The other five tabs remain fully available.

[Back to tabs](/DebugTools/tabs/) · [Back to home](/DebugTools/)
