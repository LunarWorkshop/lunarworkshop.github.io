---
title: Custom Save Game Struct Widgets
---

# Custom Save Game Struct Widgets

The Save Game tab normally displays reflected properties through Unreal's standard details controls. A project can replace every occurrence of one exact struct type with a purpose-built Editor Utility Widget.

Use this for data that is easier to edit through buttons, presets, validation, or a domain-specific layout.

---

## Create and Register a Widget

1. Create an **Editor Utility Widget Blueprint** derived from `DebugToolsSaveGameOverrideWidget`.
2. Build the struct-specific editor in UMG.
3. Open **Project Settings -> Plugins -> Debug Tools**.
4. Add an entry under **Save Game Override -> Struct Widget Overrides**.
5. Set **Struct Type** to the exact struct and **Widget Class** to the new Blueprint.

Mappings use exact struct types. A mapping for a parent or similarly shaped struct does not replace another type.

<!-- Screenshot needed: Struct Widget Overrides setting beside its matching Editor Utility Widget Blueprint. -->

## Initialize the Editor

Implement **On Save Game Override Initialized**. The supplied context contains:

- **Property Path**, identifying the value in the SaveGame object
- **Value Handle**, used to read and write the exact struct
- **Enabled**, matching the current Override save state

Use **Get Save Game Override Struct** with the expected struct type to populate the widget. **Get Owning Save Game** is available when the custom editor needs related values from the containing SaveGame object.

## Write and Commit Changes

Use **Set Save Game Override Struct** to write a replacement value through the handle. Then call **Commit Save Game Override Changes** to validate and persist the owning SaveGame object.

The set node fails when the handle is invalid or the supplied struct type does not exactly match the registered value.

## Respond to Refreshes

Implement these optional events when the widget needs live refresh behavior:

- **On Save Game Override Value Changed**: the represented value changed outside the widget
- **On Save Game Override Enabled Changed**: the tab's Override save state changed

Disable editing when the override is disabled so the custom UI matches the surrounding Save Game tab.

## Reuse the Widget in a Dashboard

Add **Debug Tools Struct Override** to a custom root widget, select the same Struct Type, and use:

- **Set Struct Override Value**
- **Get Struct Override Value**
- **On Struct Override Value Changed**
- **Get Struct Override Event Value**

The presenter embeds the registered widget and owns a copy of the supplied value. It does not require a SaveGame object.

[Back to customization](/DebugTools/customization/) · [Back to Save Game](/DebugTools/tabs/save-game)
