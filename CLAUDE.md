# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```sh
npm run dev      # Dev server at localhost:4321
npm run build    # Build to ./dist/
npm run preview  # Preview production build locally
```

## Architecture

Single-page Astro 5 site advertising a rental unit. No routing — everything lives in `src/pages/index.astro`.

**Key files:**
- `src/pages/index.astro` — entire page: hero, stats bar, description sections, sidebar, gallery, CTA
- `src/layouts/MyLayout.astro` — HTML shell with Inter font, Tailwind, GoatCounter analytics, max-w-6xl container
- `src/components/Grid.astro` — photo gallery using Swiper (carousel) + GLightbox (lightbox); images imported directly and optimized via `astro:assets`
- `src/styles/main.css` — Tailwind directives + small global overrides (hero full-bleed breakout, gallery hover zoom)
- `public/application.pdf` — downloadable rental application

**Stack:** Astro 5, Tailwind CSS v3 (via `@astrojs/tailwind`), Swiper 11, GLightbox 3. No framework components — all `.astro`.

**Images:** Stored in `src/assets/` and processed by `astro:assets` at build time. To add a photo to the gallery, import it in `Grid.astro` and add an entry to the `photos` array.

**Hero breakout:** The `.hero` class uses negative margins (`calc(50% - 50vw)`) to break out of the container on desktop while staying contained on mobile.

## Listing Content Guidelines

This listing is optimized for **student renters** (UCSC) while maintaining an elevated feel to justify the price. Key principles:

**Audience & positioning**
- Target: 1–2 students sharing a flexible loft layout
- Emphasize: private freestanding unit (not a shared house) — this justifies the price
- Tone: practical and clear, not luxury/over-stylized; scannable bullets over dense paragraphs

**Layout description**
- The unit has two distinct areas: upstairs loft sleeping area + downstairs space (bedroom/office/living)
- Do not describe as a "2-bedroom" — emphasize flexibility instead
- Downstairs can fit a dedicated bed or fold-out for a convertible space

**Pricing**
- List price: $3,395/month. Do not show per-person pricing.
- Frame as all-in value: "no accounts to set up, no bills to split"

**Parking**
- Street parking on the block
- Permit-free spots on the intersecting street directly across from the unit
- Westside residential permit easy to obtain if needed

**Commute framing**
- UCSC: ~5–10 min drive, bike-friendly via Mission St
- Mission St cafés/groceries: walking distance
- Downtown Santa Cruz: ~1 mile

**Page section order** (current):
1. Hero → Stats bar → Intro paragraph
2. Ideal For → The Space → What's Included → Why It Works for Students → The Location (with parking block) → Apply
3. Sidebar: Contact card, Property Details, Amenities
4. Gallery → Bottom CTA

**CTA language**
- "Rare private unit — reach out to schedule a showing"
- "Typically rents quickly for July availability"
- Invite questions: "Reach out to schedule a showing or ask questions"
