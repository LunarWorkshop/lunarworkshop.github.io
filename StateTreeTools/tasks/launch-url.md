---
title: Launch URL
---

# Launch URL

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Platform
**Availability:** StateTree Tools **2.0+**

Calls `LaunchURL` â€” the same function as Unreal's built-in **Launch URL** Blueprint node. This opens the provided URL using the platform's default handler, such as a web browser for `https://` links.

Fire-and-forget; the task always succeeds immediately after calling it.

---

## Configuration

### URL
The URL to open.

This can be a normal web URL such as `https://example.com`, or any other URL scheme supported by the current platform and operating system.

---

## Notes

- The task does not validate that the URL is reachable.
- Success only means the launch request was sent to the platform.
- What happens next depends on the user's platform, permissions, and registered URL handlers.

---

[â† Back to System](/StateTreeTools/tasks/system) Â· [â† Back to home](/StateTreeTools/)
