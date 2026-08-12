---
title: User Data and Persistence
---

# User Data and Persistence

Debug Tools stores user-created panel data automatically in the project `Saved` folder.

Current examples include saved Console command buttons, and the same persistence model is intended to support future user-managed Debug Tools items such as saved toggles, presets, and override rows.

---

## Storage location

Debug Tools stores its user-facing panel data in:

`Saved/DebugTools/DebugToolsUserData.json`

This is project-local saved data, not a shipping runtime save system and not a `DefaultEditor.ini` config setting.

---

## What gets saved

The persistence system is built around stable container keys and managed item types.

That means data is saved according to logical feature ids such as the Console button list, instead of being inferred from widget names or widget hierarchy paths.

This design helps saved data survive:

- root widget layout changes
- panel reorganization
- moving implementation details inside the plugin
- future expansion of each saved item type

---

## Save behavior

There is no Save button.

Debug Tools writes data automatically after user edits, using a short debounce so multiple quick changes can collapse into a single write.

---

## Current example: Console buttons

Each saved Console button stores item data rather than just a plain string. That allows the plugin to grow the behavior of a saved button over time without replacing the persistence model.

For example, a Console button can own fields such as:

- command name
- display label
- parameters
- world execution policy
- pinned state

[← Back to customization](/DebugTools/customization)


