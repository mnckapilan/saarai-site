# CLAUDE.md

This file provides guidance to Claude Code when working with code in this repository.

## Commands

Use the Node 24 binary directly (nvm shell integration doesn't work in this environment):

```bash
# Dev server (runs on http://localhost:4321)
~/.nvm/versions/node/v24.14.1/bin/npm run dev

# Production build (outputs to dist/)
~/.nvm/versions/node/v24.14.1/bin/npm run build

# Preview production build locally
~/.nvm/versions/node/v24.14.1/bin/npm run preview
```

## Architecture

A static marketing/landing site for [saarai](https://github.com/mnckapilan/saarai) built with [Astro](https://astro.build). No JS framework — pages are `.astro` components that compile to plain HTML. Styles are plain CSS using custom properties, co-located in `<style>` blocks within each `.astro` file.

```
src/
├── layouts/
│   └── Layout.astro   ← shared HTML shell, global CSS tokens, Google Fonts
└── pages/
    └── index.astro    ← landing page (hero, features, how it works, CTA, footer)
```

## Design tokens

All design tokens (colours, fonts, radii) are defined as CSS custom properties in the `<style is:global>` block in `src/layouts/Layout.astro`. Edit there to change the theme.

## Deployment

Deployed to Cloudflare Pages. The build command is `npm run build` and the output directory is `dist/`. The branch is `master`.
