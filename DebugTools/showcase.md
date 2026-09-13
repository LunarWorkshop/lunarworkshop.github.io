---
title: Showcase
---

# Showcase: A Gameplay Debug Dashboard

This walkthrough combines the built-in panel with a small project-specific dashboard. The result gives designers one place to reproduce slow loads, tune gameplay, invoke test actions, prepare progression states, and inspect server/client behavior.

<!-- Screenshot needed: Finished Debug Tools panel with a project dashboard above populated built-in tabs. -->

---

## Simulate Slow Loading

In the **Console** tab, search for `debugtools.ExtraAsyncDelayMS` and create a saved CVar control. Give it a practical range such as 0-5000 milliseconds.

Use [Debug Delay nodes](/DebugTools/runtime/debug-delay) at asynchronous loading points in the project. Raising the saved value now delays those calls so loading screens, cancellation, and repeated navigation can be tested on demand.

## Add Repeatable Gameplay Actions

Suppose an encounter Actor exposes Blueprint-callable functions such as `Start Encounter`, `Defeat Current Wave`, and `Refill Players`.

Use the [Debug Commands tab](/DebugTools/tabs/debug-commands) to select the Actor class and save those functions as buttons. Choose **Singleton** when the map should contain exactly one encounter controller, or **First available** when any matching Actor is acceptable.

Assign PIE shortcuts to the most frequent commands. Conflict warnings help avoid keys already used by another Debug Tools command or Enhanced Input.

<!-- Screenshot needed: Saved Debug Commands for a representative gameplay encounter, including one command with typed parameters. -->

## Tune Values Through Debug Options

Create gameplay tags for options such as a combat overlay, damage multiplier, or encounter name. Add their project defaults under **Project Settings -> Plugins -> Debug Tools -> Debug Options**.

Create controls in the [Debug Options tab](/DebugTools/tabs/debug-options). Designers can tune them during PIE, save personal defaults without affecting the team, or deliberately save a project default for everyone.

Gameplay code reads the same values through the [runtime Debug Option nodes](/DebugTools/runtime/debug-options) and can react immediately when they change.

## Prepare a Progression State

Configure the project's SaveGame class and a separate Debug Tools slot. In the [Save Game tab](/DebugTools/tabs/save-game), enable **Override save** and edit inventory, progression, or checkpoint values.

At startup, the project tries [Load Save Game Override](/DebugTools/runtime/save-game-override) before its normal load. Test data is now reproducible without overwriting the player's ordinary save.

For complex project structs, add a [custom struct widget](/DebugTools/customization/save-game-struct-widgets) with presets such as “Start of Chapter” or “All Abilities Unlocked.”

## Inspect the Running Game

Start PIE and use [Show Debug](/DebugTools/tabs/show-debug) to select AI, Input, Net, Physics, or another available view. Selecting an Actor in the World Outliner points the active debugger at its PIE counterpart.

Projects using GAS can select **Gameplay Ability System**, then switch among Attributes, Effects, and Abilities.

## Target Server and Clients

Run multiplayer PIE and open a host picker. Send a command to **Server**, inspect one **Client**, or enable **Update all hosts** for a value that should change everywhere.

The same targeting model is shared by Console controls, Debug Commands, Debug Options, and custom Show Debug controls. See [Multiplayer Targeting](/DebugTools/multiplayer-targeting).

## Put Frequent Controls at the Top

Create a `DebugToolsRootWidget` Editor Utility Widget Blueprint and place the most important project controls in it. The [Debug Tools UMG widgets](/DebugTools/customization/dashboard-widgets) provide the same command, CVar, Debug Command, Debug Option, and struct controls in a fixed project-authored layout.

The complete built-in tabs remain underneath for ad hoc work.

[Back to home](/DebugTools/)
