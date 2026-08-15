# AGENTS.md

## Overview

dashboard-template is a fork of **TailAdmin React (free)** v1.3.0 -- a React 18 + Vite 4 + Tailwind CSS 3 admin dashboard template (ApexCharts, JSVectorMap, flatpickr, react-router-dom 6, TypeScript sources under `src/`). It is a **reference / starting point** for dashboard UI in other projects, not a standalone app of Prince's: no deployment, no backend, no env vars, MIT-licensed by TailAdmin (`LICENSE.md`). Remote: `git@github-personal:MVPrince10/dashboard-template.git`.

## Commands

```bash
npm install        # project-local node_modules only; never npm install -g
npm run dev        # vite dev server
npm run build      # vite build -> dist/
npm run preview    # serve the build
```

No tests, no lint script. Formatting: Prettier with `prettier-plugin-tailwindcss` (`.prettierrc`: single quotes).

## Architecture

- `src/main.tsx` -> `src/App.tsx` (router) -> `src/layout/DefaultLayout.tsx` (Sidebar + Header) -> `src/pages/*` (`Dashboard/ECommerce.tsx`, `Calendar`, `Chart`, `Form/`, `Tables`, `Profile`, `Settings`, `UiElements/`, `Authentication/`).
- Reusable pieces in `src/components/*` (Charts, Tables, Forms, Sidebar, Header, Dropdowns, Maps, ...); styling in `src/css` + `tailwind.config.cjs`; static assets in `public/` and `src/images`.
- Config: `vite.config.js` (react plugin only), `postcss.config.cjs`, `tsconfig.json`.

## Conventions

- **Do not build product features here.** Copy components/patterns *out* into the target project (lmno, BetBuffer, writing, ...); keep this repo close to upstream so it stays a clean reference. Upstream history (TailAdmin merges) is intact in `git log`.
- Local working tree has a one-line `package-lock.json` diff; not meaningful -- don't churn lockfiles or bump deps here without a reason.
- `node_modules/` and `dist/` are gitignored; there is nothing secret in this repo.
- Remote is the `github-personal` SSH alias (`MVPrince10`); do not re-point origin at `git@github.com:`.
