---
title: Changelist
---

# Changelist

This page tracks user-visible Debug Tools functionality.

## Version 1.0.0

### Editor Panel

- Dockable Debug Tools panel with a project-authored Project tab followed by Console, Debug Commands, Debug Options, Save Game, and Show Debug.
- Optional project-owned Editor Utility Widget content inside the Project tab.
- One-click reset for saved console variables and Debug Options.

### Console and Commands

- Saved controls for console commands, exec commands, and bool, int, and float console variables.
- Editor and PIE execution, editable parameters, keyboard shortcuts, multiplayer targeting, and project/local CVar defaults.
- Debug Commands that call static or Actor-instance Blueprint-callable functions, including latent functions and output values.

### Runtime Debugging

- Gameplay-tagged Debug Options with bool, float, int, string, name, and gameplay-tag values.
- Blueprint and C++ access to Debug Options and Save Game Override.
- Debug Delay variants of asset loading, primary-asset bundle changes, level streaming, and asynchronous save-game operations.

### Save Games and Views

- Editable save-game overrides with project-defined types and slots.
- Custom Editor Utility Widgets for exact struct types in save data.
- Built-in and project-defined Show Debug views with categories, controls, and World Outliner target selection.
- Optional Gameplay Ability System view for attributes, gameplay effects, and abilities.

### Multiplayer

- Per-host and All Hosts targeting for console controls, Debug Commands, and Debug Options.
- Automatic discovery of server, listen-server, and client processes launched for PIE.

[Back to home](/DebugTools/)
