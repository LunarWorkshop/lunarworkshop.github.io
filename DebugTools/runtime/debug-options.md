---
title: Runtime Debug Options
---

# Runtime Debug Options

Runtime Debug Options let gameplay code consume the values configured in the Debug Tools panel. Options are identified by gameplay tags and support Bool, Float, Int, String, Name, and Gameplay Tag values.

Configure shared defaults and saved controls as described in the [Debug Options tab guide](/DebugTools/tabs/debug-options).

---

## Blueprint Access

Search for **Debug Tools | Debug Options** in Blueprint. The function library provides:

- **Get Debug Bool**, **Float**, **Int**, **String**, **Name**, and **Gameplay Tag**
- matching **Set Debug...** nodes
- **Get Debug Option Type** and **Get Debug Option Name**
- type-specific **Get Debug Option Default...** nodes
- **Get Debug Options Subsystem**

The world-context versions find the correct Game Instance subsystem automatically. Use the type that matches the option's configured type. A mismatched getter returns that type's empty/default value.

<!-- Screenshot needed: Blueprint graph reading a Bool Debug Option and listening for its changes. -->

## React to Changes

Use **Listen for Debug Option Changed** when Blueprint logic must react to one option. Its **On Changed** output fires when that tag changes.

The Debug Options subsystem also exposes **On Any Debug Option Changed**, including the changed tag and value type, for systems that monitor more than one option.

## Saving and Resetting

The subsystem provides:

- **Save Debug Options**: persist the current runtime values
- **Load Debug Options**: load persisted values
- **Reload Debug Options**: discard current values and load again
- **Reset Debug Options to Defaults**: restore the effective project or local defaults

Local defaults take precedence over project defaults in editor and PIE sessions.

## C++ Example

Use the public Blueprint function library when a world context is available:

```cpp
#include "DebugOptions/DebugToolsDebugOptionsBlueprintLibrary.h"

const bool bDrawCombatRanges = UDebugOptionsBlueprintLibrary::GetDebugBool(
    WorldContextObject,
    DrawCombatRangesTag);

UDebugOptionsBlueprintLibrary::SetDebugFloat(
    WorldContextObject,
    MovementScaleTag,
    1.5f);
```

The Game Instance subsystem provides the same typed getters, setters, lifecycle operations, and change delegate when direct subsystem access is more convenient.

## Invalid Tags and Types

Use valid gameplay tags from the `DebugOptionsCategory` category. Invalid tags are ignored. Keep one stable value type per option tag; changing the configured type makes previously saved values of another type unusable for that accessor.

[Back to Runtime and Blueprint](/DebugTools/runtime/) · [Back to home](/DebugTools/)
