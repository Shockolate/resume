# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A [JSON Resume](https://jsonresume.org/) project. The source of truth is `resume.json`, which follows the JSON Resume schema. `certificates.json` holds supplemental data not in the main schema. The rendered output is `docs/index.html`, served via GitHub Pages at shockolate.github.io/resume/.

## Commands

```bash
npm test          # Validates resume.json against the JSON Resume schema
npm run build     # Renders resume.json → docs/index.html using jsonresume-theme-tech
npm run build-and-view  # validate → build → open in browser
```

## How it works

- `resumed` is the CLI that handles both validation and rendering.
- The theme (`jsonresume-theme-tech`) controls all HTML/CSS output. To change layout or styling, the theme package itself would need to be forked/replaced — there are no local template files.
- GitHub Pages serves `docs/index.html` directly from the `main` branch. Committing a rebuilt `docs/index.html` is how you publish changes.
- PDF export is browser print-to-PDF from the hosted page; the theme is already print-optimized for two pages.
