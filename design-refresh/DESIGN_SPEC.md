# DESIGN_SPEC — Toyota Sales Advisor Landing Page Refresh

**Version:** 1.0  
**Date:** 2026-06-16  
**Source files:** `design/index.html`, `design/styles.css`, `uiux/UIUX_PROPOSAL.md`

---

## 1. Design Goals

1. Earn trust within 5 seconds — Lim must feel like a real, local, responsive person.
2. Reduce bounce from generic copy — every section must answer "why contact Lim?"
3. Surface WhatsApp CTA at every high-intent scroll moment.
4. Add model category filtering to reduce mobile scan friction across 12 cards.
5. Replace placeholder testimonials with an honest "Why Lim" reasons section.
6. Add advisor identity slot (avatar + dealership name) to anchor credibility.
7. Improve tap targets and focus states for mobile and keyboard users.

---

## 2. Color Tokens

| Token          | Value        | Usage                                      |
|----------------|--------------|--------------------------------------------|
| `--red`        | `#d71920`    | Primary CTA, eyebrow labels, category badges, checklist icons |
| `--red-dark`   | `#9f1016`    | Hover/active states on red elements         |
| `--ink`        | `#10131a`    | Headings, body text, default button bg      |
| `--muted`      | `#5d6675`    | Secondary/supporting text, descriptions     |
| `--line`       | `#e6e8ee`    | Borders, dividers, trust strip grid lines   |
| `--soft`       | `#f6f7f9`    | Section alt-backgrounds, model card image area |
| `--white`      | `#ffffff`    | Card backgrounds, header background         |
| `--wa-green`   | `#20b15a`    | Sticky WhatsApp CTA only — do not reuse     |
| `--shadow-sm`  | `0 10px 35px rgba(16,19,26,.06)` | Card resting shadow        |
| `--shadow-md`  | `0 14px 42px rgba(16,19,26,.075)` | Model card shadow          |
| `--shadow-lg`  | `0 24px 70px rgba(16,19,26,.12)` | Hero card shadow            |

No new colors should be introduced. All design decisions must use these tokens.

---

## 3. Typography

| Role     | Size (clamp)                      | Weight | Letter-spacing | Color       |
|----------|-----------------------------------|--------|----------------|-------------|
| H1       | `clamp(38px, 8vw, 78px)`          | 800    | `-0.055em`     | `--ink`     |
| H2       | `clamp(29px, 5vw, 52px)`          | 800    | `-0.04em`      | `--ink`     |
| H3       | `22px`                            | 800    | `-0.025em`     | `--ink`     |
| Lead     | `clamp(18px, 2vw, 22px)`          | 400    | normal         | `--muted`   |
| Body     | `16px` / `line-height: 1.6`       | 400    | normal         | `--ink`     |
| Eyebrow  | `12px` / uppercase               | 850    | `0.16em`       | `--red`     |
| Caption  | `13–14px`                         | 400    | normal         | `--muted`   |

Font stack: `Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`

Mobile overrides (≤759px):
- H1: `clamp(36px, 11.5vw, 48px)`
- H2: `clamp(28px, 8.5vw, 38px)`
- Lead: `17px`

---

## 4. Spacing System

| Token               | Value                                    |
|---------------------|------------------------------------------|
| Section v-padding   | `clamp(54px, 8vw, 110px)` top/bottom     |
| Section h-padding   | `clamp(18px, 5vw, 64px)` left/right      |
| Max content width   | `1180px`, `margin: 0 auto`               |
| Card gap (grid)     | `18px` model grid / `28px` two-col       |
| Card inner padding  | `26px` default / `18px` mobile           |
| Border radius (card)| `28px` model cards / `24px` default      |
| Button border radius| `999px` (full pill)                      |

---

## 5. Component Reference

### 5a. Button
- Min height: `50px` (desktop) / `52px` (mobile)
- Min tap width on mobile: `100%` (full-width stacked)
- Padding: `0 22px`
- States: resting / `:hover` (translateY -1px) / `:focus-visible` (2px offset outline in `--red`)
- **Primary:** `--red` bg, white text
- **Default:** `--ink` bg, white text
- **Small (header):** same pill, `min-height: 42px`, `font-size: 14px`
- Do not use outline-only buttons — insufficient contrast for mobile scanning

