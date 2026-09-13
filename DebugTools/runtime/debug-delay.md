---
title: Debug Delay Nodes
---

# Debug Delay Nodes

Debug Delay nodes reproduce slow asynchronous operations without changing the project's production services. They behave like the corresponding Unreal operation but wait before starting it.

Use them to test loading indicators, cancellation, repeated input, transitions, timeouts, and UI that is otherwise difficult to observe on a fast development machine.

---

## Choose the Delay

Every node combines two values:

- the global `debugtools.ExtraAsyncDelayMS` console variable
- the node's **Add delay (ms)** input

The effective delay is the total of those values, clamped so it cannot become negative. Put `debugtools.ExtraAsyncDelayMS` on the [Console tab](/DebugTools/tabs/console) to change latency for every Debug Delay node while testing. Use **Add delay (ms)** for a delay specific to one call site.

## Soft Asset Loading

| Node | Result |
|------|--------|
| Async Load Asset (Debug Delay) | Loads one Soft Object Reference |
| Async Load Class Asset (Debug Delay) | Loads one Soft Class Reference |
| Async Load Assets (Debug Delay) | Loads a list of Soft Object References |

These nodes preserve the familiar typed pins of Unreal's load-asset nodes. A failed load completes with an empty result.

## Primary Assets and Bundles

- **Async Load Primary Asset (Debug Delay)**
- **Async Load Primary Asset Class (Debug Delay)**
- **Async Load Primary Asset List (Debug Delay)**
- **Async Load Primary Asset Class List (Debug Delay)**
- **Async Change Bundle State for Matching Primary Assets (Debug Delay)**
- **Async Change Bundle State for Primary Asset List (Debug Delay)**

The Completed output fires after the delay and the underlying Asset Manager request have finished, whether or not every requested asset was found.

## Level Streaming

- **Load Stream Level (by Name) (Debug Delay)**
- **Load Stream Level (by Object Reference) (Debug Delay)**
- **Unload Stream Level (by Name) (Debug Delay)**
- **Unload Stream Level (by Object Reference) (Debug Delay)**

The standard visibility and blocking options still apply. The added delay occurs before the underlying stream or unload request begins.

## Save Games

- **Async Save Game To Slot (Debug Delay)**
- **Async Load Game From Slot (Debug Delay)**

Completion includes the SaveGame object and success result supplied by the underlying operation.

<!-- Screenshot needed: Blueprint graph containing soft-asset, level-streaming, and save-game Debug Delay nodes beside the global delay Console control. -->

## Practical Testing Pattern

1. Replace the asynchronous operation under test with its Debug Delay variant.
2. Save `debugtools.ExtraAsyncDelayMS` as a Console control.
3. Test with zero delay to confirm normal behavior.
4. Increase the delay while PIE is running and exercise navigation, cancellation, repeated actions, and teardown.
5. Reset the CVar when latency testing is complete.

[Back to Runtime and Blueprint](/DebugTools/runtime/) · [Back to home](/DebugTools/)
