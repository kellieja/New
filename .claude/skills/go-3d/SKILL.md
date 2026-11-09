---
name: go-3d
description: 3D menu. Picks the right skill for 3D on websites, from choosing the approach to building scenes, using helper components, or adding tilt and depth effects.
disable-model-invocation: true
argument-hint: "[what 3D you need]"
---

# 3D

Pick one skill from the table, load it with the Skill tool, and do the work. Say in one line which skill you used. If the request spans two rows, run them in order.

| If they want to... | Use |
|---|---|
| Decide how to add 3D to a site, or prep 3D files for the web | `3d-web-experience` |
| Build the 3D scene in React (setup, animation, clicks) | `react-three-fiber` |
| Controls, lighting, 3D text, labels, loaders | `drei` |
| Cards or sections that tilt toward the cursor | `3d-ui` |

Typical order for a full 3D section: `3d-web-experience`, then `react-three-fiber`, then `drei`.
Always add a still-image fallback and respect reduced-motion settings.
