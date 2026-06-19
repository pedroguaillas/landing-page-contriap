# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```sh
npm run dev      # dev server at localhost:4321
npm run build    # build to ./dist/
npm run preview  # preview production build
```

## Architecture

Astro 6 project (static site, no framework integrations configured yet).

- `src/pages/` — file-based routing; each `.astro` file is a route
- `src/layouts/Layout.astro` — base HTML shell with `<slot />` for page content
- `src/components/` — reusable `.astro` components
- `src/assets/` — static assets imported by components (SVGs, images)
- `public/` — assets served verbatim at root (favicons, etc.)

Pages compose: `index.astro` → `Layout.astro` wraps `Welcome.astro` via `<slot />`. New pages follow the same pattern.

`astro.config.mjs` is minimal — add integrations (React, Tailwind, etc.) here via `astro add`.
