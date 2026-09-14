---
title: Getting Started
---

# Getting Started

## Supported Versions

Debug Tools 1.0 supports Unreal Engine 4.27 and Unreal Engine 5.0 through 5.8. The same major features are available throughout that range.

| Unreal version | Panel menu |
|----------------|------------|
| UE 4.27 | **Window -> Debug Tools** |
| UE 5.0-5.8 | **Tools -> Debug Tools** |

---

## Install the plugin

Purchase Debug Tools on Fab and add it to your engine version from the Epic Games Launcher. The plugin comes with precompiled binaries so no source compilation is needed.

## Enable the plugin

Open your project in Unreal Engine, then go to **Edit â†’ Plugins**. Search for **Debug Tools** and enable it. Restart the editor when prompted.

## Enable dependencies

If **Gameplay Abilities** is enabled, Debug Tools will automatically activate its GAS-specific functionality. Otherwise, Debug Tools still loads normally and all GAS-specific functions stay unavailable.

## Open the Panel

Open **Window -> Debug Tools** in UE 4.27 or **Tools -> Debug Tools** in UE 5.0 and later. The panel can be docked like other Unreal Editor tabs.

The panel contains six tabs: **Project**, **Console**, **Debug Commands**, **Debug Options**, **Save Game**, and **Show Debug**. The first tab hosts an Editor Utility Widget dashboard supplied by the project.

![Debug Tools panel with the Project dashboard followed by the five built-in tabs](assets/screenshots/complete-panel.png)

## Create Your First Console Control

1. Open the **Console** tab.
2. Search for a console command or variable, such as `debugtools.ExtraAsyncDelayMS`.
3. Select the result and click **Create Widget**.
4. Use the saved control directly from the panel.

The saved control returns the next time you open the panel. Use its gear menu to change its label, execution target, range, shortcut, or saved default when those options apply.

See [Console](/DebugTools/tabs/console) for the complete workflow.

## Configure Project Features

Open **Project Settings -> Plugins -> Debug Tools** to configure:

- the project dashboard shown in the Project tab
- whether multiplayer controls are shown
- save-game override definitions and custom struct widgets
- project defaults for Debug Options
- custom Show Debug views

Settings intended for the whole project are written to project configuration. Personal saved controls and local overrides remain local to the user. See [User Data and Persistence](/DebugTools/customization/user-data).

![Debug Tools settings filtered in Project Settings, showing the Panel and Save Game Override groups](assets/screenshots/project-settings.png)

[Back to home](/DebugTools/)
