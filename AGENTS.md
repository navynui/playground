# App Linking System

## Overview

The app uses a simple file-based navigation system where HTML files register themselves in `localStorage` and `index.html` dynamically builds links from the registry.

## How It Works

### index.html (Hub)

- Reads `localStorage.getItem('htmlRegistry')` which is a JSON object mapping filenames to display titles
- Iterates over all entries and creates `<a>` links for each registered file (except itself)
- Located at the root: `/home/nui/dev/www/index.html`

### Child Pages (balls.html, shoot.html)

Each child page self-registers on load using an IIFE at the top of its `<script>` block:

```js
(function register() {
  const registry = JSON.parse(localStorage.getItem('htmlRegistry') || '{}');
  registry['filename.html'] = document.title;
  localStorage.setItem('htmlRegistry', JSON.stringify(registry));
})();
```

Each child page also includes a Home link:

```html
<a id="home-link" href="index.html">Home</a>
```

## Registered Apps

| File | Title |
|------|-------|
| `index.html` | Hello World (hub, not self-registered) |
| `balls.html` | Ball Pit Simulator |
| `shoot.html` | Slingshot 3D |

## File Structure

```
/home/nui/dev/www/
├── index.html          # Hub page with dynamic links
├── balls.html          # Ball pit simulator
└── shoot.html          # 3D slingshot game
```

## Adding a New App

1. Create a new `.html` file in `/home/nui/dev/www/`
2. Add the registration IIFE at the top of the `<script>` block:
   ```js
   (function register() {
     const registry = JSON.parse(localStorage.getItem('htmlRegistry') || '{}');
     registry['yourfile.html'] = document.title;
     localStorage.setItem('htmlRegistry', JSON.stringify(registry));
   })();
   ```
3. Add a Home link in the HTML:
   ```html
   <a id="home-link" href="index.html">Home</a>
   ```
4. The app will automatically appear as a link on `index.html`
