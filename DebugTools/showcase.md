---
title: Showcase
---

# Showcase: A Gameplay Debug Dashboard

This walkthrough combines the built-in panel with a small project-specific dashboard. The result gives designers one place to reproduce slow loads, tune gameplay, invoke test actions, prepare progression states, and inspect server/client behavior.

<!-- Screenshot needed: Finished Debug Tools panel with the project-authored Project tab selected. -->

---

## Tune Values Through Debug Options

A Debug Option is like a console variable that you can create right in the editor, no C++ required. You can tune their value live during Play In Editor with a slider for instant testing.

Create controls in the [Debug Options tab](/DebugTools/tabs/debug-options). Designers can save personal defaults without affecting the team, or define a project default for everyone.

Gameplay code reads the same values through the [runtime Debug Option nodes](/DebugTools/runtime/debug-options) and can react immediately when they change.

## Console Variables Are Now Widgets

No more forgetting the name of that console variable. No more repetitive stress injury typing them into the console. Turn "Recompile shaders" or "Stat fps" into a button that you can just click. Add `r.Lumen.Visualize` and `r.ShaderDevelopmentMode` or any other cvar to a panel to turn them on and off easily.

## Instant Cheats and Debug Commands

Turn any Blueprint or C++ function in your game into a button that you can run at a click. Give yourself health and gold, kill all enemies, whatever you want, it's all in instant reach.

Use the [Debug Commands tab](/DebugTools/tabs/debug-commands) to select the Actor class and save those functions as buttons. Choose **Singleton** when the map should contain exactly one encounter controller, or **First available** when any matching Actor is acceptable.

You can also assign PIE shortcut keys to the most frequent commands. Conflict warnings help you avoid keys already used by another Debug Tools command or Enhanced Input.

<!-- Screenshot needed: Saved Debug Commands for a representative gameplay encounter, including one command with typed parameters. -->

## Make Your Team A Cheats/Debug Panel

Create a `DebugToolsRootWidget` Editor Utility Widget Blueprint and place the most important project controls in it. The [Debug Tools UMG widgets](/DebugTools/customization/dashboard-widgets) provide the same command, CVar, Debug Command, Debug Option, and struct controls in a fixed project-authored layout inside the **Project** tab.

## Loading Delay Controls

Debug Tools makes it easy to simulate long loading times for players. Use [Debug Delay nodes](/DebugTools/runtime/debug-delay) at asynchronous loading points in the project. Then use the `debugtools.ExtraAsyncDelayMS` CVar control to add a fake delay to your loads. Raising the saved value now delays those calls so loading screens, cancellation, and repeated navigation can be tested on demand.

## Load A Fake Save Game

With a few clicks, create a fake save game for your game and then load it, so you can test your game at any point without having to play through it all.

Configure the project's SaveGame class and a separate Debug Tools slot. In the [Save Game tab](/DebugTools/tabs/save-game), enable **Override save** and edit inventory, progression, or checkpoint values.

At startup, the project tries [Load Save Game Override](/DebugTools/runtime/save-game-override) before its normal load. Test data is now reproducible without overwriting the player's ordinary save.

For complex project structs, add a [custom struct widget](/DebugTools/customization/save-game-struct-widgets) with presets such as “Start of Chapter” or “All Abilities Unlocked.”

## Inspect the Running Game

Start PIE and use [Show Debug](/DebugTools/tabs/show-debug) to select AI, Input, Net, Physics, or another available view. Selecting an Actor in the World Outliner points the active debugger at its PIE counterpart.

Projects using GAS can select **Gameplay Ability System**, then switch among Attributes, Effects, and Abilities.

## Target Server and Clients

Run multiplayer PIE and open a host picker. Send a command to **Server**, inspect one **Client**, or enable **Update all hosts** for a value that should change everywhere.

The same targeting model is shared by Console controls, Debug Commands, Debug Options, and custom Show Debug controls. See [Multiplayer Targeting](/DebugTools/multiplayer-targeting).

[Back to home](/DebugTools/)
