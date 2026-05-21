# Studio site (Jekyll + Tailwind CSS)

This repository is the **Jekyll source** for the public Studio marketing site at **`https://studio.59projects.com`**, deployed with GitHub Actions to GitHub Pages ([**59-Projects/studio-pages**](https://github.com/59-Projects/studio-pages)).

The Electron app, maintainer docs, and update-feed behavior are documented in the main Studio repo: [**59-Projects/studio**](https://github.com/59-Projects/studio) (`docs/RELEASES.md`).

Styling uses **Tailwind CSS** (utilities in `_layouts/` and compiled CSS in `assets/css/site.css`).

## Prerequisites

- **Ruby** 3.2 or newer (this repo includes **`.ruby-version`** set to 3.3.x for [rbenv](https://github.com/rbenv/rbenv), [mise](https://mise.jdx.dev/), or [asdf](https://asdf-vm.com/) so `bundle exec` matches CI)
- **Bundler** (`gem install bundler` if needed)
- **Node.js** 18 or newer and **Yarn** (Classic 1.x is fine; enable [Corepack](https://nodejs.org/api/corepack.html) if you use a modern Yarn release)

## Local preview

**One-time setup** (from the repository root):

```bash
bundle install
yarn install
```

**Recommended: single dev command** (builds CSS once, then runs Tailwind watch and Jekyll together):

```bash
yarn dev
```

This runs `yarn build:css`, then starts **Tailwind in watch mode** and **`bundle exec jekyll serve --livereload`** side by side. Open the URL Jekyll prints (usually `http://127.0.0.1:4000/`).

Stop both processes with **Ctrl+C** once.

If `bundle exec` fails with missing gems, run **`bundle install`** again. If `jekyll` is not found, confirm Ruby matches **`.ruby-version`** and your shell sees the same Ruby as the terminal where you run Yarn.

### Other flows

**CSS only, then Jekyll yourself**

```bash
yarn run build:css
yarn run jekyll:serve
```

**Two terminals** (same as `yarn dev`, but manual)

Terminal 1: `yarn run watch:css`  
Terminal 2: `yarn run jekyll:serve`

The HTML references `assets/css/site.css`, which is **generated** by the Tailwind CLI, not edited by hand.

With `url` and `baseurl` in `_config.yml` matching production, you do not need an extra `--baseurl` flag for normal preview.

If you ever need to mirror the fallback `*.github.io` host before DNS is live, you can temporarily set `baseurl` in `_config.yml` to match that host’s path prefix, then restore it for `studio.59projects.com`.

## Tailwind workflow

- **Source:** `src/tailwind.css` (`@tailwind` layers only.)
- **Config:** `tailwind.config.js` (scans `_layouts/`, `_includes/`, root `*.md`, and `_posts/` if you add them.)
- **Output:** `assets/css/site.css` (committed so a CSS build is not strictly required for every clone, but **run `yarn run build:css` after changing classes or Tailwind config** so the file stays in sync.)

Use Tailwind utility classes in `_layouts/default.html` (and any future includes). Markdown body copy is wrapped with the Typography plugin (`prose` / `prose-stone` in the default layout) so headings and links pick up sane defaults.

## Files

- `_config.yml` — site title, description, `url`, `baseurl`, Jekyll `exclude` for Node and Tailwind sources
- `Gemfile` — Jekyll 4 (CI uses the same `Gemfile.lock` as local preview)
- `package.json` — Tailwind, PostCSS, Typography plugin; scripts including **`yarn dev`**
- `yarn.lock` — lockfile for Yarn (commit this; CI uses `yarn install --frozen-lockfile`)
- `CNAME` — custom domain hint for the built site (`studio.59projects.com`)
- `latest.json` — semver manifest for in-app update checks; see [**Studio `docs/RELEASES.md`**](https://github.com/59-Projects/studio/blob/main/docs/RELEASES.md) in the app repository

## GitHub Pages

After this workflow exists on **`main`**, enable **Settings → Pages → Build and deployment → Source: GitHub Actions** and choose this workflow. For `studio.59projects.com`, set the **Custom domain** in Pages settings and add DNS at your host per GitHub’s instructions.
