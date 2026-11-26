# Agent guide for jadegourd-web

This repo is Jade Gourd's public website: the home page, Support and the Privacy Policy. It is cloned as `web/`
inside the medicine-tracker workspace; the workspace's `AGENTS.md` covers work that spans repos.

## What's here

- Plain HTML and CSS, with no build step and no scripts:
  - `index.html`: the home page.
  - `support/` and `privacy/`: an `index.html` each.
  - `site.css`: every page's style, in the app's Mountains colours, light and dark.
  - `images/`: the icon and the home page's pictures, made from the app's App Store screenshots.
- Store screenshots and their sources live in the workspace (`docs/release/screenshots/`). This repo keeps only the
  files the pages serve.

## Publishing

- GitHub Pages builds the site from the root of `main` and serves it at <https://blitzdex27.github.io/jadegourd-web/>.
  A push to `main` is live within a few minutes.
- Pages runs Jekyll, which publishes a Markdown file as a page. `_config.yml` keeps `AGENTS.md`, `CLAUDE.md` and
  `README.md` off the site; list any other file that isn't part of the site there too.
- Don't move or rename the three pages. The iOS app links to Support and the Privacy Policy, and the App Store
  listing points at all three (the workspace's `docs/release/listing.md`).
- Links between pages stay relative (`../privacy/`), because the site lives under `/jadegourd-web/`.

## Branches

- `main` is the live site. Do work on your own branch, in a worktree
  (`git worktree add .claude/worktrees/<task> -b claude/<task> origin/main` for Claude Code,
  `.codex/worktrees/<task>` for Codex), and merge into `main` only when Dexter asks: merging publishes.
- To preview a worktree, run `python3 -m http.server 8000` in it and open <http://localhost:8000/>.

## Content rules

- What the site says about the app (price, availability, features) must match the Release build and its App Store
  listing. Jade Gourd Plus comes with 1.1: until 1.1 is released, only the privacy policy mentions it (buying it, from
  version 1.1). The home page and Support add Plus at release.
- No medical claims: the app records what people enter and never suggests, calculates or checks doses.
- The privacy policy describes what the app actually does with data. Change it only with the app, and give it a
  new effective date.
- Every page's footer keeps the developer line, links to the other pages, and the copyright and Apple trademark line.
