# Savan Patel — Personal Portfolio

Personal portfolio site for Savan Patel, an AI/software engineer. A single-page, static site covering About, Experience, Projects (featuring Nexus OS), Skills, Education, and Contact.

## Stack

- [Astro](https://astro.build) 5 — static site generator, zero client-side JavaScript
- Hand-rolled plain CSS (`src/styles/global.css`) — no frameworks, dark mode via `prefers-color-scheme`
- No external APIs, no paid services, no trackers

## Run locally

```sh
npm install
npm run dev      # dev server at http://localhost:4321
npm run build    # static build to dist/
npm run preview  # preview the production build
```

## Structure

```
astro.config.mjs        Astro config
src/pages/index.astro   Single-page site (all sections + content)
src/styles/global.css   All styling
```
