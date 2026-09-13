---
title: User Data and Persistence
---

# User Data and Persistence

Debug Tools separates project defaults from each developer's personal dashboard and test data.

---

## What the Project Shares

Settings saved with **Save (Project)** or configured under **Project Settings -> Plugins -> Debug Tools** belong to project configuration. These include:

- the Root Panel Widget Class
- Debug Option project defaults
- Save Game Override definitions and struct-widget mappings
- custom Show Debug views
- the multiplayer suppression setting
- console-variable values explicitly saved to a project config file

Commit these config changes when the team should share them. Root and custom struct Widget Blueprints are project assets and should also be committed.

## What Stays Local

Personal panel layout is saved automatically in:

`Saved/DebugTools/DebugToolsUserData.json`

It includes saved Console controls, Debug Commands, Debug Options, their order, labels, ranges, shortcuts, parameters, and execution choices.

Local CVar and Debug Option defaults are stored under the project's platform-specific `Saved/Config` directory. They override project defaults for that user without changing team configuration.

Do not commit the project's `Saved` directory.

## Save Game Override Data

Prepared Save Game Override objects and their enabled state use Unreal save slots under `Saved/SaveGames`. They are local test data and should not be committed.

Changing or clearing personal panel data does not remove project defaults. Likewise, clearing a local override reveals the project default rather than deleting it.

## Automatic Saving

There is no Save button for panel layout. Debug Tools writes personal changes automatically after edits. Project and local default actions report whether their configuration write succeeded.

If a project config file is under source control, Debug Tools asks the configured provider to make it writable before saving. A read-only Save Game Override file must be made writable before the tab can replace it.

[Back to customization](/DebugTools/customization/) · [Back to home](/DebugTools/)
