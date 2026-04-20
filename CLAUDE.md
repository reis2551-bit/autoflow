# CLAUDE.md — Autoflow Website

This file provides guidance to Claude Code when working with this project.

## Project Overview

Static marketing website for **Autoflow** — a media/automation company that sells WhatsApp, SMS, and call automation services to small businesses in Portugal. Content is in European Portuguese (PT-PT).

## Stack

- **Zero dependencies** — pure HTML/CSS/JS, no build step, no npm, no frameworks
- Single file: `index.html` — the complete website
- Open directly in a browser or deploy to any static host (Netlify, cPanel, Vercel, etc.)

## Pages / Sections (SPA, scroll-based)

All content is in a single `index.html`. Sections use IDs for anchor navigation:

| ID | Content |
|---|---|
| `#home` | Hero — headline, phone mockup, CTAs |
| `#exemplos` | Logos bar — client social proof + stats |
| `#solucoes` | Solutions — 6 service cards |
| `#como-funciona` | How it works — 4 steps |
| `#precos` | Pricing — 3 tiers |
| `#testemunhos` | Testimonials — 3 cards |
| `#faq` | FAQ accordion |
| `#contacto` | CTA section |

## Design System

CSS custom properties defined in `:root`:

```css
--bg:          #0A0A0A   /* main background */
--bg2:         #111111   /* alternate sections */
--bg3:         #171717   /* cards */
--bg4:         #1F1F1F   /* featured card */
--accent:      #FF6A00   /* primary orange — ALL CTAs, highlights */
--accent-h:    #FF7A1A   /* hover state */
--accent-dim:  rgba(255,106,0,0.12)  /* icon backgrounds */
--text:        #F2F2F2   /* primary text */
--text-muted:  #888888   /* secondary text */
--border:      #2A2A2A   /* card borders */
```

Fonts: **Space Grotesk** (headings) + **Inter** (body) — loaded from Google Fonts.

## Key Components

- **`.btn-primary`** — orange filled button (CTAs)
- **`.btn-outline`** — ghost button with border
- **`.sol-card`** — service card with hover lift + top accent line
- **`.price-card.featured`** — highlighted pricing tier
- **`.fade-in`** — scroll-triggered animation (via IntersectionObserver)
- **`.phone`** — CSS phone mockup with WhatsApp chat UI in hero

## Placeholders to Replace for Production

| Placeholder | Location |
|---|---|
| `+351 910 000 000` | footer, WhatsApp links, CTA section |
| `https://wa.me/351910000000` | floating button, CTA section, footer |
| `hello@autoflow.pt` | footer, CTA section |
| Instagram / LinkedIn URLs | footer social buttons (currently `#`) |
| Client logo text (HIDROFIX, STUDIO F., etc.) | logos bar — replace with real client names |
| Testimonial names/quotes | testimonials section |
| Pricing amounts | verify with actual pricing strategy |

## Development

No build tooling. Open directly:

```bash
# Windows — open in default browser
start index.html

# Or serve locally
python -m http.server 8080
```

## Other Files

- `plano_source.html` — internal A4 sales proposal document (separate file, not the website)
- `Exemplo de design.jpg` — original design reference/mockup
- `Plano_Vendas_Autoflow.pdf` — sales plan PDF
