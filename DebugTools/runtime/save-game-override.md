---
title: Runtime Save Game Override
---

# Runtime Save Game Override

The Save Game Override runtime API lets normal loading code ask whether Debug Tools has a prepared test save enabled. Debug Tools never intercepts a project's load path automatically.

First configure and prepare an override using the [Save Game tab](/DebugTools/tabs/save-game).

---

## Blueprint Integration

At the start of the normal save-loading flow:

1. Call **Load Save Game Override**.
2. If it succeeds, cast and use the returned Save Game object.
3. If it fails, continue through the project's normal save-loading path.

**Is Save Game Override Enabled** can be used when the game needs to change UI or logging before loading. **Get Save Game Override Metadata** is also available to systems that pass or inspect the public override state in C++.

<!-- Screenshot needed: Blueprint branch using Load Save Game Override before the project's normal Load Game From Slot path. -->

## C++ Example

```cpp
#include "SaveGameOverride/DebugToolsSaveGameOverrideBlueprintLibrary.h"

USaveGame* DebugSave = nullptr;
if (UDebugToolsSaveGameOverrideBlueprintLibrary::LoadSaveGameOverride(
        WorldContextObject,
        DebugSave))
{
    // Cast DebugSave to the project's SaveGame type and use it.
}
else
{
    // Continue with the project's normal save-loading path.
}
```

The public `DebugToolsSaveGameOverride::LoadSaveGameOverride` helper provides the same result when no world-context object is available.

## When Loading Fails

The call returns false when:

- no configured override is enabled
- the prepared slot does not exist or cannot be read
- the saved object is not the configured SaveGame class
- the configuration is invalid

Treat false as “no debug override available” and use the normal loading path.

## Shipping Builds

Save Game Override is disabled in Shipping builds. The enabled check is false and loading returns false, so the same fallback path continues to the player's normal save.

[Back to Runtime and Blueprint](/DebugTools/runtime/) · [Back to home](/DebugTools/)
