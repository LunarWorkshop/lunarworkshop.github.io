---
title: Debug Tools
---

# Debug Tools

Debug Tools is an Unreal Engine plugin for building project-specific debug dashboards. It combines a dockable editor panel with reusable controls for console commands, runtime options, save-game overrides, multiplayer instances, and Unreal's Show Debug views.

> **Hey you!**
> Enjoying Debug Tools? Unsure whether it fits your project? I want to hear from you.
> Mail [support@lunarworkshop.com](mailto:support@lunarworkshop.com) with questions and suggestions.

---

## [Showcase](/DebugTools/showcase)

Build a practical gameplay-debugging dashboard and see how the built-in tools work together.

---

## [Getting Started](/DebugTools/getting-started)

Install the plugin, open the Debug Tools panel, and create your first saved control.

---

## [Building from Source](/DebugTools/building-from-source)

Add Debug Tools to a Blueprint or C++ project and build it with your normal Unreal workflow.

---

## [Changelist](/DebugTools/changelist)

See the user-visible features included in each Debug Tools release.

---

## Panel Tabs

| Tab | Description |
|-----|-------------|
| [Project](/DebugTools/tabs/project) | A project-authored dashboard built as an Editor Utility Widget Blueprint |
| [Console](/DebugTools/tabs/console) | Turn console commands, exec commands, and console variables into saved controls |
| [Debug Commands](/DebugTools/tabs/debug-commands) | Run Blueprint-callable functions without building temporary UI or console commands |
| [Debug Options](/DebugTools/tabs/debug-options) | Create gameplay-tagged values that designers can edit while testing |
| [Save Game](/DebugTools/tabs/save-game) | Prepare and enable alternate save-game data without replacing a normal save |
| [Show Debug](/DebugTools/tabs/show-debug) | Select Unreal Show Debug views, categories, controls, and target actors |

---

## Runtime and Blueprint

| Topic | Description |
|-------|-------------|
| [Debug Options](/DebugTools/runtime/debug-options) | Read, write, save, reset, and listen for runtime debug-option values |
| [Save Game Override](/DebugTools/runtime/save-game-override) | Let game loading code use an enabled debug save when one is available |
| [Debug Delay Nodes](/DebugTools/runtime/debug-delay) | Add controllable latency to asset, level, and save-game operations |

---

## Project Workflows

| Topic | Description |
|-------|-------------|
| [Multiplayer Targeting](/DebugTools/multiplayer-targeting) | Send controls to one PIE instance or every available host |
| [Gameplay Ability System](/DebugTools/gameplay-ability-system) | Use the GAS Show Debug view and follow actor/avatar ownership automatically |
| [Customization](/DebugTools/customization/) | Build a custom root panel, use Debug Tools UMG controls, and customize save structs |

[Back to Lunar Workshop](/)
