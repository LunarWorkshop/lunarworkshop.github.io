---
title: Building from Source
---

# Building from Source

The packaged plugin includes precompiled Win64 editor binaries and full source. A source-only package is also available for teams that build the plugin themselves.

**Blueprint projects** can use the precompiled package for their exact Unreal version without compiling the plugin.

**C++ projects** compile Debug Tools as part of a normal project build. Place it in `YourProject/Plugins/DebugTools`, enable it in the `.uproject`, regenerate project files if your workflow requires it, and build the project's Editor target.

Use the package matching the project's exact Unreal version. Debug Tools supports UE 4.27 and UE 5.0 through UE 5.8.

After the build, open the editor and choose **Window -> Debug Tools** in UE 4.27 or **Tools -> Debug Tools** in UE 5.0 and later.

[Back to home](/DebugTools/)
