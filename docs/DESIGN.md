# OPSIDIAN Design System

Visual identity for the `devcldkai229` GitHub profile README.

## Theme: OPSIDIAN Cloud Architecture

A premium dark-mode developer portfolio language combining:

- Futuristic infrastructure / engineering dashboard cues
- Subtle cyberpunk atmosphere (restrained, not neon overload)
- Cloud architecture blueprints and terminal aesthetics
- Glass-like translucent surfaces and refined gradients

## Color tokens

| Token | Hex | Role |
|-------|-----|------|
| Primary background | `#080F1E` | Hero / panel fill |
| Secondary background | `#13243A` | Nodes, borders, badges |
| Electric cyan | `#22D3EE` | Primary accent, CTAs, live nodes |
| Azure blue | `#3B82F6` | Connectors, secondary accents |
| Soft indigo | `#818CF8` | Tertiary accents, service variety |
| Primary text | `#F8FAFC` | Headlines and body on dark |
| Muted text | `#94A3B8` | Labels, annotations |

Light-mode variants invert surfaces to slate/white/indigo washes while keeping cyan–azure–indigo accents for brand continuity.

## Typography (SVG)

- Brand / UI: system UI sans (`ui-sans-serif`, Segoe UI, system-ui)
- Technical labels: monospace (`ui-monospace`, Menlo, Consolas)
- No external web fonts (GitHub SVG isolation)

## Motifs

- Perspective grids fading into depth
- Microservice / repo nodes with thin connectors
- Animated data packets along paths (slow, low-cost SMIL)
- Circuit traces and small telemetry indicators
- Soft cyan light sweeps (hero only)

## Motion

- Duration target: 4–9s loops
- Prefer opacity pulse and path motion over large transforms
- Honor `prefers-reduced-motion: reduce` inside SVG `<style>` blocks
- Assets must remain complete when animation is disabled

## Section information architecture

1. Hero banner  
2. Introduction & identity  
3. Engineering focus  
4. Engineering Toolkit  
5. How I Think About Systems  
6. Explore My Repositories (gateway — no curated project list)  
7. GitHub Activity  
8. Connect  
9. Signature footer  

## Asset map

| File | Purpose |
|------|---------|
| `assets/hero-dark.svg` / `hero-light.svg` | Primary brand banner |
| `assets/architecture-dark.svg` / `architecture-light.svg` | Conceptual system diagram |
| `assets/explore-repos-dark.svg` / `explore-repos-light.svg` | Repository mesh gateway |
| `assets/footer.svg` | Closing signature |

## Constraints

- GitHub Flavored Markdown + supported HTML only
- Repository-hosted SVGs for custom art
- No React/Vite/Tailwind/JS for README rendering
- No iframes, canvas, or unsupported CSS class systems
- Dark/light via `<picture>` + `prefers-color-scheme`
- No fabricated achievements, metrics, or project claims
