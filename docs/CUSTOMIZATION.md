# Customization & Publishing Guide

How to maintain and publish the OPSIDIAN GitHub profile README.

## Publish the profile

GitHub shows the root `README.md` of the public repository named **exactly** `devcldkai229` (matching your username) at [https://github.com/devcldkai229](https://github.com/devcldkai229).

### First publish

1. Review local files (`README.md`, `assets/`, `.github/workflows/`, `docs/`).
2. Commit on `main` (when you are ready):

   ```bash
   git add README.md assets docs .github
   git commit -m "feat: add OPSIDIAN GitHub profile README"
   git push -u origin main
   ```

3. Visit [https://github.com/devcldkai229](https://github.com/devcldkai229) and confirm the hero renders in dark and light themes.

Do not force-push or rewrite history unless you intentionally need to.

## Editing content

| Goal | Where |
|------|--------|
| Intro / positioning copy | `README.md` top sections |
| Tech stack icons & badges | `README.md` ? Engineering Toolkit |
| Architecture caption / focus chips | `README.md` ? How I Think About Systems |
| Explore CTA | `README.md` ? Explore My Repositories |
| Colors / motifs | `docs/DESIGN.md` + SVG fills/strokes in `assets/` |
| Hero / diagrams | `assets/*.svg` |

Keep public copy in **English**. Do not invent jobs, awards, metrics, or production claims.

## Dark / light assets

Each major illustration has a pair:

- `*-dark.svg` — default / dark theme
- `*-light.svg` — light theme

README uses:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/...-dark.svg"/>
  <source media="(prefers-color-scheme: light)" srcset="./assets/...-light.svg"/>
  <img src="./assets/...-dark.svg" alt="..." width="100%"/>
</picture>
```

Keep viewBox proportions when editing so mobile scaling stays intact.

## Contribution snake (optional)

Workflow: [`.github/workflows/snake.yml`](../.github/workflows/snake.yml)

### One-time setup

1. Push the workflow to `main` (publishing the profile is enough).
2. On GitHub: **Actions** ? **Generate contribution snake** ? **Run workflow**.
3. Wait for success. SVGs are written to the **`output`** branch:
   - `github-contribution-grid-snake.svg` (light)
   - `github-contribution-grid-snake-dark.svg` (dark)
4. In `README.md`, find the commented snake block under **GitHub Activity** and **uncomment** it (remove the surrounding `<!--` / `-->`).
5. Commit and push the README change.

Until step 4, the snake image is intentionally omitted so the profile never shows a broken image.

### Schedule

- Runs daily at 00:00 UTC via `cron`
- Also supports manual `workflow_dispatch`
- Permissions: `contents: write` only (uses `GITHUB_TOKEN` — no extra secrets)

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
- [ ] Snake not shown until first successful Action run
- [ ] Dark and light `<picture>` sources present
- [ ] No fabricated achievements or fake stats
