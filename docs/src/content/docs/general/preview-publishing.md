---
title: "Preview & publishing"
description: "How to preview the docs locally and publish to GitHub Pages."
---

# Preview & publishing

## Local preview

Requirements: Node.js 20+ and npm.

```sh
cd docs
npm install
npm run dev     # local preview with hot reload
npm run build   # static output in docs/dist/
npm run preview # serve the built output
```

## GitHub Pages (fork-safe)

`docs/astro.config.mjs` derives `site` and `base` at build time — nothing is
hardcoded:

- `GITHUB_REPOSITORY` (`owner/repo`, always set in Actions) →
  `site: https://owner.github.io/repo/`, `base: /repo/`.
- Optional overrides: `SITE_URL` and `SITE_BASE` environment variables.
- Locally (neither set): root-relative URLs, so `npm run dev` just works.

This keeps forks working without editing the config.

## No workflows in this repo

By maintainer request, **no GitHub Actions workflows are created or modified
here**. To publish `docs/dist/` to Pages later, a maintainer can add a standard
Astro Pages workflow (latest `actions/*` majors, `npm ci` + `npm run build` in
`docs/`, upload `docs/dist` to `actions/upload-pages-artifact`, deploy with
`actions/deploy-pages`) — but that file intentionally does not exist yet.
