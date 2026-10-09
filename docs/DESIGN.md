# OPSIDIAN Design System

Visual identity for the `devcldkai229` GitHub profile README.

## Theme: OPSIDIAN Cloud Architecture

A premium backend / cloud engineer portfolio language:

- Elegant, architectural, futuristic, technical
- Minimal but rich -- artwork carries identity
- Restrained cyberpunk atmosphere (never neon overload)
- Cloud blueprints and quiet terminal aesthetics

## Restraint rules (non-negotiable)

1. **One palette only** for chrome -- no vendor rainbow badges (no orange RabbitMQ, green Swagger, purple Axios, etc.).
2. **Artwork over badges** -- hero, architecture, explore, and footer do the visual work.
3. **Typography for identity** -- focus areas and principles as readable text or monospace lines, not shield spam.
4. **Tech icons: uniform or absent** -- Skill Icons rows only; concepts without icons as muted monospace labels.
5. **Quieter motion** -- packets + at most one soft accent per SVG; avoid busy float/pulse on every node.
6. **Whitespace as luxury** -- breathing room in compositions and README sections.
7. Every element must feel intentional. Prefer remove over decorate.

## Color tokens

| Token | Hex | Role |
|-------|-----|------|
| Primary background | `#080F1E` | Hero / panel fill |
| Secondary background | `#13243A` | Nodes, borders |
| Electric cyan | `#22D3EE` | Primary accent, live nodes |
| Azure blue | `#3B82F6` | Connectors, secondary accents |
| Soft indigo | `#818CF8` | Tertiary accents |
| Primary text | `#F8FAFC` | Headlines and body on dark |
| Muted text | `#94A3B8` | Labels, annotations |

Light-mode variants invert surfaces to slate/white/indigo washes while keeping cyan-azure-indigo accents.

## Typography (SVG)

- Brand / UI: system UI sans (`ui-sans-serif`, Segoe UI, system-ui)
- Technical labels: monospace (`ui-monospace`, Menlo, Consolas)
- No external web fonts (GitHub SVG isolation)
- ASCII-safe text in SVG files

## Motifs

- Perspective grids fading into depth
- Microservice / repo nodes with thin connectors
- Slow data packets along paths
- Sparse circuit traces and telemetry marks
- Soft cyan light accent (hero only, restrained)

## Motion

- Duration target: 5-9s loops
- Prefer path motion over large transforms
- Honor `prefers-reduced-motion: reduce` (hide `.packet`, disable CSS animations)
- Assets must remain complete when animation is disabled

## Section information architecture

1. Hero banner
2. Introduction and identity
3. Engineering focus
4. Engineering Toolkit
5. Explore My Repositories (gateway -- no curated project list)
6. GitHub Activity
7. Connect
8. Signature footer

## Asset map

| File | Purpose |
|------|---------|
| `assets/hero-dark.svg` / `hero-light.svg` | Primary brand banner |
| `assets/explore-repos-dark.svg` / `explore-repos-light.svg` | Repository mesh gateway |
| `assets/footer.svg` | Closing signature |

## Constraints

- GitHub Flavored Markdown + supported HTML only
- Repository-hosted SVGs for custom art
- No React/Vite/Tailwind/JS for README rendering
- No iframes, canvas, or unsupported CSS class systems
- Dark/light via `<picture>` + `prefers-color-scheme`
- No fabricated achievements, metrics, or project claims
