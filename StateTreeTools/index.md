---
title: StateTree Tools
---

# StateTree Tools

A plugin for Unreal Engine 5 that extends the StateTree system with ready-made tasks, components, and utilities - so you can build AI and gameplay logic faster without writing custom C++.

> **Hey you!**
> Enjoying State Tree Tools? Unsure about whether you want to buy? I want to hear from you.
> Mail [support@lunarworkshop.com](mailto:support@lunarworkshop.com) with questions and suggestions.

---

## [Showcase](/StateTreeTools/showcase)

Examples of what you can build with StateTree Tools - patrol AI, perception-driven behaviour, ability-driven state machines, and more.

---

## [Getting Started](/StateTreeTools/getting-started)

Install the plugin, enable it in your project, and set up your first StateTree using StateTree Tools tasks.

---

## [Building from Source](/StateTreeTools/building-from-source)

Instructions for contributors building the plugin from the source repository, including the one-time environment setup required for UE 5.5 and earlier.

---

## [Changelist](/StateTreeTools/changelist)

User-visible functionality changes are tracked here so readers can quickly see what changed between documentation updates.

---

## Tasks

Tasks run when a state is entered or exited and can keep the state alive while they do work.

| Category | Description |
|----------|-------------|
| [Actor](/StateTreeTools/tasks/actor) | Find actors in the world |
| [Audio](/StateTreeTools/tasks/audio) | Play and stop sounds on actors |
| [Animation](/StateTreeTools/tasks/animation) | Trigger and control animation montages |
| [Debug](/StateTreeTools/tasks/debug) | Draw debug shapes; flush debug lines and strings |
| [Niagara](/StateTreeTools/tasks/niagara) | Spawn and manage Niagara particle systems |
| [Navigation](/StateTreeTools/tasks/navigation) | Find random reachable points for patrol and wandering |
| [Enhanced Input](/StateTreeTools/tasks/enhanced-input) | Add and remove Enhanced Input mapping contexts |
| [Input](/StateTreeTools/tasks/input) | Set player controller input modes |
| [UI](/StateTreeTools/tasks/ui) | Create widgets, call widget events, and listen to widget events |
| [Gameplay \| Actions](/StateTreeTools/tasks/actions) | Drive async Blueprint logic from a StateTree state |
| [Gameplay \| StateTree](/StateTreeTools/tasks/statetree) | Send events with typed payloads to StateTree components |
| [Utilities \| Events](/StateTreeTools/tasks/events) | Call Blueprint events and dispatchers on actors by name |
| [Utilities \| Properties](/StateTreeTools/tasks/properties) | Set actor and component properties by name |
| [Abilities](/StateTreeTools/tasks/abilities) | Activate GAS abilities and send gameplay events |
| [System](/StateTreeTools/tasks/system) | Quit the application |

---

## Property Functions

> **Requires UE 5.5 or later.** Property functions are not available in UE 5.4.

Property functions compute a value each time a binding is evaluated.

| Category | Description |
|----------|-------------|
| [Components](/StateTreeTools/property-functions/components) | Get root component and other component accessors |
| [Enhanced Input](/StateTreeTools/property-functions/enhanced-input) | Access Enhanced Input subsystems |
| [Game](/StateTreeTools/property-functions/game) | Access game-level objects such as player controllers |
| [UI](/StateTreeTools/property-functions/ui) | Access widget-specific values such as animations |
| [Math \| Float](/StateTreeTools/property-functions/math-float) | Arithmetic, comparisons, trigonometry, and general float math |
| [Math \| Vector](/StateTreeTools/property-functions/math-vector) | Vector arithmetic, measurement, and conversion |
| [Utilities](/StateTreeTools/property-functions/utilities) | String conversion and general value utilities |
| [Call Pure Function](/StateTreeTools/property-functions/call-pure-function) | Call a BlueprintPure function and expose its return value as a binding |
| [Gameplay Attributes](/StateTreeTools/property-functions/gameplay-attributes) | Read GAS float attributes from an actor's Ability System Component |

---

## Conditions

Conditions test a value and return true or false, used in transitions and state selection.

| Category | Description |
|----------|-------------|
| [Gameplay Tags](/StateTreeTools/conditions/gameplay-tags) | Check gameplay tag state on an actor's Ability System Component |

---

## Components

| Component | Description |
|-----------|-------------|
| [Perception Event Forwarder](/StateTreeTools/components/perception-event-forwarder) | Forwards AI perception events into the StateTree event system |
| [Primitive Event Forwarder](/StateTreeTools/components/primitive-event-forwarder) | Forwards primitive component events (overlaps, hits, physics, input) into the StateTree event system |
| [GAS Event Forwarder](/StateTreeTools/components/gas-event-forwarder) | Forwards GAS gameplay events and tag changes into the StateTree event system |