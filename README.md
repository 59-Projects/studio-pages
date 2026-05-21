# Studio site (Jekyll + Tailwind CSS)

This repository is the **Jekyll source** for the public Studio marketing site at **`https://studio.59projects.com`**, deployed with GitHub Actions to GitHub Pages ([**59-Projects/studio-pages**](https://github.com/59-Projects/studio-pages)).

The Electron app, maintainer docs, and update-feed behavior are documented in the main Studio repo: [**59-Projects/studio**](https://github.com/59-Projects/studio) (`docs/RELEASES.md`).

Styling uses **Tailwind CSS** (utilities in `_layouts/` and compiled CSS in `assets/css/site.css`).

## Prerequisites

- **Ruby** 3.2 or newer (3.3 matches CI), with Bundler
- **Node.js** 18 or newer and npm (for Tailwind)

## Local preview

Clone this repo, then from the repository root:

```bash
bundle install
npm install
```

Build Tailwind **before** (or in parallel with) Jekyll. The HTML references `assets/css/site.css`, which is **generated** by npm, not edited by hand.

**Option A: one terminal (simplest)**  
Build CSS, then start Jekyll:

```bash
npm run build:css
bundle exec jekyll serve --livereload --host 127.0.0.1
```

Open the URL Jekyll prints (usually `http://127.0.0.1:4000/`).

**Option B: two terminals (edit CSS or layouts with fast feedback)**  

Terminal 1:

```bash
npm run watch:css
```

Terminal 2:

```bash
bundle exec jekyll serve --livereload --host 127.0.0.1
```

**Option C: single command**  
Runs Tailwind in watch mode and Jekyll together (requires both installs above):

```bash
npm run dev
```

With `url` and `baseurl` in `_config.yml` matching production, you do not need an extra `--baseurl` flag for normal preview.

If you ever need to mirror the fallback `*.github.io` host before DNS is live, you can temporarily set `baseurl` in `_config.yml` to match that host’s path prefix, then restore it for `studio.59projects.com`.

## Tailwind workflow

- **Source:** `src/tailwind.css` (`@tailwind` layers only.)
- **Config:** `tailwind.config.js` (scans `_layouts/`, `_includes/`, root `*.md`, and `_posts/` if you add them.)
- **Output:** `assets/css/site.css` (committed so a CSS build is not strictly required for every clone, but **run `npm run build:css` after changing classes or Tailwind config** so the file stays in sync.)

Use Tailwind utility classes in `_layouts/default.html` (and any future includes). Markdown body copy is wrapped with the Typography plugin (`prose` / `prose-stone` in the default layout) so headings and links pick up sane defaults.

## Files

- `_config.yml` — site title, description, `url`, `baseurl`, Jekyll `exclude` for Node and Tailwind sources
- `Gemfile` — Jekyll 4 (CI uses the same `Gemfile.lock` as local preview)
- `package.json` — Tailwind, PostCSS, Typography plugin; scripts for CSS build and `npm run dev`
- `CNAME` — custom domain hint for the built site (`studio.59projects.com`)
- `latest.json` — semver manifest for in-app update checks; see [**Studio `docs/RELEASES.md`**](https://github.com/59-Projects/studio/blob/main/docs/RELEASES.md) in the app repository

## GitHub Pages

After this workflow exists on **`main`**, enable **Settings → Pages → Build and deployment → Source: GitHub Actions** and choose this workflow. For `studio.59projects.com`, set the **Custom domain** in Pages settings and add DNS at your host per GitHub’s instructions.
