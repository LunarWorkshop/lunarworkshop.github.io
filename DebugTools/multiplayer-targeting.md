---
title: Multiplayer Targeting
---

# Multiplayer Targeting

Debug Tools can send Console controls, Debug Commands, and Debug Options to a specific PIE instance or to every available host. This makes one editor panel useful while testing standalone, listen-server, dedicated-server, and client behavior.

No external service is required. Hosts launched for the current project advertise themselves locally while the editor session is active.

---

## Host Names

The host picker uses role-based labels:

| Label | Target |
|-------|--------|
| Editor | The editor world |
| PIE | A standalone PIE world |
| Listen Server | The listen-server world or process |
| Server | A dedicated-server world or process |
| Client 1, Client 2, ... | PIE client worlds or processes |

Hosts launched in separate PIE processes appear after they register. Closed or expired processes disappear from the list.

<!-- Screenshot needed: Host picker showing Editor, Listen Server, and two Client entries during multiplayer PIE. -->

## All Hosts

Enable **Update all hosts** when a control should affect every compatible checked host. This is useful for overlays, shared tuning values, and commands that should produce the same state across server and clients.

For Console and Debug Command rows, the Editor/PIE policy still limits which worlds are eligible. A host that cannot run the configured operation is skipped.

## One Host

Disable **Update all hosts** to show a host picker. Choose the server or client that should receive the next command or value change.

If the selected host is no longer available, the control displays **No Host** or becomes unavailable until a valid host is selected. Remote Debug Option and CVar controls read the selected host's value so the panel reflects that process rather than the editor's local copy.

## Multi-Process PIE

Start PIE with separate server/client processes through Unreal's multiplayer play settings. Debug Tools discovers those processes automatically and routes supported operations to them.

The host list is scoped to the current local editor session. It is not an internet remote-console feature and does not discover other machines.

## Single-Player Projects

Enable **Project Settings -> Plugins -> Debug Tools -> Multiplayer -> Suppress Multiplayer Options** to:

- hide host-targeting controls
- use the local eligible world directly
- disable Debug Tools multiplayer process communication

Use this setting when a project never needs server/client selection.

[Back to home](/DebugTools/)
