---
title: Call Pure Function
---

# Call Pure Function

Property functions for calling `BlueprintPure` functions on actors or their components and exposing the return value as a bindable output. **Requires UE 5.5+.** Each variant covers a different output type; all share the same Setup configuration.

Every variant provides a custom details panel. Set **ActorClass** to populate a searchable dropdown of pure functions whose return type matches the variant. Set **ComponentName** if the function lives on a component rather than the actor directly.

If **ActorClass** and **ComponentName** are set, compile validation also checks that the selected component and pure function still exist on that actor class.

| Property Function | Description |
|-------------------|-------------|
| [Call Pure Function (Bool)](/StateTreeTools/property-functions/call-pure-function-bool) | Return value exposed as `bool` |
| [Call Pure Function (Actor)](/StateTreeTools/property-functions/call-pure-function-actor) | Return value exposed as `Actor` reference |
| [Call Pure Function (Byte)](/StateTreeTools/property-functions/call-pure-function-byte) | Return value exposed as `byte` |
| [Call Pure Function (Int)](/StateTreeTools/property-functions/call-pure-function-int) | Return value exposed as `int32` |
| [Call Pure Function (Int64)](/StateTreeTools/property-functions/call-pure-function-int64) | Return value exposed as `int64` |
| [Call Pure Function (Float)](/StateTreeTools/property-functions/call-pure-function-float) | Return value exposed as `float` |
| [Call Pure Function (Double)](/StateTreeTools/property-functions/call-pure-function-double) | Return value exposed as `double` |
| [Call Pure Function (Name)](/StateTreeTools/property-functions/call-pure-function-name) | Return value exposed as `FName` |
| [Call Pure Function (String)](/StateTreeTools/property-functions/call-pure-function-string) | Return value exposed as `FString` |
| [Call Pure Function (Text)](/StateTreeTools/property-functions/call-pure-function-text) | Return value exposed as `FText` |
| [Call Pure Function (Vector)](/StateTreeTools/property-functions/call-pure-function-vector) | Return value exposed as `FVector` |
| [Call Pure Function (Rotator)](/StateTreeTools/property-functions/call-pure-function-rotator) | Return value exposed as `FRotator` |
| [Call Pure Function (Transform)](/StateTreeTools/property-functions/call-pure-function-transform) | Return value exposed as `FTransform` |

[â† Back to home](/StateTreeTools/)
