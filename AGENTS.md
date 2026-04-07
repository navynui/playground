# App Linking System

## Overview

Flat playground of standalone HTML canvas games. No build step, no dependencies, no server needed. Open any `.html` file directly in a browser.

## Navigation

- `index.html` is the hub with static `<a>` links to all apps
- Each child page has `<a id="home-link" href="index.html">Home</a>`
- Click anywhere on `index.html` (except links) to cycle background gradients
- To add a new app: create the `.html` file, add a Home link in it, and add a link in `index.html`'s `<div id="links">`

## Apps

| File | Title |
|------|-------|
| `index.html` | Hello World (hub) |
| `balls.html` | Ball Pit Simulator |
| `shoot.html` | Slingshot 3D (finished) |
| `marble.html` | Marble Machine 2D |
| `liquid.html` | Liquid Simulation |
| `mechanics.html` | Mechanics Simulation |

## Rules

- Each new app (`.html` file) MUST include a link back to home: `<a id="home-link" href="index.html">Home</a>`.
- Each new app MUST be registered in `index.html` within the `<div id="links">` section.

## Notes

- `marble.html` uses `localStorage` for persisting its own marble structure state — this is functional.
- No linting, testing, or typecheck commands exist.
