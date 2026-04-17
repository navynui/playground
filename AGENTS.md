# App Linking System

## Overview

Flat playground of standalone HTML canvas games. No build step, no dependencies, no server needed.

## Apps

| File | Title |
|------|-------|
| `index.html` | Hello World (hub) |
| `balls.html` | Ball Pit Simulator |
| `shoot.html` | Slingshot 3D |
| `marble.html` | Marble Machine 2D |
| `liquid.html` | Liquid Simulation |
| `mechanics.html` | Mechanics Simulation |
| `abstract.html` | Abstract Art Generator |

## Adding New Apps

- Each `.html` file MUST include: `<a id="home-link" href="index.html">Home</a>`
- Register in `index.html` within `<div id="links">`

## Notes

- `marble.html` uses `localStorage` for persisting state
- No linting, testing, or typecheck commands exist