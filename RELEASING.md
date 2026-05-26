# Publish a Mac build (manual, every release)

The public website and `latest.json` point at this **exact** URL:

`https://github.com/59-Projects/studio-pages/releases/latest/download/Studio-mac.dmg`

That URL only works after the **latest published** Release in **this repo** includes an asset literally named **`Studio-mac.dmg`**. The private [`59-Projects/studio`](https://github.com/59-Projects/studio) app repo cannot serve anonymous downloads.

Do the following **every time** you ship a new Studio Mac build (from your machine or Cursor).

## 1. Build the installer (in `studio`)

```bash
cd /path/to/studio
yarn install
yarn dist
```

Confirm **`dist/Studio-mac.dmg`** exists (set by `build.mac.artifactName` in that repo).

## 2. Put the DMG on a public Release (this repo)

### Option A: GitHub web UI

1. Open [**59-Projects/studio-pages → Releases**](https://github.com/59-Projects/studio-pages/releases).
2. **Draft a new release**.
3. **Choose a tag**: e.g. **`v0.2.1`** (new tag, publish on create). Use the same semver as `package.json` in `studio` (with a leading `v` is fine).
4. **Attach** the file from your machine: **`Studio-mac.dmg`**. The download name in the UI must stay **`Studio-mac.dmg`** so the stable link above keeps working.
5. **Publish release**.

If you are **replacing** an existing tag’s DMG, edit that release, remove the old **`Studio-mac.dmg`**, attach the new one, then save.

### Option B: GitHub CLI (same result)

With [`gh`](https://cli.github.com/) logged in:

```bash
gh release create v0.2.1 \
  --repo 59-Projects/studio-pages \
  --title "Studio v0.2.1" \
  /absolute/path/to/studio/dist/Studio-mac.dmg
```

Use a new tag per version so **latest** moves forward. The asset name comes from the filename: keep it **`Studio-mac.dmg`**.

## 3. Update `latest.json` in this repo

Edit [`latest.json`](./latest.json):

- Set **`version`** to the shipped semver (must match `app.getVersion()` in the built app, usually the same as **`package.json`** in `studio`).
- Keep **`url`** as **`https://github.com/59-Projects/studio-pages/releases/latest/download/Studio-mac.dmg`** unless you change hosting.

Commit and push **`main`** so the site and hosted JSON update (Pages will rebuild from the push).

## Quick verify

- Open the [**download URL**](https://github.com/59-Projects/studio-pages/releases/latest/download/Studio-mac.dmg) in a private window. It should **download** `Studio-mac.dmg`, not show a 404 or only the Releases index.
- Open **`https://studio.59projects.com/latest.json`** and confirm **`version`**.

## Optional

- You can still create Releases on **private** `studio` for internal notes. They do **not** replace step 2 for public downloads.
