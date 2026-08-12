---
title: Building from Source
---

# Building from Source

## Add the plugin to your project

Place the `DebugTools` plugin in your project's `Plugins` directory.

## Generate project files if needed

If your Unreal workflow requires generated project files, regenerate them after adding the plugin.

## Build the editor target

Build your editor target as usual. Debug Tools is an editor plugin with a runtime stub module and an editor module that contains the panel UI, persistence system, and root widget hosting logic.

## Launch the editor

After the build succeeds, start the editor and open **Tools -> Debug Tools** to verify the plugin loaded correctly.

[← Back to home](/DebugTools/)
