# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Serve locally with live reload
bundle exec jekyll serve

# Build for production
bundle exec jekyll build

# Format Liquid/HTML files
npx prettier --write "**/*.liquid" "**/*.html"
```

## Architecture

This is a personal academic website built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme, hosted on GitHub Pages.

**Branch structure**: All edits are made on the `source` branch. GitHub Pages auto-deploys from there; do not edit the `main`/`gh-pages` branch directly.

### Content files (edit these for site updates)

| Location | Purpose |
|---|---|
| `_pages/about.md` | Homepage — bio text and profile config |
| `_bibliography/papers.bib` | Publications (BibTeX) |
| `_data/socials.yml` | Social media links |
| `_data/coauthors.yml` | Co-author links in publications |
| `assets/json/resume.json` | CV data (JSON Resume format) |
| `_config.yml` | Site-wide settings, plugins, scholar config |
| `_news/` | News items shown on about page |
| `_posts/` | Blog posts (filename: `YYYY-MM-DD-title.md`) |
| `_projects/` | Project cards |

### Theming / styling

- `_sass/_themes.scss` — theme color (`--global-theme-color`)
- `_sass/_variables.scss` — color palette options
- `_sass/_base.scss` — fonts, spacing

### Publications system

`jekyll-scholar` renders `_bibliography/papers.bib`. The author name matching uses `scholar.last_name` / `scholar.first_name` in `_config.yml` (currently `Caldwell`, `[David, J.]`). Custom BibTeX fields like `pdf`, `code`, `arxiv`, `abstract`, `bibtex_show`, and `selected` control which buttons appear on each publication entry.

### Removing/disabling pages

Prefer adding unwanted files to the `exclude` list in `_config.yml` rather than deleting them, to avoid future merge conflicts when pulling upstream al-folio updates.

### Formatting

`prettier` with `@shopify/prettier-plugin-liquid` is configured for `.liquid` and `.html` files (see `package.json`).
