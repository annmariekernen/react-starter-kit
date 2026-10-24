<div align="center">

# React Starter Kit

**A small, opinionated starting point for front-end projects.**<br />
React, TypeScript, Tailwind CSS and shadcn/ui on Radix, with design tokens and dark mode ready to go.

![React](https://img.shields.io/badge/React-19-149eca?logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-6-3178c6?logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4-06b6d4?logo=tailwindcss&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-8-646cff?logo=vite&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui-Radix-111?logo=shadcnui&logoColor=white)

</div>

---

## Why this exists

Every new project starts with the same hour of setup: picking a build tool, wiring up styles, choosing a component library, setting up tokens and dark mode. This kit does that once, so each new project can start at the interesting part.

It is deliberately **lightweight**. It includes only what nearly every project needs. Anything else gets added per project, when that project needs it.

## What's inside

| | Tool | What it does |
|---|---|---|
| ⚛️ | [React](https://react.dev) | Builds the UI out of reusable components |
| 🔷 | [TypeScript](https://www.typescriptlang.org) | Catches mistakes before the code runs |
| ⚡ | [Vite](https://vite.dev) | Runs the local dev server with instant updates, and builds for production |
| 🎨 | [Tailwind CSS](https://tailwindcss.com) | Styles elements with utility classes, driven by design tokens |
| 🧩 | [shadcn/ui](https://ui.shadcn.com) | Copy-in components you own and can restyle |
| ♿ | [Radix](https://www.radix-ui.com) | Handles accessibility, keyboard support and focus inside each component |
| ✨ | [Lucide](https://lucide.dev) | Icon set |

**Included components:** Button, Badge, Card, Dialog, Input, Label<br />
**Also set up:** light and dark mode (follows the system setting, with a toggle), the Geist font, the `@/` import shortcut, and linting with Oxlint

## Getting started

### Start a new project from this template

1. Click **Use this template → Create a new repository** at the top of this page.
2. Clone your new repository and install:

   ```bash
   git clone https://github.com/<your-username>/<your-new-repo>.git
   cd <your-new-repo>
   npm install
   ```

3. Start the dev server:

   ```bash
   npm run dev
   ```

   Open **http://localhost:5173**. Edits show up in the browser as soon as you save.

4. Rename the project in `package.json` (`"name"`) and `index.html` (`<title>`).

**Requires** [Node.js](https://nodejs.org) 20.19 or newer.

### Commands

| Command | What it does |
|---|---|
| `npm run dev` | Starts the local dev server |
| `npm run build` | Type-checks, then builds a production version into `dist/` |
| `npm run preview` | Serves the production build locally to check it |
| `npm run lint` | Checks the code for common mistakes |

## Project structure

```
src/
├── components/
│   └── ui/           ← shadcn components (yours to edit)
├── hooks/
│   └── use-theme.ts  ← light/dark mode toggle
├── lib/
│   └── utils.ts      ← cn() helper for combining classes
├── App.tsx           ← the demo page; replace with your app
├── index.css         ← design tokens and theme
└── main.tsx          ← entry point; mounts the app
components.json       ← shadcn settings (style, icons, paths)
vite.config.ts        ← build setup, Tailwind plugin, @/ shortcut
```

## Customizing

### Design tokens

All colors, the corner radius and the fonts live in **[`src/index.css`](src/index.css)**:

- `:root { … }` holds **light mode** values
- `.dark { … }` holds **dark mode** values
- `--radius` sets corner rounding across every component

Change a token once and every component that uses it updates. For example, set `--primary` to your brand color and every primary button follows. Colors use [OKLCH](https://oklch.com), a color format where equal steps in lightness look equal to the eye.

The demo page shows each token as a swatch, so you can see changes right away.

### Adding components

Browse the [shadcn/ui component list](https://ui.shadcn.com/docs/components), then add one by name:

```bash
npx shadcn@latest add tabs
```

The component's code is copied into `src/components/ui/`. From then on it's a regular file in your project, so you can change it however you like.

### Using a component

```tsx
import { Button } from '@/components/ui/button'

<Button variant="outline" size="sm">Save</Button>
```

## Principles

- **Own the code.** Components are copied in, not hidden in a package, so nothing is locked.
- **Tokens first.** Style through tokens rather than one-off values, so design and code stay in step.
- **Accessible by default.** Radix handles keyboard, focus and screen reader behavior.
- **Add when needed.** Routing, data fetching, forms and testing are left out on purpose. Add them per project.

---

<div align="center">
<sub>Built by Ann Marie Kernen</sub>
</div>