### 5b. Card (default)
- Background: `--white`
- Border: `1px solid var(--line)`
- Border radius: `24px`
- Shadow: `--shadow-sm`
- Padding: `clamp(24px, 4vw, 38px)`

### 5c. Model Card
- Border radius: `28px`
- Image area height: `154px` desktop / `124px` mobile / `112px` at ≤380px
- Image area background: gradient (`--white → --soft`) with subtle vignette shadow
- Category badge: `--red`, `font-weight: 900`, uppercase, `12px`, `letter-spacing: 0.12em`
- CTA: `--red`, `font-weight: 900`, pinned to card bottom via `margin-top: auto`
- **Refresh change:** CTA must be `display: inline-block; padding: 10px 0` for adequate tap target

### 5d. Hero Card (dark)
- Background: dark gradient (`#202633 → #080a0f`) with radial red glow at top-right
- Inner showcase panel: frosted glass effect, `border: 1px solid rgba(255,255,255,.12)`
- Bottom price card: white, `border-radius: 22px`, bottom-anchored at `24px`
- Min height: `390px` desktop / `330px` mobile / `310px` at ≤520px

### 5e. Trust Strip
- Layout: 4-col desktop / 2-col mobile / 1-col at ≤380px
- Background: `--line` grid with `--white` cells
- Cell padding: `20px` desktop / `16px 14px` mobile
- **Refresh addition:** Add small inline SVG icon (16–18px) before each `<strong>` label

### 5f. Steps (Process)
- Each step: `display: flex; gap: 14px; align-items: center; padding: 16px`
- Number circle: `34px`, `--red` bg, white text, `border-radius: 50%`
- **Refresh addition:** Add WhatsApp CTA button after the 4 steps

### 5g. Sticky WhatsApp Bar
- Mobile: full-width pill, bottom `18px`, `min-height: 56px`
- Desktop: right-anchored, `auto` width, `padding: 0 28px`
- Background: `--wa-green`, shadow: `0 18px 42px rgba(32,177,90,.35)`
- **Refresh addition:** Prepend WhatsApp SVG icon (24px, white) before label text
- Footer must have `padding-bottom: 96px` (mobile) / `36px` (desktop) to clear bar

### 5h. FAQ Accordion
- Uses native `<details>/<summary>` — keyboard accessible by default
- `summary`: `font-weight: 850; cursor: pointer`
- Border: `1px solid var(--line)`, `border-radius: 24px`, `padding: 20px 24px`
- `margin-bottom: 12px` between items

### 5i. Category Filter Tabs (new)
- Positioned above model grid
- Role: `tablist`, each button: `role="tab"`, `aria-selected`
- Active state: `--red` bg, white text
- Inactive: `--soft` bg, `--ink` text
- Border radius: `999px` per tab
- JS: toggle `data-category` visibility on `.model-card[data-category]`
- Categories: All / Sedan / SUV / MPV / Pickup / EV

### 5j. Advisor Avatar Slot (new)
- Circular, `80px × 80px` minimum
- Positioned inside or above the About section H2
- Placeholder: grey silhouette circle if real photo unavailable
- `alt="Lim, Toyota Sales Advisor Penang"`

### 5k. Why Lim Section (new — replaces placeholder testimonials)
- 3–4 reason cards in a grid matching the model grid layout
- Each card: icon + bold title + 1-sentence description
- Reasons (draft): Fast WhatsApp response / Local Penang guidance / Clear loan & booking steps / Follow-up support
- These are honest claims that do not require real social proof to publish

---

## 6. Section Layout and Responsive Behavior

### Header (sticky)
- Desktop: brand + nav (Models / Finance / FAQ) + WhatsApp button
- Mobile ≤759px: brand + WhatsApp button (nav hidden)
- Mobile ≤520px: brand only (nav and header button hidden); rely on sticky bar
- `backdrop-filter: blur(16px)` on white `rgba(255,255,255,.88)` bg

### Hero
- Desktop: 2-col (`1.1fr .9fr`), copy left, dark card right
- Mobile: single column, copy then card
- CTA row: column on mobile, row on desktop

### Trust Strip
- Full-bleed with max-width `1180px`; margin uses section h-padding

