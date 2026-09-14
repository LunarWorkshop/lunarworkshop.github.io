# Debug Tools Screenshot Checklist

Screenshots were captured from Unreal Engine 5.8 at native editor scaling and cropped to the relevant feature.

## Captured

- Complete Debug Tools panel with **Project** followed by all five built-in tabs (`complete-panel.png`).
- **Project Settings -> Plugins -> Debug Tools** with the visible setting groups (`project-settings.png`).
- Console Widget Builder search results and representative saved controls (`console-builder.png`).
- Debug Command Builder with an Actor class and Blueprint-callable function selected (`debug-command-builder.png`).
- UMG Designer showing the configured `DebugToolsRootWidget` dashboard (`root-widget-designer.png`).
- UMG palette filtered to the five Debug Tools widget types (`umg-palette-widgets.png`).
- Finished showcase panel with the project-authored **Project** tab selected (`showcase-panel.png`).
- Representative saved Actor Debug Commands (`saved-debug-commands.png`).
- Project-authored dashboard in the **Project** tab (`project-dashboard.png`).

The following supporting states were also captured:

- A saved Float Debug Option and the Debug Option Builder (`debug-options.png`).
- The actionable Save Game empty state shown when no override definition exists (`save-game-empty-state.png`).
- The disabled Show Debug picker before PIE begins (`show-debug-editor-state.png`).

## Still Needed

These require a documentation sample project or runtime setup that was not present in the running Lyra editor. Do not manufacture these states by changing an unrelated project's configuration.

1. Console search results showing a command, exec command, Bool CVar, Int32 CVar, and Float CVar together.
2. Populated Debug Options tab demonstrating all six value types.
3. Save Game tab with an example SaveGame object expanded and **Override save** enabled.
4. Show Debug dropdown during PIE with built-in and Gameplay Ability System views.
5. Blueprint graph reading and listening to a Debug Option.
6. Blueprint save-loading branch that tries **Load Save Game Override** before the normal load.
7. Blueprint graph with representative asset, level, and save-game Debug Delay nodes.
8. **Struct Widget Overrides** setting alongside its matching Editor Utility Widget Blueprint.
9. Multiplayer host picker showing a listen server and multiple clients.
10. Gameplay Ability System view with **Attributes**, **Effects**, and **Abilities** categories.
11. Saved gameplay Debug Command with a typed parameter expanded.

Use native editor scaling, crop to the relevant UI, avoid project-confidential names or data, and write descriptive alt text when replacing each remaining comment with its final image reference.
