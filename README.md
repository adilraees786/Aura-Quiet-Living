# Aura — Quiet Living

A serene e-commerce experience for **Aura**, a premium warm-minimalist electronics brand. The site showcases organic, calm technology with an in-app **AI Concierge** powered by Google Gemini.

## Overview

- **Brand:** Aura — “Quiet living.” Technology designed to disappear into your life (warm materials, silent operation, natural forms).
- **Tone:** Calm, inviting, grounded; typography uses Inter + Playfair Display on a cream/charcoal palette.
- **Stack:** React 19, TypeScript, Vite 6, Tailwind CSS 4, Google Gemini (Gen AI).

## Features

| Feature | Description |
|--------|-------------|
| **Hero** | Full-screen hero with “Quiet living.” and CTA to the product collection. |
| **Shop** | Product grid (Audio, Wearable, Mobile, Home) with cards and product detail pages (gallery, features, add to cart). |
| **About** | Brand story and philosophy section. |
| **Journal** | Editorial articles (e.g. “The Psychology of Texture”, “Living with Less”) with full article view. |
| **Cart** | Slide-out cart drawer; add/remove items and proceed to checkout. |
| **Checkout** | Checkout view (UI only; no payment integration). |
| **AI Concierge** | Floating chat assistant (Gemini) for product questions, recommendations, and brand philosophy. |

## Project Structure

```
aura-quiet-living/
├── index.html          # Entry HTML
├── index.tsx           # React entry, mounts App and imports index.css
├── index.css           # Tailwind + base styles (fonts, scroll, animations)
├── App.tsx             # Root: view state, nav, cart, routes (home / product / journal / checkout)
├── types.ts            # Product, JournalArticle, ChatMessage, ViewState
├── constants.ts        # PRODUCTS, JOURNAL_ARTICLES, BRAND_NAME
├── vite.config.ts      # Vite + React + Tailwind + env (GEMINI_API_KEY)
├── components/
│   ├── Navbar.tsx      # Fixed nav: logo, Shop / About / Journal, Cart, mobile menu
│   ├── Hero.tsx       # Hero section + “View Collection” CTA
│   ├── ProductGrid.tsx # Product grid + ProductCard
│   ├── ProductDetail.tsx
│   ├── ProductCard.tsx
│   ├── About.tsx
│   ├── Journal.tsx
│   ├── JournalDetail.tsx
│   ├── Footer.tsx
│   ├── CartDrawer.tsx
│   ├── Checkout.tsx
│   ├── Assistant.tsx  # AI Concierge chat (Gemini)
│   └── Features.tsx
└── services/
    └── geminiService.ts  # Gemini chat API (catalog-aware system prompt)
```

## Prerequisites

- **Node.js** (LTS recommended)
- **Gemini API key** (for the AI Concierge)

## Setup & Run

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Configure Gemini API key**  
   Create `.env.local` in the project root and set your key:
   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   ```
   (Vite loads this via `vite.config.ts`; the key is not committed — `.env*.local` is in `.gitignore`.)

3. **Run locally**
   ```bash
   npm run dev
   ```
   App runs at **http://localhost:3000** (configurable in `vite.config.ts`).

4. **Build for production**
   ```bash
   npm run build
   ```

5. **Preview production build**
   ```bash
   npm run preview
   ```

## Scripts

| Command | Description |
|--------|-------------|
| `npm run dev` | Start Vite dev server (default port 3000). |
| `npm run build` | Production build (output in `dist/`). |
| `npm run preview` | Serve the production build locally. |

## Environment

| Variable | Required | Description |
|----------|----------|-------------|
| `GEMINI_API_KEY` | Yes (for AI Concierge) | Google Gemini API key. Without it, the assistant will show a “Missing API Key” message. |

## License

SPDX-License-Identifier: Apache-2.0 (see file headers in source).

---

*You can also open this app in [AI Studio](https://ai.studio/apps/bundled/aura_quiet_living) if you use the bundled version there.*
