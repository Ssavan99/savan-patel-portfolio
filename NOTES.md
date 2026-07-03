# Build Notes — Savan Patel Portfolio Site

Autonomous build, no resume/auth issues to flag (resume was readable; `gh` was authenticated as Ssavan99).

## What was built
A single-page Astro static site (`src/pages/index.astro` + `src/styles/global.css`) covering About, Experience, Projects (including Nexus OS as a featured project), Skills, and Contact. Fully static, zero client-side JS shipped, $0 hosting cost, builds cleanly with `npm run build`.

**Stack choice:** Astro over plain HTML/CSS/JS or 11ty — gives component structure and a clean build pipeline while still shipping zero JS by default, which fit the "clean, confident, not flashy" brief better than hand-rolled HTML for a site this size.

## Model attribution
- **Planning, design direction, coding, and content writing:** all done by a single subagent dispatched on `model: fable` — it succeeded on the first attempt, so no fallback to opus/sonnet was needed.
- **Orchestration only** (resume read, GitHub repo scan, git init/commit, `gh repo create`/push, this file): done by the default top-level session model, per the task's split.

## Assumptions / placeholders
- No headshot or any images used anywhere — none existed, and the task said not to fake one.
- LinkedIn URL assumed to be `linkedin.com/in/ssavan971` from the resume's handle; GitHub assumed `github.com/Ssavan99`.
- Project links included only where a GitHub repo name was identifiable from the resume/GitHub scan; a few resume projects (RAG-Based AI Assistant, "Fortune Teller" stock predictor) are listed without a repo link rather than guessing one.
- Skills are grouped into Languages / Frameworks & ML / Cloud & Tools for scannability — same items from the resume, no additions.
- `astro.config.mjs` sets `site` to a GitHub Pages-style URL as a placeholder default; irrelevant since Pages was not enabled (see below).
- Nexus OS's project description was written from its real `README.md`/`docs/architecture.md` — described accurately as a personal workflow/config layer around a GBrain-backed memory engine (Postgres + pgvector, local Ollama embeddings, MCP access for multiple agents, read-only enforced for cloud surfaces), not oversold as a product.

## Personality thread
Chose **AI/engineering** (not gaming/space/sports — the resume is dominated by RAG, LLM, and ML project work, so this was the clear fit). It shows up in exactly one place: a subtle static SVG "knowledge graph" node-and-edge motif in the hero section background of `src/pages/index.astro` (`.hero-graph`), styled in a low-opacity muted tone via a `--node` CSS variable, marked `aria-hidden` and non-animated. Everything else — typography, section layout, copy — reads as a normal, clean professional site.

## Repo status
- Created and pushed: **yes** — https://github.com/Ssavan99/savan-patel-portfolio (public)
- GitHub Pages / any deployment: **not enabled**, per instructions — this is local/unpublished only; no live URL exists or was looked for.

## Things Savan might want to tweak himself
1. Add a real headshot/photo if he wants one — currently there are none anywhere on the site.
2. Verify the assumed LinkedIn/GitHub URLs are exactly right, and add direct links for the 2 projects that currently have no repo link.
3. Decide on and enable actual hosting (GitHub Pages, Vercel, Netlify) when ready — `astro.config.mjs`'s `site` value will need to match whatever domain he picks.
