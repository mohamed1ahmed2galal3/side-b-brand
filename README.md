# SIDE//B — Brand Landing Page

> **Premium Urban Fashion · Brand Presence Website · SS25**

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Tech Stack](#2-tech-stack)
3. [Design System](#3-design-system)
4. [Project Structure](#4-project-structure)
5. [Components Documentation](#5-components-documentation)
6. [Sections Documentation](#6-sections-documentation)
7. [Assets Management](#7-assets-management)
8. [Responsive Design Strategy](#8-responsive-design-strategy)
9. [Animation System](#9-animation-system)
10. [SEO Setup](#10-seo-setup)
11. [Future Development Roadmap](#11-future-development-roadmap)
12. [Deployment Guide](#12-deployment-guide)
13. [Maintenance Guide](#13-maintenance-guide)
14. [FOR FUTURE AI ASSISTANTS](#14-for-future-ai-assistants)

---

## 1. Project Overview

### Brand Name
**SIDE//B** — The `//` is a core design motif representing duality, the "other side" of identity. It is not decorative; it is structural to the brand and must be preserved in all typographic applications.

### Project Purpose
This is a **brand presence and investor-facing landing page** for SIDE//B, a premium urban fashion label. The site is intentionally **not** an e-commerce store at this stage. Its sole purpose is to:

- Establish SIDE//B as a credible, premium fashion brand
- Present the SS25 collection in an editorial, high-fashion context
- Convert visitors into wholesale inquiries, press contacts, and social followers
- Serve as a proof-of-concept for potential investors and retail partners
- Act as the brand's digital flagship before full e-commerce launches

### Business Goals

| Goal | Mechanism |
|---|---|
| Generate wholesale inquiries | WhatsApp CTA (floating button + contact section) |
| Grow social following | TikTok section with direct link to @sideb736 |
| Establish brand equity | Editorial design, premium copy, luxury aesthetic |
| Attract investors | Professional presentation, clear brand identity |
| Build a contact pipeline | Contact section with WhatsApp integration |

### Target Audience

**Primary:** Fashion-forward consumers aged 18–32, urban-dwelling, culturally engaged, streetwear-literate. They understand the difference between a brand and a label.

**Secondary:** Wholesale buyers, boutique owners, fashion press, brand investors, and collaborators who need to immediately understand the brand's positioning and aesthetic.

**Tertiary:** TikTok-native audiences discovering the brand through social content.

### Brand Identity & Design Philosophy

SIDE//B lives at the intersection of **luxury craftsmanship** and **streetwear authenticity**. The brand rejects the idea that premium fashion must be cold or inaccessible — and equally rejects the idea that streetwear must be loud or disposable.

The design philosophy can be summarized in four words: **Confident. Minimal. Urban. Editorial.**

Every design decision on this site must reinforce that SIDE//B is:
- Worth paying a premium for
- Culturally literate and street-credible
- Not trying too hard (restraint is a luxury signal)
- Forward-thinking but not trend-dependent

---

## 2. Tech Stack

### Current Implementation (Phase 1)
The Phase 1 landing page is delivered as a **single self-contained HTML file** with embedded CSS and JavaScript. This was a deliberate choice for maximum portability, zero dependency management overhead, and instant deployment to any static host.

```
sideb_landing.html    ← Single file, fully self-contained
```

### Phase 2+ Target Stack (React Migration)
When the project scales to a product catalog or e-commerce store, the planned stack is:

| Layer | Technology | Version | Purpose |
|---|---|---|---|
| Framework | React | 18+ | Component architecture |
| Styling | Tailwind CSS | 3+ | Utility-first CSS |
| Animations | Framer Motion | 11+ | Scroll + hover animations |
| Routing | React Router | 6+ | Multi-page navigation |
| State Management | Zustand | 4+ | Cart, filters, UI state |
| Icons | Lucide React | Latest | Minimal icon set |
| Fonts | Google Fonts | — | Playfair Display + Space Grotesk |
| Build Tool | Vite | 5+ | Fast dev/build |
| Deployment | Vercel | — | Edge CDN, preview deploys |
| CMS (future) | Sanity.io | — | Content management |
| E-commerce (future) | Shopify Storefront API | — | Product catalog + checkout |

### Current Dependencies (Phase 1 HTML)

| Resource | Source | Purpose |
|---|---|---|
| Playfair Display | Google Fonts | Display/heading typeface |
| Space Grotesk | Google Fonts | Body/utility typeface |
| WhatsApp Web API | `wa.me` | Contact CTA links |
| TikTok | External link | Social section |

No npm packages, no build step, no bundler required for Phase 1.

---

## 3. Design System

This design system is the single source of truth for all visual decisions on the SIDE//B project. Any future design work — new sections, new pages, new components — must derive from these tokens.

### 3.1 Color Palette

The palette is intentionally **black and white only**. Color is not used as a brand signal; restraint is the luxury signal. The single exception is the `grayscale-to-color` hover reveal on collection images, which makes color feel like a reward.

| Token | Hex | Usage |
|---|---|---|
| `--black` | `#000000` | Primary background |
| `--white` | `#F5F5F3` | Primary text, CTA backgrounds |
| `--gray` | `#888888` | Secondary text, labels, metadata |
| `--dark` | `#0A0A0A` | Alternate section background (about, philosophy, contact) |
| `--card` | `#111111` | Card backgrounds, TikTok frame, contact card |
| `--border` | `rgba(245,245,243,0.1)` | Subtle dividers, card borders |

**Rules:**
- Never introduce a new color without updating this table
- Never use pure `#FFFFFF` — always use `#F5F5F3` (the slight warmth prevents harshness)
- Accent colors (blue, red, green) are prohibited in Phase 1 and Phase 2
- The only "color" permitted is from the clothing photography, revealed on hover

### 3.2 Typography

The typeface pairing is the most critical brand decision on this site. It must not be changed casually.

**Playfair Display** (Display/Editorial)
- Used for: hero headline, section titles, about heading, philosophy card numbers, collection names, footer logo
- Rationale: The serif brings luxury editorial energy — think Vogue, CR Fashion Book. It creates visual tension against the streetwear subject matter, which is exactly the brand's identity.
- Weights used: 400 (regular), 400 italic, 700, 700 italic, 900

**Space Grotesk** (Body/Utility)
- Used for: navigation, body copy, labels, CTAs, captions, stats
- Rationale: A geometric grotesque with subtle personality — more characterful than Inter or Helvetica, but still clean enough to not compete with Playfair.
- Weights used: 300 (body copy), 400, 500, 600, 700 (CTAs)

**Type Scale**

| Role | Font | Size | Weight | Letter Spacing |
|---|---|---|---|---|
| Hero Title | Playfair Display | `clamp(52px, 10vw, 140px)` | 900 | -0.03em |
| Section Title | Playfair Display | `clamp(36px, 5vw, 72px)` | 900 | -0.02em |
| Collection Title | Playfair Display | `clamp(40px, 6vw, 88px)` | 900 | -0.03em |
| Card Title | Playfair Display | 1.4rem | 700 | -0.01em |
| Nav Logo | Playfair Display | 1.3rem | 900 | 0.05em |
| Footer Logo | Playfair Display | 2.5rem | 900 | -0.02em |
| Section Label | Space Grotesk | 0.6rem | 600 | 0.4em |
| Body Copy | Space Grotesk | 0.88–0.9rem | 300 | 0 |
| CTA Buttons | Space Grotesk | 0.7rem | 600–700 | 0.2em |
| Eyebrow Text | Space Grotesk | 0.65rem | 500–600 | 0.35em |
| Metadata/Tags | Space Grotesk | 0.65rem | — | 0.25em |

**Typography Rules:**
- Section labels always use `//` prefix (via CSS `::before`) and uppercase + wide tracking
- Italic Playfair Display is used for the "other side" — softer, more personal moments in headlines
- All uppercase text must use generous letter-spacing (minimum 0.2em)
- Never use Playfair Display for body copy — it becomes illegible at small sizes

### 3.3 Spacing System

All spacing is based on an 8px base unit. The site uses deliberate breathing room — cramped layouts signal low-end brands.

| Token | Value | Usage |
|---|---|---|
| `xs` | 8px | Icon gaps, small internal padding |
| `sm` | 16px | Button padding (vertical), small gaps |
| `md` | 24–28px | Navigation padding, card inner spacing |
| `lg` | 40–48px | Section horizontal padding, grid gaps |
| `xl` | 72–80px | Vertical rhythm within sections |
| `2xl` | 140px | Section top/bottom padding (desktop) |
| `3xl` | 180–200px | Large decorative spacing |

Section padding: `140px 48px` on desktop, scales to `80px 28px` on tablet/mobile.

### 3.4 Animation Principles

Animations serve the brand, not the technology. Every animation must pass this test: *does this make the content feel more premium, or does it distract?*

**Principles:**
1. **Reveal, don't perform.** Scroll animations reveal content — they don't entertain. `fadeUp` with `opacity + transform` is the standard. No bounces, no elastic effects.
2. **Slow is expensive.** Duration range: 0.4s (hover micro-interactions) to 0.9s (scroll reveals). Nothing faster than 0.3s for content.
3. **Stagger creates hierarchy.** When multiple elements reveal, use delay increments of 0.15s to suggest order and importance.
4. **Hover is a reward.** The grayscale-to-color image reveal on collection items is the single biggest animation payoff. Guard it.
5. **Ambient motion.** The hero background text has a slow `slowdrift` animation (20s) — barely perceptible, creates life.
6. **No spin, no pulse (except scroll indicator).** These read as loading states, not premium brand signals.

### 3.5 UI Style Guidelines

**Buttons:**
- Primary (`.btn-primary`): White background, black text, no border-radius, uppercase, wide-tracked. Transitions to gray on hover.
- Ghost (`.btn-ghost`): Transparent background, white text, 1px border with low opacity. Border becomes full white on hover.
- No rounded corners on any buttons — zero border-radius is a deliberate luxury signal.

**Cards:**
- Background: `--card` (`#111`)
- Border: 1px solid `--border` (very subtle)
- No border-radius
- Bottom-border accent (white, scales in from left on hover) is the standard hover treatment for philosophy cards

**Section Labels:**
- Always prefixed with `//` via CSS pseudo-element
- Font: Space Grotesk, 0.6rem, 600 weight, 0.4em letter-spacing, uppercase
- Color: `--gray`
- Followed by 48px margin before the section title

**Lines & Dividers:**
- 1px solid `--border` for structural dividers
- Gradient lines (`rgba(245,245,243,0.15)`) for decorative vertical lines
- The `//` motif appears as text decoration throughout — never as an actual HTML divider

---

## 4. Project Structure

### Phase 1 (Current)
```
sideb/
├── sideb_landing.html          ← Complete self-contained site
└── README.md                   ← This file
```

### Phase 2+ (Planned React Architecture)
```
sideb/
├── public/
│   ├── favicon.ico             ← Brand favicon (to be designed)
│   ├── og-image.jpg            ← Open Graph share image (1200x630)
│   └── fonts/                  ← Self-hosted font fallbacks
│
├── src/
│   ├── components/             ← Reusable UI atoms
│   │   ├── Button/
│   │   │   ├── Button.jsx
│   │   │   └── Button.module.css
│   │   ├── SectionLabel/
│   │   │   └── SectionLabel.jsx
│   │   ├── Marquee/
│   │   │   └── Marquee.jsx
│   │   ├── Cursor/
│   │   │   └── Cursor.jsx
│   │   └── FloatingWhatsApp/
│   │       └── FloatingWhatsApp.jsx
│   │
│   ├── sections/               ← Full-width page sections
│   │   ├── Hero/
│   │   │   ├── Hero.jsx
│   │   │   └── Hero.module.css
│   │   ├── About/
│   │   │   └── About.jsx
│   │   ├── Collection/
│   │   │   ├── Collection.jsx
│   │   │   └── CollectionItem.jsx
│   │   ├── Philosophy/
│   │   │   └── Philosophy.jsx
│   │   ├── TikTok/
│   │   │   └── TikTokSection.jsx
│   │   ├── Contact/
│   │   │   └── Contact.jsx
│   │   └── Footer/
│   │       └── Footer.jsx
│   │
│   ├── pages/                  ← Route-level page components
│   │   ├── Home.jsx            ← Landing page (all sections)
│   │   ├── Collection.jsx      ← Full collection page (Phase 2)
│   │   └── Product.jsx         ← Product detail page (Phase 3)
│   │
│   ├── assets/
│   │   ├── images/
│   │   │   ├── collection/     ← Product photography
│   │   │   │   ├── azure-stripe-shirt.jpg
│   │   │   │   ├── noir-grid-shirt.jpg
│   │   │   │   ├── rust-check-shirt.jpg
│   │   │   │   ├── monochrome-check.jpg
│   │   │   │   ├── forest-plaid-shirt.jpg
│   │   │   │   └── indigo-grid-shirt.jpg
│   │   │   └── brand/          ← Logo, campaign imagery
│   │   │       └── logo.svg
│   │   └── fonts/              ← Self-hosted fonts (optional)
│   │
│   ├── hooks/
│   │   ├── useScrollReveal.js  ← IntersectionObserver for reveal animations
│   │   ├── useParallax.js      ← Parallax effect for hero
│   │   └── useCursor.js        ← Custom cursor position tracking
│   │
│   ├── utils/
│   │   ├── constants.js        ← Brand constants (phone, TikTok URL, etc.)
│   │   └── helpers.js          ← Utility functions
│   │
│   ├── data/
│   │   ├── collection.js       ← Collection items data array
│   │   └── philosophy.js       ← Philosophy cards data array
│   │
│   └── styles/
│       ├── globals.css         ← CSS custom properties, reset, base styles
│       ├── typography.css      ← Type scale definitions
│       └── animations.css      ← Keyframe definitions
│
├── index.html                  ← Vite entry point
├── vite.config.js
├── tailwind.config.js
├── package.json
└── README.md
```

### Folder Purposes

**`src/components/`** — Atoms and molecules. These are the smallest reusable building blocks: a button, a label, a marquee strip. They receive props, have no knowledge of page context, and can be composed into any section. Each component lives in its own folder with its styles co-located.

**`src/sections/`** — Full-width page sections. These are self-contained blocks of the page (Hero, About, etc.). They may consume data from `src/data/` and use components from `src/components/`. They are not reused across pages in the traditional sense — each section is unique.

**`src/pages/`** — Route-level containers. In Phase 1 this is just `Home.jsx` which renders all sections in order. In Phase 2+, this folder grows to include Collection, Product, and Account pages.

**`src/assets/`** — All static files. Images are organized by category. All product images should be named descriptively (kebab-case) to facilitate CMS migration in Phase 3.

**`src/hooks/`** — Custom React hooks that abstract browser APIs (IntersectionObserver, mousemove events, scroll position). Keeping these in hooks rather than inline in components makes them testable and reusable.

**`src/utils/`** — Pure functions and constants with no React dependencies. The `constants.js` file is especially important — all brand configuration (phone number, social URLs, etc.) must live here, not hardcoded in components.

**`src/data/`** — Static data arrays for rendered content (collection items, philosophy cards). In Phase 3 this data migrates to Sanity CMS, but keeping it here in Phase 2 allows easy content updates without touching component logic.

**`src/styles/`** — Global styles that can't live in Tailwind config or component files. CSS custom properties (design tokens) must be defined in `globals.css` so they're available everywhere.

---

## 5. Components Documentation

### 5.1 Button

**Purpose:** Primary interaction element. Two variants: `primary` (white fill) and `ghost` (outline).

**Props (Phase 2):**
```jsx
<Button
  variant="primary" | "ghost"   // Required
  href="/collection"             // Optional: renders as <a> if provided
  onClick={() => {}}             // Optional: onClick handler
  size="md" | "lg"               // Optional: default "md"
  external={false}               // Optional: adds target="_blank" rel="noopener"
>
  Explore Collection
</Button>
```

**Usage Examples:**
```jsx
// Hero CTAs
<Button variant="primary" href="#collection">Explore Collection</Button>
<Button variant="ghost" href="#contact">Contact Us</Button>

// External TikTok link
<Button variant="primary" href="https://tiktok.com/@sideb736" external>
  Follow on TikTok
</Button>
```

**Design Rules:**
- No border-radius (ever)
- Font: Space Grotesk, 0.7rem, 600–700 weight, 0.2em letter-spacing, uppercase
- Primary: `background: #F5F5F3`, `color: #000` → hover: `background: #888`
- Ghost: `border: 1px solid rgba(245,245,243,0.3)` → hover: `border-color: #F5F5F3`
- Padding: `16px 36px`

---

### 5.2 SectionLabel

**Purpose:** Consistent section labeling component. Always renders with `//` prefix and uppercase tracking.

**Props:**
```jsx
<SectionLabel>About the Brand</SectionLabel>
```

**Output renders:** `// ABOUT THE BRAND`

**Design Rules:**
- `//` prefix must always be white (`#F5F5F3`)
- Label text must always be `--gray` (`#888`)
- Font: Space Grotesk, 0.6rem, 600 weight, 0.4em letter-spacing
- Always uppercase
- Always followed by 40–48px margin before the section title

---

### 5.3 Marquee

**Purpose:** Horizontal scrolling text strip. Used between Hero and About sections as a brand signal band.

**Props:**
```jsx
<Marquee
  items={["SIDE//B", "Premium Streetwear", "Urban Identity", "Self Expression"]}
  speed={18}          // Animation duration in seconds (lower = faster)
  separator="·"       // Character between items
  background="white"  // "white" | "black"
/>
```

**Design Rules:**
- White background version: black text, used as a section break
- Text: Playfair Display, 0.75rem, 700 weight, 0.3em tracking, uppercase
- Seamless loop: the track must contain items duplicated to fill at least 200% of viewport width
- Border: 1px on top and bottom

---

### 5.4 Cursor

**Purpose:** Custom cursor that replaces the default OS cursor on desktop. Two-part: a small dot that tracks exactly, and a larger ring that follows with lag.

**Behavior:**
- Dot: 8px circle, instantaneous tracking
- Ring: 36px circle with 0.12 lerp factor (smooth lag)
- On hover over interactive elements: ring expands to 60px with faint white fill
- Disabled on touch devices (detect via `window.matchMedia('(pointer: coarse)')`)

**Design Rules:**
- Never use `pointer-events: none` on the cursor elements — they need to pass events through
- The ring expansion must use `transition` not `animation` to feel responsive

---

### 5.5 FloatingWhatsApp

**Purpose:** Persistent floating button in the bottom-right corner that opens a WhatsApp conversation.

**Props:**
```jsx
<FloatingWhatsApp
  phoneNumber="201102946965"    // No + sign, no spaces
  message="Hi, I'm interested in SIDE//B."  // Pre-filled message (optional)
/>
```

**Design Rules:**
- Position: `fixed`, `bottom: 32px`, `right: 32px`
- Size: 56×56px
- Background: `#F5F5F3` (white)
- No border-radius (consistent with brand)
- WhatsApp SVG icon in `#000`
- Box shadow: `0 8px 32px rgba(0,0,0,0.6)` — ensures visibility on dark backgrounds
- Hover: `translateY(-4px) scale(1.05)`
- `z-index: 200` — above everything including nav

---

## 6. Sections Documentation

### 6.1 Hero Section

**Purpose:** First impression. Establishes brand identity, communicates the brand name and tagline, and provides two CTAs.

**Structure:**
```
[NAV]
[HERO — 100vh]
  Background: Ghost "SIDE//B" text (parallax, barely visible)
  Vertical decorative lines (left + right)
  ─────────────────────────
  [Eyebrow] Premium Urban Fashion · Est. 2024
  [H1] Wear Your
       Other Side.
  ─────────────────────────
  [Bottom row]
    [Brand statement]    [CTAs: Explore Collection | Contact Us]
  [Scroll indicator — right edge]
```

**Key behaviors:**
- Ghost background text drifts slowly on a 20s `slowdrift` animation
- On scroll, the ghost text moves upward at 0.3× scroll speed (parallax)
- All text elements animate in with `fadeUp` staggered: 0.3s, 0.5s, 0.8s, 1.2s
- Nav uses `mix-blend-mode: difference` to invert against the background — switches to a solid black nav after 80px of scroll

**How to modify:**
- Change the headline: edit the `<h1>` content. Keep the `<em>` for the italic line — it's intentional.
- Change the eyebrow: edit the `.hero-eyebrow` text
- Change CTAs: edit the `.hero-ctas` anchor hrefs and text
- The ghost background text: edit `.hero-bg-text` content — keep it as `SIDE//B` for brand consistency

---

### 6.2 About Section

**Purpose:** Brand story and identity. Establishes emotional connection, explains what SIDE//B stands for, and provides credibility through stats.

**Structure:**
```
[Left Column]
  Section Label
  Split headline (bold + italic alternation)
  3 paragraphs of brand narrative
  Stats row (3 cells, bordered)

[Right Column]
  Main image (80% width, full height, right-aligned)
  Overlay image (55% width, bottom-left, overlaps main)
```

**Key behaviors:**
- Both images are grayscale by default (`filter: grayscale(100%)`)
- Hover on either image removes grayscale — `filter: grayscale(0%)` with 0.6s transition
- The large ghost letter `B` in the background (CSS `::before` on the section) adds texture
- All elements have `.reveal` class for scroll-triggered fade-in

**How to modify:**
- Brand story text: edit the three `.about-body` paragraphs
- Stats: edit the three `.stat` blocks — number and label
- Images: swap the `src` attributes on `.about-img-main` and `.about-img-overlay`
- To add a fourth stat, add a new `.stat` div and update the `grid-template-columns` to `repeat(4, 1fr)`

---

### 6.3 Collection Section

**Purpose:** Showcase the SS25 product photography in an editorial gallery format.

**Structure:**
```
[Collection Header]
  Section Label + Title              [Piece count]

[Collection Grid — 12 column asymmetric]
  Row 1: [Item 1 — 5 cols] [Item 2 — 3 cols] [Item 3 — 4 cols]
  Row 2: [Item 4 — 4 cols] [Item 5 — 4 cols] [Item 6 — 4 cols]
```

**Key behaviors:**
- Images are `grayscale(60%)` at rest — partially desaturated, not fully
- On hover: image scales to `1.06×`, grayscale removes completely
- Overlay appears on hover with gradient fade-to-black at the bottom
- Product name and tag slide up from the bottom on hover (10px → 0 translateY)
- Each item has staggered `.reveal` delays

**Grid intentionality:** The asymmetric first row (5-3-4 columns) creates visual interest and prevents the gallery from looking like a grid template. The uniform second row (4-4-4) provides balance. This asymmetry is intentional — do not normalize it to equal columns.

**How to modify:**
- Add a new item: copy a `.col-item` div, change the image `src` and the overlay text
- Change grid proportions: edit the `grid-column` values in the nth-child CSS rules
- Add more items: extend the grid rows by adding `grid-row: 3` items and adding `grid-template-rows` definitions
- Change item names/tags: edit `.col-name` and `.col-tag` text content

**Tablet/Mobile fallback:** The asymmetric grid collapses to a 2-column uniform grid on screens below 1024px.

---

### 6.4 Philosophy Section

**Purpose:** Articulate the brand's values in a structured, premium format. Builds trust with investors and wholesale buyers.

**Cards:**

| Number | Title | Core Message |
|---|---|---|
| 01 | Quality | Materials chosen for durability and feel, not trend |
| 02 | Design | Restraint as the highest form of creativity |
| 03 | Identity | Fashion for the multitude within each person |
| 04 | Culture | Born from the streets, not inspired by them |

**Key behaviors:**
- Ghost number (`-webkit-text-stroke`) at rest, becomes slightly more visible on hover
- Bottom border scales in from left on hover (`transform: scaleX(0)` → `scaleX(1)`)
- Background darkens slightly on hover (`#111` → `#181818`)
- Cards use a 4-column grid on desktop, 2-column on tablet, 1-column on mobile

**How to modify:**
- Change card content: edit `.philo-title` and `.philo-body` text
- Change card count: add/remove `.philo-card` divs and update `grid-template-columns`
- Change numbering: edit `.philo-num` text — always use zero-padded two digits (`01`, `02`)

---

### 6.5 TikTok Section

**Purpose:** Convert site visitors to TikTok followers. Social proof and community building.

**Structure:**
```
[Left Column]
  Section Label
  Headline: "We Live / On Camera."
  Body copy
  @sideb736 handle (underlined, external link)
  "Follow on TikTok" CTA button

[Right Column]
  Branded TikTok card:
    TikTok icon
    @sideb736 username
    "Official SIDE//B TikTok" subtitle
    Stats row: Daily Content | Drops | Culture
    "Follow Now" full-width button
```

**TikTok URL:** `https://www.tiktok.com/@sideb736`
All links in this section must open in a new tab (`target="_blank"`).

**How to modify:**
- Update handle: find all instances of `@sideb736` and `sideb736` and update
- Update TikTok URL: find all instances of `https://www.tiktok.com/@sideb736`
- Update stats: edit the three `.tiktok-stat` blocks
- The TikTok icon is an inline SVG — do not replace with an image for performance reasons

---

### 6.6 Contact Section

**Purpose:** Convert interested visitors into actual contacts. Primary conversion point for wholesale inquiries and press.

**WhatsApp Number:** `+20 110 294 6965` — formatted as `201102946965` in the `wa.me` URL (no plus, no spaces).

**Structure:**
```
[Background ghost text: "CONTACT"]
[Centered content block]
  Eyebrow: // Get in Touch //
  Large headline: "Let's Build / Something / Real."
  Subtext
  [Contact Card]
    [WhatsApp CTA button]
    Contact note with number and response time
```

**`wa.me` URL format:** `https://wa.me/201102946965`
To add a pre-filled message: `https://wa.me/201102946965?text=Hi%2C%20I%E2%80%99m%20interested%20in%20SIDE%2F%2FB`

**How to modify:**
- Change phone number: update `href` on both `.wa-btn` and `.float-wa`, and the `.contact-note` text
- Change headline: edit `.contact-title` — keep the `<em>` for the italic line
- Change subtext: edit `.contact-sub`
- Add email contact: add a second CTA button below the WhatsApp button with `mailto:` href

---

### 6.7 Footer

**Purpose:** Brand closure. Provides navigation, social links, and copyright. Clean and minimal — no clutter.

**Structure:**
```
[Footer Top]
  [Brand: SIDE//B logo + tagline]    [Links: Navigate | Social]

[Footer Bottom]
  Copyright text                     Social link row
```

**How to modify:**
- Add navigation links: add `<li><a>` items to the "Navigate" footer column
- Add social platforms: add items to the "Social" footer column
- Update copyright year: edit the `.footer-copy` text — in Phase 2, make this dynamic with `new Date().getFullYear()`

---

## 7. Assets Management

### 7.1 Image Inventory

| Filename | Used In | Description |
|---|---|---|
| `WhatsApp_Image_2026-06-12_at_12_02_50_AM.jpeg` | Collection item 1, About (overlay) | Blue/white stripe short-sleeve shirt |
| `WhatsApp_Image_2026-06-12_at_12_01_57_AM.jpeg` | Collection item 2 | Dark navy plaid shirt (worn, street photo) |
| `WhatsApp_Image_2026-06-12_at_12_01_57_AM__1_.jpeg` | Collection item 5, About (main) | Green tartan plaid shirt |
| `WhatsApp_Image_2026-06-12_at_12_01_57_AM__2_.jpeg` | Collection item 3 | Rust/terracotta check cropped shirt |
| `WhatsApp_Image_2026-06-12_at_12_01_57_AM__3_.jpeg` | Collection item 4, About (overlay) | Black/grey check shirt (Butter Goods) |
| `WhatsApp_Image_2026-06-12_at_12_01_56_AM.jpeg` | Collection item 6 | Blue plaid wide-fit shirt |

### 7.2 Image Optimization Guidelines

**For Phase 2 React migration:**

1. **Rename all images** using the descriptive naming convention established in the collection data:
   - `azure-stripe-shirt.jpg`
   - `noir-grid-shirt-worn.jpg`
   - `forest-plaid-shirt.jpg`
   - `rust-check-shirt.jpg`
   - `monochrome-check-shirt.jpg`
   - `indigo-grid-shirt.jpg`

2. **Export specifications:**
   - Collection grid: 800×1000px (portrait, 3:4 ratio) for product shots, WebP format
   - About section main image: 900×1200px, WebP
   - About section overlay image: 600×600px, WebP
   - OG Image: 1200×630px, JPEG

3. **Use `next/image` or `<img loading="lazy">` for all below-the-fold images**

4. **Compression targets:**
   - Product shots: 85% quality WebP (typically 60–120KB)
   - About imagery: 80% quality WebP

5. **Always provide `alt` text** — describe the garment specifically, not generically. `"SIDE//B Forest Plaid Oversized Shirt SS25"` not `"shirt"`.

### 7.3 Brand Assets

**Logo Treatment:**
The brand name `SIDE//B` is the logo. There is no separate logomark at this stage.

- **Primary:** `SIDE//B` in Playfair Display, weight 900
- **The `//` must never be replaced** with a single `/`, `|`, or any other character
- **Minimum size:** 18px in any display context
- **Color:** White on dark backgrounds, black on light backgrounds
- **Never italicize the logo** — italic is reserved for editorial emphasis in headlines, not the brand mark

**Favicon (to be created):** A minimal `S//B` or `//` mark, white on black, 512×512px source.

---

## 8. Responsive Design Strategy

### 8.1 Breakpoints

| Name | Width | Description |
|---|---|---|
| Mobile | < 640px | Single column, stacked layouts |
| Tablet | 640px – 1024px | Two-column where appropriate |
| Desktop | > 1024px | Full layout with asymmetric grids |

### 8.2 Mobile Behavior (< 640px)

- Navigation: hamburger menu, links stack vertically in a full-width overlay panel
- Hero: headline scales down to `clamp(40px, 14vw, 80px)`, bottom row stacks vertically
- About: single column, image stack collapses, stats go 2-column
- Collection: uniform 2-column grid, all items equal size, `aspect-ratio: 3/4`
- Philosophy: single column cards
- TikTok: stacked, left content first
- Custom cursor: **disabled** on touch devices (detect via pointer media query)
- Floating WhatsApp: remains active — critical conversion path on mobile

### 8.3 Tablet Behavior (640px – 1024px)

- Navigation: hamburger menu replaces nav links
- Hero: scroll indicator hidden, bottom row wraps
- About: single column (left content stacked above right image)
- Collection: 2×3 uniform grid (all items span 6 of 12 columns)
- Philosophy: 2×2 card grid
- TikTok: single column, full width
- Section padding reduces: `140px 48px` → `80px 28px`

### 8.4 Desktop Behavior (> 1024px)

- Full layout as designed
- Custom cursor active
- Asymmetric collection grid (5-3-4 / 4-4-4)
- About section 2-column split layout
- TikTok section 2-column split layout
- Philosophy 4-column card row

---

## 9. Animation System

### 9.1 Scroll Reveal Animations

All content sections use an `IntersectionObserver`-based reveal system.

**Implementation:**
- Elements with class `.reveal` start at `opacity: 0; transform: translateY(40px)`
- When 10% of the element enters the viewport (with a -50px root margin), the class `.visible` is added
- `.visible` sets `opacity: 1; transform: translateY(0)` with a `0.9s ease` transition
- Stagger delays: `.reveal-delay-1` (0.15s), `.reveal-delay-2` (0.3s), `.reveal-delay-3` (0.45s)

**In Phase 2 (Framer Motion):**
```jsx
import { motion } from 'framer-motion';

const fadeUp = {
  hidden: { opacity: 0, y: 40 },
  visible: { opacity: 1, y: 0, transition: { duration: 0.9, ease: [0.25, 0.46, 0.45, 0.94] } }
};

// Usage:
<motion.div
  variants={fadeUp}
  initial="hidden"
  whileInView="visible"
  viewport={{ once: true, margin: "-50px" }}
>
```

### 9.2 Hover Animations

| Element | Hover Effect | Duration |
|---|---|---|
| Collection image | Scale 1.06×, grayscale → color | 0.7s / 0.5s |
| Collection overlay | Opacity 0 → 1 | 0.4s |
| Collection text | translateY(10px) → 0 | 0.4s / 0.45s |
| About images | grayscale → color | 0.6s |
| Philosophy cards | Background darkens, bottom border in | 0.4s / 0.5s |
| Ghost card numbers | Stroke opacity increases | 0.4s |
| Primary button | Background → gray | 0.3s |
| Ghost button | Border → full white | 0.3s |
| Nav links | Underline slides in | 0.4s |
| Floating WhatsApp | translateY(-4px) scale(1.05) | 0.3s |
| TikTok handle | Opacity 0.6 | 0.3s |

### 9.3 Ambient / Continuous Animations

| Element | Animation | Duration |
|---|---|---|
| Hero ghost background text | `slowdrift` (subtle rotation + translation) | 20s infinite alternate |
| Marquee strip | `marquee` (translateX 0 → -50%) | 18s linear infinite |
| Slash divider text | `marquee` | 25s linear infinite |
| Scroll indicator line | `scrollpulse` (opacity + scaleY) | 2s infinite |

### 9.4 Parallax

The hero ghost background text moves at `0.3 × scrollY` pixels upward as the user scrolls. This creates a sense of depth without being distracting.

```javascript
window.addEventListener('scroll', () => {
  bgText.style.transform = `translate(-50%, calc(-50% + ${window.scrollY * 0.3}px))`;
});
```

### 9.5 Page Entry Animation

Hero elements animate in on page load with `animation: fadeUp` via CSS, not JavaScript, to avoid flash-of-invisible-content:
- Eyebrow: 0.3s delay
- H1: 0.5s delay
- Bottom row: 0.8s delay
- Scroll indicator: 1.2s delay

### 9.6 Respecting Reduced Motion

In Phase 2, all animations must respect `prefers-reduced-motion`:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 10. SEO Setup

### 10.1 Current Meta Tags (Phase 1)

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="SIDE//B — Premium Urban Fashion. Where identity meets craft.">
<title>SIDE//B — Premium Urban Fashion</title>
```

### 10.2 Phase 2 Full SEO Setup

Add to `<head>`:

```html
<!-- Primary Meta -->
<meta name="title" content="SIDE//B — Premium Urban Fashion">
<meta name="description" content="SIDE//B is a premium urban fashion label. Luxury craftsmanship meets streetwear culture. Shop the SS25 collection.">
<meta name="keywords" content="SIDE B, urban fashion, premium streetwear, SS25, fashion Cairo, luxury streetwear">
<meta name="author" content="SIDE//B">
<meta name="robots" content="index, follow">

<!-- Open Graph -->
<meta property="og:type" content="website">
<meta property="og:url" content="https://sideb.com/">
<meta property="og:title" content="SIDE//B — Premium Urban Fashion">
<meta property="og:description" content="Where identity meets craft. Shop the SIDE//B SS25 Collection.">
<meta property="og:image" content="https://sideb.com/og-image.jpg">

<!-- Twitter Card -->
<meta property="twitter:card" content="summary_large_image">
<meta property="twitter:url" content="https://sideb.com/">
<meta property="twitter:title" content="SIDE//B — Premium Urban Fashion">
<meta property="twitter:description" content="Where identity meets craft. Shop the SIDE//B SS25 Collection.">
<meta property="twitter:image" content="https://sideb.com/og-image.jpg">

<!-- Canonical -->
<link rel="canonical" href="https://sideb.com/">
```

### 10.3 Structured Data (Phase 2)

Add `application/ld+json` for brand and product schema:

```json
{
  "@context": "https://schema.org",
  "@type": "ClothingStore",
  "name": "SIDE//B",
  "description": "Premium urban fashion label",
  "url": "https://sideb.com",
  "sameAs": [
    "https://www.tiktok.com/@sideb736"
  ],
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+20-110-294-6965",
    "contactType": "customer service",
    "availableLanguage": ["English", "Arabic"]
  }
}
```

### 10.4 Performance Optimization

- **Fonts:** Use `display=swap` parameter on Google Fonts (already implemented)
- **Images:** Use `loading="lazy"` on all below-fold images
- **CSS:** The single-file approach eliminates render-blocking CSS requests
- **JS:** All JavaScript is deferred (placed before `</body>`)
- **No external JS libraries** in Phase 1 — zero JavaScript bundle overhead
- **Target Lighthouse score:** 95+ Performance, 100 Accessibility, 100 Best Practices, 100 SEO

---

## 11. Future Development Roadmap

### Phase 1 — Brand Landing Page *(Current — Completed)*
**Goal:** Establish brand identity, generate first contacts, grow TikTok following.

- [x] Single-page HTML landing page
- [x] Hero section with brand statement
- [x] About section with brand story
- [x] Collection gallery (6 SS25 pieces)
- [x] Philosophy section (4 pillars)
- [x] TikTok social section
- [x] WhatsApp contact section + floating button
- [x] Fully responsive (mobile/tablet/desktop)
- [x] Custom cursor
- [x] Scroll reveal animations
- [ ] Favicon design
- [ ] OG image creation
- [ ] Domain setup and deployment

---

### Phase 2 — Product Catalog *(Estimated: 3–4 months post-Phase 1)*
**Goal:** Allow visitors to browse the full collection without a cart. Think lookbook + product pages.

**Deliverables:**
- React + Vite + Tailwind CSS migration
- Multi-page routing (React Router)
- Full collection page with filtering (by category, color, size)
- Individual product pages with image gallery
- Sanity CMS integration for content management
- Instagram feed integration
- Performance audit and optimization
- Google Analytics 4 setup

**New Sections/Pages:**
- `/collection` — Full product catalog grid
- `/collection/:slug` — Product detail page
- `/lookbook` — Editorial photography section

---

### Phase 3 — Full E-commerce *(Estimated: 6–9 months post-Phase 1)*
**Goal:** Enable online purchasing. First revenue-generating version of the site.

**Deliverables:**
- Shopify Storefront API integration (headless commerce)
- Shopping cart (Zustand state management)
- Checkout flow (Shopify-hosted checkout)
- Payment processing (card + installments)
- Order confirmation emails
- Inventory management via Shopify admin
- Size guide component
- Product reviews section
- Wishlist functionality
- Arabic language support

---

### Phase 4 — Admin Dashboard *(Estimated: 12 months post-Phase 1)*
**Goal:** Give the brand owner a custom interface to manage content, products, and orders.

**Deliverables:**
- Custom admin panel (or extended Sanity Studio)
- Product upload and management
- Order tracking and management
- Customer inquiry inbox (WhatsApp integration dashboard)
- Sales analytics overview
- Collection launch scheduling
- Announcement/banner management

---

### Phase 5 — Customer Accounts *(Estimated: 18 months post-Phase 1)*
**Goal:** Build a loyal customer base with personal accounts and loyalty features.

**Deliverables:**
- Customer account creation (email + social login)
- Order history and tracking
- Saved addresses
- Wishlist persistence
- Early access / waitlist for drops
- Loyalty points system
- Referral program
- Email marketing integration (Klaviyo)

---

## 12. Deployment Guide

### 12.1 Phase 1 — Static HTML Deployment

The Phase 1 site is a single HTML file. It can be deployed anywhere that serves static files.

**Option A: Vercel (Recommended)**
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy from the directory containing sideb_landing.html
vercel

# Follow prompts. Site will be live at a .vercel.app URL instantly.
# To add custom domain: vercel domains add sideb.com
```

**Option B: Netlify**
```bash
# Drag and drop the sideb_landing.html file to app.netlify.com/drop
# Or use Netlify CLI:
netlify deploy --dir . --prod
```

**Option C: GitHub Pages**
1. Create a GitHub repository
2. Rename `sideb_landing.html` to `index.html`
3. Push to the `main` branch
4. Go to Settings → Pages → Deploy from main branch

### 12.2 Phase 2 — React Build & Deploy

```bash
# Clone repository
git clone https://github.com/sideb/sideb-website.git
cd sideb-website

# Install dependencies
npm install

# Start development server
npm run dev
# → http://localhost:5173

# Build for production
npm run build
# → /dist folder

# Preview production build locally
npm run preview

# Deploy to Vercel
vercel --prod
```

### 12.3 Environment Variables (Phase 2+)

Create a `.env.local` file (never commit this to git):

```env
# Sanity CMS
VITE_SANITY_PROJECT_ID=your_project_id
VITE_SANITY_DATASET=production

# Shopify (Phase 3)
VITE_SHOPIFY_STORE_DOMAIN=sideb.myshopify.com
VITE_SHOPIFY_STOREFRONT_TOKEN=your_token

# Analytics
VITE_GA4_MEASUREMENT_ID=G-XXXXXXXXXX
```

**Note:** The WhatsApp number and TikTok URL are brand constants, not sensitive — they can live in `src/utils/constants.js`, not `.env`.

### 12.4 Production Checklist

Before every production deployment:
- [ ] Images optimized and in WebP format
- [ ] `og-image.jpg` present in `/public`
- [ ] All links tested (WhatsApp, TikTok, nav anchors)
- [ ] Mobile layout tested on real device (not just browser emulation)
- [ ] Lighthouse score run and logged
- [ ] Console is error-free
- [ ] `robots.txt` present
- [ ] Analytics tag verified

---

## 13. Maintenance Guide

### 13.1 Updating Contact Information

**WhatsApp Number** appears in 3 places in `sideb_landing.html`:
1. `.float-wa` href: `https://wa.me/201102946965`
2. `.wa-btn` href: `https://wa.me/201102946965`
3. `.contact-note` text: `+20 110 294 6965`

In Phase 2, this will be a single constant in `src/utils/constants.js`:
```javascript
export const BRAND = {
  whatsapp: "201102946965",
  whatsappUrl: "https://wa.me/201102946965",
  tiktok: "https://www.tiktok.com/@sideb736",
  tiktokHandle: "@sideb736",
};
```

### 13.2 Adding New Products to the Collection

In Phase 1 (HTML):
1. Add a new `.col-item` div inside `.collection-grid`
2. Set the image `src` to the new product photo
3. Update the `.col-name` and `.col-tag` text
4. Update the piece count in `.collection-count`
5. Adjust the `grid-column` and `grid-row` CSS for the new item's layout position

In Phase 2 (React + Data):
```javascript
// src/data/collection.js
export const collection = [
  {
    id: "azure-stripe-shirt",
    name: "Azure Stripe Shirt",
    tag: "SS25 · Relaxed Fit",
    image: "/assets/images/collection/azure-stripe-shirt.webp",
    alt: "SIDE//B Azure Stripe Short Sleeve Shirt SS25",
  },
  // Add new item here:
  {
    id: "new-item-name",
    name: "New Item Display Name",
    tag: "SS25 · Fit Description",
    image: "/assets/images/collection/new-item.webp",
    alt: "Descriptive alt text for SEO and accessibility",
  },
];
```

### 13.3 Adding a New Section

1. Create the section HTML structure inside `sideb_landing.html`
2. Follow the section anatomy:
   - Section wrapper: `<section id="section-name">`
   - Background: either `var(--black)` or `var(--dark)` — alternate between sections
   - Padding: `140px 48px` (desktop), responsive via media queries
   - First child: `<div class="section-label reveal">Label Text</div>`
   - Add `.reveal` class to all content elements
3. Add a nav link: `<li><a href="#section-name">Label</a></li>`
4. Follow the color alternation pattern:
   - Hero: black
   - About: dark
   - Collection: black
   - Philosophy: dark
   - TikTok: black
   - Contact: dark
   - Footer: black

### 13.4 Modifying the Color Scheme

If the brand ever approves a color accent (Phase 3+):
1. Add the new color token to `:root` in the CSS
2. Document it in the Design System section of this README
3. Apply it sparingly — only one accent color ever, used in one or two specific contexts
4. Never apply color to text — only to borders, underlines, or backgrounds

### 13.5 Updating Typography

If the typeface pairing changes:
1. Update the Google Fonts `<link>` in `<head>`
2. Update `--font-display` and `--font-body` CSS custom properties
3. Update the Typography section of this README with the rationale for the change

---

## 14. FOR FUTURE AI ASSISTANTS

This section is written specifically for AI coding assistants (Claude, GPT, Gemini, Cursor, Copilot, etc.) who will work on this project in future sessions. Read this before making any changes.

---

### Project Identity

**This is SIDE//B.** A premium urban fashion brand. The website is designed to make visitors feel they've discovered something exclusive. Every design decision has been made to signal quality, restraint, and cultural authenticity. Do not make this site feel like a generic fashion e-commerce template.

The `//` in `SIDE//B` is non-negotiable. It appears throughout the site as a motif. Never replace it, simplify it, or "clean it up."

---

### Architecture Decisions

**Phase 1 is a single HTML file by design.** Do not refactor it into React "to improve it" unless the user explicitly requests Phase 2 migration. The single-file approach has zero build complexity and deploys anywhere instantly. This was intentional.

**When React migration is requested**, follow the project structure defined in Section 4 of this README exactly. Do not invent a new structure.

**Do not introduce new dependencies** without a clear reason. Phase 1 intentionally has zero npm dependencies. Phase 2 dependencies are pre-selected in Section 2 of this README.

---

### Design Constraints

These are hard rules. Do not violate them:

1. **Color palette is black and white only.** `#000000`, `#F5F5F3`, `#888888`, `#0A0A0A`, `#111111`. No blue, no red, no green, no brand accent colors until explicitly approved by the brand owner.

2. **No border-radius anywhere.** Zero. On buttons, cards, images, containers — nothing. Square corners are a deliberate luxury signal on this brand.

3. **Playfair Display for display headings, Space Grotesk for everything else.** Do not suggest replacing these. Do not add a third typeface.

4. **The `//` motif must appear as section label prefixes** via CSS `::before` pseudo-element. Do not change this pattern.

5. **Images should be grayscale at rest, revealing color on hover.** This is the collection section's primary interaction. Do not remove this behavior.

6. **Animations must be slow and premium.** Minimum 0.4s for micro-interactions, 0.9s for scroll reveals. No bounces, no elastics, no "fun" easing curves.

7. **No border-radius on images.** Images are displayed with sharp corners throughout.

---

### Coding Conventions

**CSS:**
- Use CSS custom properties (`--black`, `--white`, etc.) for all color values — never hardcode hex in CSS rules
- Use `clamp()` for fluid typography (`clamp(min, viewport-unit, max)`)
- Class names are kebab-case, descriptive, and semantic (`.col-overlay`, `.philo-card`, `.hero-eyebrow`)
- No CSS frameworks in Phase 1 — all styles are hand-written
- Media queries use `max-width` (mobile-last in Phase 1, adjust to mobile-first in Phase 2 Tailwind)

**JavaScript:**
- Phase 1 uses vanilla JS only — no libraries, no frameworks
- All JS is deferred (before `</body>`)
- Use `IntersectionObserver` for scroll reveals, not scroll event listeners
- Cursor tracking uses `requestAnimationFrame` for smooth performance
- Mobile devices: detect touch via `window.matchMedia('(pointer: coarse)')` to disable cursor

**HTML:**
- Semantic elements: `<nav>`, `<section>`, `<footer>`, `<h1>`–`<h4>`
- One `<h1>` per page (the hero headline)
- All images must have descriptive `alt` text
- All external links must have `target="_blank" rel="noopener noreferrer"`
- `aria-label` on icon-only interactive elements (floating WhatsApp button)
- `aria-hidden="true"` on purely decorative elements (ghost background text, marquee)

---

### Contact Information (Brand Constants)

**Never infer or guess these. Use exactly:**

- WhatsApp: `+20 110 294 6965` → `wa.me` URL: `https://wa.me/201102946965`
- TikTok handle: `@sideb736`
- TikTok URL: `https://www.tiktok.com/@sideb736`

If the user asks you to update contact information, update ALL instances simultaneously and confirm the count of replacements made.

---

### Content Voice & Copy

When writing or editing copy for SIDE//B:

- **Tone:** Confident, not arrogant. Premium, not pretentious. Urban, not aggressive.
- **Voice:** First person plural ("we," "our") for brand statements. Second person ("you," "your") for CTAs and direct address.
- **Avoid:** Generic fashion clichés ("elevated," "curated," "artisanal," "luxe"). These read as hollow.
- **Use instead:** Specific, concrete language. "We obsess over silhouette" not "We create elevated pieces."
- **Headlines:** Playfair Display italic is used for the "emotional" or "other" line in a split headline. The bold line is declarative; the italic line is the turn. This is intentional — preserve the pattern.
- **The `//` as separator:** In headlines with two thoughts, a line break separates them, not `//`. The `//` only appears in the brand name itself and in section labels.

---

### Section Order & Visual Rhythm

The section order is:

```
Nav → Hero → Marquee → About → Collection → Philosophy → Slash Divider → TikTok → Contact → Footer
```

Do not reorder sections without discussion. The alternating `--black` / `--dark` backgrounds create visual breathing room between sections — this rhythm depends on the order.

---

### Known Future Work Items

These are documented decisions deferred to future phases. Do not implement them in Phase 1 unless explicitly requested:

- Favicon and brand mark design
- OG image for social sharing
- Arabic language (RTL) support — important for the Egyptian market
- Product sizing information
- Instagram feed integration
- Email newsletter signup
- Loading screen / page transition animation
- Lookbook editorial photography section

---

### What Makes This Site Succeed

The site works because of three things:

1. **Restraint.** Every element earns its place. If you're considering adding something, ask: does this make the brand feel more premium, or does it add noise?

2. **Typography tension.** Playfair Display (luxury serif) against Space Grotesk (clean grotesque) on a streetwear brand creates productive dissonance — that's the brand's identity in typographic form.

3. **The reveal.** Collection images are grayscale until hovered. Color is a reward. This single interaction communicates more about the brand's relationship with exclusivity than any headline could.

Protect all three of these as the project grows.

---

*README maintained by: Development team*
*Last updated: June 2025*
*Phase: 1.0 — Brand Landing Page (Complete)*
*Next milestone: Phase 1.1 — Favicon, OG image, domain deployment*
