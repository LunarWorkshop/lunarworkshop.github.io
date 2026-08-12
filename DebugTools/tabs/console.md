---
title: Console
---

# Console

The Console tab is the first built-in Debug Tools tab. It is designed to turn frequently used console commands and `int32` console variables into a personal, saved widget board.

---

## Console Widget Builder

The builder searches two kinds of console objects from the current editor session:

- enabled console commands
- enabled `int32` console variables

Search behavior:

- Case-insensitive
- Sloppy matching is allowed
- Spaces are ignored for matching, so a search such as `a b c` can match a target whose letters appear in order with any number of characters between them

The results list shows:

- the console object name
- the help text when available
- whether the result is a `Console Command` or an `Int32 CVar`

To create a saved widget:

1. Search for a console command or `int32` console variable
2. Select it from the results list
3. Click **Create Widget**

Saved widgets are stored in one mixed ordered list, so command widgets and `int32` console variable widgets can be interleaved freely.

---

## Console Command Widgets

If you create a widget from a console command, Debug Tools creates a saved command widget.

Command widgets support:

- clicking the main button to run the command
- dragging by the left handle to reorder
- opening the gear menu for settings
- clicking the trash button to remove the widget

Duplicate saved widgets for the same command are not added.

### Command world selection

The gear menu for a command widget lets you choose where the command runs:

- `Editor`
- `PIE`

If a command widget is set to `PIE`:

- the button shows a subdued `[PIE]` prefix
- the button is disabled while PIE is not running
- the button re-enables automatically when PIE starts again

---

## Int32 Console Variable Widgets

If you create a widget from an `int32` console variable, Debug Tools creates a saved `int32` console variable widget.

These widgets support:

- dragging by the left handle to reorder
- opening the gear menu for settings
- clicking the trash button to remove the widget

The main control uses Unreal's numeric slider style:

- the console variable name appears on the left
- the numeric slider fills the remaining width on the right and keeps a minimum width
- you can drag left and right on the control
- you can also type a number directly into the value field
- changes update the live console variable immediately

If the underlying console variable is missing or is no longer an `int32` variable, the widget disables itself instead of being removed automatically.

---

## Int32 Widget Range Settings

The gear menu for an `int32` console variable widget lets you configure:

- `Min`
- `Max`

These values are saved with the widget.

If `Min > Max`, Debug Tools normalizes the range by swapping them before saving.

The slider write path clamps outgoing values into the saved range. The live console variable itself is not forcibly rewritten just because it currently sits outside the saved range.

### Default range on creation

When a new `int32` console variable widget is created:

- default range is `0` to `1000`
- if the live value is below `0`, range becomes `2 * value` to `0`
- if the live value is above `1000`, range becomes `0` to `2 * value`

---

## First-Run Default Widget

If Debug Tools does not find an existing user save file yet, it seeds the saved console widget list with:

- `debugtools.ExtraAsyncDelayMS`

This only happens on first run when there is no existing Debug Tools save file. Existing save files are left unchanged.

---

## Persistence

Saved console widgets are stored automatically. There is no Save button.

Debug Tools persists:

- widget type
- widget order
- command world policy
- `int32` widget min/max range

For `int32` widgets, the display name and help text are always read live from the current console object instead of being stored redundantly in saved data.

Your saved widget list is restored when you reopen the panel or restart the editor. Saved data lives in the project's `Saved/DebugTools/DebugToolsUserData.json` file.

See [User Data and Persistence](/DebugTools/customization/user-data) for more detail.

[? Back to tabs](/DebugTools/tabs)