### About Lim
- Desktop: 2-col (`1.1fr .9fr`), heading left, panel right
- Mobile: stacked
- New: avatar slot above or beside H2

### Model Grid
- Desktop: 3-col
- Mobile: 1-col (responsive to 2-col at ~500px if space allows — optional)
- Filter tabs above grid, full-width, scroll-x on mobile if needed

### Finance / Process
- Desktop: 2-col (heading left, steps right)
- Mobile: stacked
- New: WhatsApp CTA button after step 4

### Why Lim (new)
- Desktop: 3-col or 2-col reason cards
- Mobile: 1-col or 2-col

### FAQ
- Single column, full-width, max `1180px`

### Location
- Desktop: 2-col (text left, CTA right)
- Mobile: stacked, CTA full-width

### Footer
- Single column, `padding-bottom` clears sticky bar

---

## 7. Accessibility Notes

| Item | Requirement |
|------|-------------|
| Focus visible | All interactive elements need `:focus-visible` outline: `2px solid var(--red)` at `2px offset` |
| Sticky bar | Must have `aria-label="WhatsApp Lim"` |
| Model card links | Must be `<a>` (not `<div>`) with descriptive text (already is) |
| Hero showcase | `aria-hidden="true"` (decorative — already implemented) |
| Filter tabs | `role="tablist"` / `role="tab"` / `aria-selected` |
| Color contrast | White on `--red` (#d71920): passes AA at ≥18px bold; verify at 12px eyebrow — use weight/size to compensate if needed |
| `lang="en"` | Set on `<html>` (already done) |
| Alt text | All model images: `alt="Toyota [Model Name]"`; advisor photo: `alt="Lim, Toyota Sales Advisor Penang"` |
| Skip link | Add `<a class="skip-link" href="#main">Skip to content</a>` as first body child |
| FAQ | `<details>/<summary>` is natively keyboard accessible — keep as-is |

---

## 8. Content Placeholder Rules

These rules govern every placeholder that appears in the live build. Placeholders that damage trust must be blocked from production.

| Placeholder | Status | Rule |
|-------------|--------|------|
| WhatsApp number `60000000000` | **BLOCKER** | Must not go live. Centralise in one JS const: `const WA_NUMBER = "60XXXXXXXXX"` |
| Branch / dealership address | **BLOCKER** | Must not go live. Use `[Dealership name and address]` token in source; render as styled placeholder in dev only |
| Advisor profile photo | **Deferred** | Show circular silhouette placeholder in dev; swap with real photo before launch |
| Testimonials / customer quotes | **Remove pre-launch** | Replace section with "Why Lim" reasons cards (section 5k) which require no real social proof |
| `response-note` dev warning in hero | **BLOCKER** | Replace with real response-time copy: e.g. "Usually replies within the hour" |
| FAQ item about placeholder number | **BLOCKER** | Remove before launch — exposes in-progress status to real visitors |
| Footer "Placeholder site for review" | **Remove pre-launch** | Replace with standard copyright + pricing disclaimer |

**Global find/replace before launch:** `60000000000` → real number  
**Centralisation target:** single `<script>const WA_NUMBER = "60XXXXXXXXX";</script>` in `<head>` or top of body; build all `wa.me` links dynamically from this.

---

## 9. Section Order (final)

1. Header (sticky)
2. Hero
3. Trust Strip
4. About Lim (with avatar slot)
5. Model Grid (with category filter tabs)
6. Why Lim (replaces placeholder testimonials)
7. Enquiry Process / Finance (with trailing CTA)
8. FAQ
9. Location / Coverage
10. Final CTA block (short reassurance + WhatsApp button)
11. Footer
12. Sticky WhatsApp Bar (fixed overlay)

---

## 10. Implementation Notes

- Static HTML/CSS/JS only. No build step. GitHub Pages compatible.
- All styles in a single `styles.css`. No preprocessor.
- WhatsApp links: build from `WA_NUMBER` const — never hardcode in markup.
- Car images in `design/assets/cars/` — reuse paths from existing implementation.
- Category filter: ~12 lines of vanilla JS; no library needed.
- Do not add new external dependencies beyond Inter font (already via system stack).
- `.nojekyll` must remain at repo root for GitHub Pages asset paths to work.
