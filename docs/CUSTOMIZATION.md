# Customization & Publishing Guide

How to maintain and publish the OPSIDIAN GitHub profile README.

## Visual chrome rules

Keep the profile looking like a premium backend / cloud portfolio:

- Do **not** add colorful shields.io vendor badges (rainbow logos break the palette).
- Navigation and CTAs: plain Markdown text links.
- Focus areas and principles: monospace or plain text lines.
- Toolkit: Skill Icons gallery (`theme=dark` / `theme=light`) with sparse `<sub>` captions and SVG rules — not a documentation outline of `###` headings.
- Custom SVGs carry brand identity; chrome stays quiet and intentional.
- See [`DESIGN.md`](DESIGN.md) restraint rules before adding decoration.

## Publish the profile

GitHub shows the root `README.md` of the public repository named **exactly** `devcldkai229` (matching your username) at [https://github.com/devcldkai229](https://github.com/devcldkai229).

### Publish updates

```bash
git add README.md assets docs .github
git commit -m "chore: update OPSIDIAN profile"
git push origin main
```

Visit [https://github.com/devcldkai229](https://github.com/devcldkai229) and confirm dark/light themes.

## Editing content

| Goal | Where |
|------|--------|
| Intro / positioning copy | `README.md` top sections |
| Tech stack icons and labels | `README.md` - Engineering Toolkit |
| Explore CTA | `README.md` - Explore My Repositories |
| Colors / motifs | `docs/DESIGN.md` + SVG fills/strokes in `assets/` |
| Hero / diagrams | `assets/*.svg` |

Keep public copy in **English**. Do not invent jobs, awards, metrics, or production claims.

## Dark / light assets

Each major illustration has a pair:

- `*-dark.svg` - default / dark theme
- `*-light.svg` - light theme

README uses:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/...-dark.svg"/>
  <source media="(prefers-color-scheme: light)" srcset="./assets/...-light.svg"/>
  <img src="./assets/...-dark.svg" alt="..." width="100%"/>
</picture>
```

Keep viewBox proportions when editing so mobile scaling stays intact. Use ASCII-only text inside SVGs.

## Contribution snake (optional)

Workflow: [`.github/workflows/snake.yml`](../.github/workflows/snake.yml)

### One-time setup

1. Push the workflow to `main`.
2. On GitHub: **Actions** -> **Generate contribution snake** -> **Run workflow**.
3. Wait for success. SVGs are written to the **`output`** branch:
   - `github-contribution-grid-snake.svg` (light)
   - `github-contribution-grid-snake-dark.svg` (dark)
4. In `README.md`, find the commented snake block under **GitHub Activity** and **uncomment** it.
5. Commit and push the README change.

Until step 4, the snake image is intentionally omitted so the profile never shows a broken image.

### Schedule

- Runs daily at 00:00 UTC via `cron`
- Also supports manual `workflow_dispatch`
- Permissions: `contents: write` only (uses `GITHUB_TOKEN` - no extra secrets)

### Disable

Delete or disable the workflow in the Actions UI, and remove the snake block from `README.md` if it was enabled.

## Stats widgets

GitHub Activity uses [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) with OPSIDIAN palette colors.

If a widget fails to load (third-party outage), remove that `<img>` rather than leaving a broken image.

## Validation checklist

- [ ] SVG files open without XML errors
- [ ] Relative paths `./assets/...` resolve
- [ ] Repository and LinkedIn links work
- [ ] No featured/curated project list
- [ ] No rainbow vendor badge wall
- [ ] Snake not shown until first successful Action run
- [ ] Dark and light `<picture>` sources present
- [ ] No fabricated achievements or fake stats
