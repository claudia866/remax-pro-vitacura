# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-file landing page for **RE/MAX PRO Vitacura** — a luxury real estate agency in Vitacura, Santiago, Chile. The page is conversion-focused for Meta Ads and Google Ads campaigns.

## Architecture

The entire site lives in `index.html` — one self-contained file with inline CSS and JavaScript. No build tool, no framework, no dependencies to install. Open the file directly in a browser.

**External CDN dependencies (loaded at runtime):**
- GSAP 3.12.5 + ScrollTrigger — scroll-based animations
- Three.js r128 — hero 3D particle field
- Lenis 1.0.42 — smooth scroll
- Google Fonts — Cormorant Garamond + DM Sans + Bebas Neue

## Running the Site

```
# Open directly in browser (no server needed)
start index.html

# Or serve locally if needed (any static server works)
npx serve .
python -m http.server 8080
```

## Key Data to Edit

All property listings and testimonials are defined as plain JS arrays near the top of the `<script>` block:

- `PROPERTIES` — 8 property objects with: `name`, `location`, `type` (casa/depto/oficina), `op` (venta/arriendo), `uf`, `m2`, `hab`, `banos`, `badge` (new/op/exc/null), `img` (Unsplash URL)
- `TESTIMONIALS` — 6 testimonial objects

## Client Info

- **Brand:** RE/MAX PRO Vitacura
- **Phone/WhatsApp:** +56994394228
- **Email:** oficina@remax-pro.cl
- **Address:** Francisco de Aguirre 3620, Vitacura
- **Instagram:** @gestiones_inmobiliarias_pro
- **Colors:** Red `#DC1A2C`, Navy `#003DA5`, Gold `#C9A96E`, Black `#0A0A0A`

## Conversion Tracking

- **Meta Pixel:** Placeholder comment in `<head>` — replace with actual pixel ID
- **Lead event:** Fires `fbq('track', 'Lead')` on form submit
- **WhatsApp CTAs:** All use UTM params `?utm_source=landing&utm_medium=<location>&utm_campaign=<action>`

## Design System

Two skills are installed in `.claude/skills/`:
- `frontend-design` — general frontend design principles
- `ui-ux-pro-max` — comprehensive UI/UX rules (50+ styles, palettes, font pairings)

Use `/frontend-design` or `/ui-ux-pro-max` when making visual changes to stay consistent with the established aesthetic: dark luxury, glassmorphism cards, Cormorant Garamond headlines, gold accents.
