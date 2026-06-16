# UIUX Proposal — Toyota Sales Advisor Landing Page (Malaysia)

---

## 1. UIUX Brief

**Product:** Single-page landing site for Lim, a Toyota sales advisor serving Penang and surrounding areas in Malaysia.

**Goal:** Convert mobile visitors from WhatsApp, Facebook, Instagram, and TikTok referrals into WhatsApp enquiries. Not a full e-commerce or booking system — the sole conversion is one tap to WhatsApp.

**Audience:** Malaysia buyers (Penang focus) comparing Toyota models before contacting a dealer. Mixed digital literacy. High mobile dependency. Short attention span typical of social-referred traffic.

**Primary CTA:** WhatsApp Lim (single consistent action across entire page).

**Stack:** Static HTML/CSS/JS. GitHub Pages. No backend.

**Phase:** Design prototype complete. Content blockers remain. Not yet launch-ready.

---

## 2. UX Research Summary

No primary user research has been conducted. The following is inferred from the audience profile and Malaysia automotive market context.

**Assumed mental model of target user:**
- Has seen a Toyota ad or shared link via social
- Wants to know: "which model fits me and what will it cost?"
- Doesn't want to call — prefers WhatsApp
- Fears being pressured or given vague answers
- Needs reassurance that Lim is real, local, and responsive

**Key friction points to reduce:**
1. Generic sales copy ("find the right Toyota") is expected and therefore ignored
2. Visitors need a reason to prefer Lim over walking into a showroom
3. Price sensitivity is high; inability to show a real number is a trust killer if not handled well
4. Model choice is overwhelming without guidance

**What the current design gets right:**
- WhatsApp-first approach matches user preference
- 12-model grid gives breadth for comparison shoppers
- 4-step process (enquiry → discuss → quote → test drive) reduces uncertainty
- Sticky WhatsApp button is always accessible

**What the current design lacks:**
- No real identity signal for Lim (no photo, no credentials, no dealership name)
- Placeholder testimonials undermine the credibility they're meant to build
- Placeholder WhatsApp number means the site literally does not convert yet
- No model category filter — 12 cards in one flat grid is harder to scan on mobile
- No answer to "why Lim vs. walking into any Toyota showroom"

---

## 3. Sitemap + User Flow

### Current sitemap (single page, anchor-based)

```
/ (index.html)
├── #top       Hero
├── #about     About Lim
├── #models    Model grid
├── #finance   Enquiry process + financing
├──            Testimonials
├── #faq       FAQ
└──            Location / coverage
```

### Intended future expansion (not yet built)

```
/
/models/<model-slug>    Individual model detail pages
/promotions             Manual promo listing page
/about                  Full advisor profile page
/contact                Location / contact page
```

### Primary user flow (mobile, social-referred)

```
Landing via shared link
  → Hero (5-second impression check)
      → Scans value prop + CTA
          → [High intent] Taps sticky WhatsApp → CONVERT
          → [Browsing] Scrolls to model grid
              → Finds relevant model → taps model CTA → CONVERT
              → Still unsure → reads FAQ / process steps
                  → Taps sticky WhatsApp → CONVERT
```

### Drop-off risk points
- Hero: if value prop is too generic → bounce
- Model grid: if no model matches perceived need → bounce
- FAQ: if placeholder answer exposes site-in-progress status → trust loss

---

## 4. Wireframe Spec

Describes the intended layout for each section. The current `design/index.html` implements most of this; gaps are noted.

---

### Header (sticky, all viewports)
```
[ L  Lim  Toyota Sales Advisor Penang ]  [ Models | Finance | FAQ ]  [ WhatsApp Lim ]
```
- Mobile (<520px): hide nav and header button; rely on sticky CTA bar
- Brand mark: red square "L" avatar; replace with real logo if available

---

### Section 1 — Hero
```
[ Eyebrow: Toyota model enquiries in Penang         ]
[ H1: Find the right Toyota with clear guidance     ]
[ Lead: WhatsApp Lim for latest packages, financing ]
[ CTA button: Ask for latest Toyota package         ]
[ Note: response time / availability signal ←MISSING]

[ Right: hero card — car image + category tags + quote card ]
```
**Gap:** The `response-note` span currently shows a placeholder warning visible to end users. It should be replaced with a real response-time signal (e.g., "Usually replies within the hour") before launch.

---

### Section 2 — Trust Strip (4 columns)
```
[ Penang focused ]  [ WhatsApp first ]  [ Model guidance ]  [ Test drive ]
```
- Currently 2-col on mobile, 4-col on desktop. Correct.
- Icons would improve scannability but are absent — acceptable for this phase.

---

### Section 3 — About Lim
```
[ Eyebrow + H2: Hi, I'm Lim ]         [ Panel: what Lim helps with + checklist ]
```
**Gap:** No profile photo placeholder or slot. A circular avatar slot should be added above or beside the H2. Even a placeholder silhouette communicates where real content belongs.

---

### Section 4 — Model Grid
```
[ Eyebrow + H2: Choose from current Toyota model categories ]
[ 3-col grid (desktop) / 1-col (mobile): 12 model cards ]
  Each card: image + category badge + name + description + WhatsApp CTA link
```
**Gap:** No category filter tabs (Sedan / SUV / MPV / Pickup / EV). With 12 models in one flat list, mobile users must scroll through all cards to reach their category. A simple tab or anchor group would reduce friction significantly.

---

### Section 5 — Enquiry Process (Finance)
```
[ Eyebrow + H2: Get the latest package ]
[ 4 numbered steps stacked vertically  ]
[ (no CTA button in this section) ←GAP]
```
**Gap:** A WhatsApp CTA should appear at the bottom of this section. Users who read through the process steps are high-intent; the nearest CTA is the sticky bar.

---

### Section 6 — Testimonials
```
[ Eyebrow + H2: Clear answers before the booking ]
[ 2-col blockquote grid ]
```
**Gap:** Both quotes are flagged as placeholder. The section as implemented still renders them in a credibility position. Until real quotes are available, consider replacing this section with a "Why buyers work with Lim" reasons list, which can be honest without requiring real social proof.

---

### Section 7 — FAQ
```
[ Eyebrow + H2: Common questions ]
[ details/summary accordion: 5 questions ]
```
**Gap:** One FAQ item ("Is the WhatsApp number final?") is explicitly about the placeholder status and must be removed before launch. It is useful during review but damaging live.

---

### Section 8 — Location
```
[ Eyebrow + H2: Serving Toyota buyers around Penang ]
[ Placeholder branch address ←MUST REPLACE ]
[ WhatsApp CTA button ]
```

---

### Footer
```
[ © 2026 Lim Toyota Sales Advisor, Penang ]
[ Pricing disclaimer ]
```

---

### Sticky WhatsApp Bar (fixed, always visible)
```
[ WhatsApp Lim ]  ← green pill, bottom right (desktop) / full-width bottom (mobile)
```
- Correct implementation. Keep.
- Consider adding the WhatsApp icon (SVG) for faster recognition.

---

## 5. UI Direction + Design System Draft

### Design intent
Clean, professional, slightly premium. Toyota brand red used as primary accent. Dark hero card creates contrast anchor. Whitespace-heavy to avoid the "cluttered car ad" feel.

---

### Color tokens (from `styles.css`)

| Token        | Value                        | Usage                         |
|--------------|------------------------------|-------------------------------|
| `--red`      | `#d71920`                    | Primary CTA, badges, eyebrows |
| `--red-dark` | `#9f1016`                    | Hover states                  |
| `--ink`      | `#10131a`                    | Body text, headings           |
| `--muted`    | `#5d6675`                    | Secondary text, descriptions  |
| `--line`     | `#e6e8ee`                    | Borders, dividers             |
| `--soft`     | `#f6f7f9`                    | Section backgrounds           |
| `--white`    | `#ffffff`                    | Card backgrounds              |
| WhatsApp green | `#20b15a`                  | Sticky CTA only               |

---

### Typography

- Font: Inter (Google Fonts or system fallback via `ui-sans-serif`)
- H1: `clamp(38px, 8vw, 78px)` / `letter-spacing: -0.055em`
- H2: `clamp(29px, 5vw, 52px)` / `letter-spacing: -0.04em`
- H3: `22px` / `letter-spacing: -0.025em`
- Lead: `clamp(18px, 2vw, 22px)` / `color: var(--muted)`
- Eyebrow: `12px` / `uppercase` / `letter-spacing: 0.16em` / `color: var(--red)`
- Body: `16px` / `line-height: 1.6`

---

### Component patterns

**Button**
- Shape: full pill (`border-radius: 999px`)
- Min height: 50px (52px mobile for tap target)
- Primary: `--red` bg, white text
- Default: `--ink` bg, white text
- Hover: `translateY(-1px)` lift

**Card**
- Border radius: `28px` (model cards) / `24px` (default)
- Border: `1px solid var(--line)`
- Shadow: `0 14px 42px rgba(16,19,26,.075)`
- Background: white

**Model card specifics**
- Top image area: gradient bg (`--soft` palette) with drop-shadow on car image
- Category badge: `--red`, uppercase, bold, small
- CTA link: `--red`, bold, `margin-top: auto` to pin to card bottom

**Hero card (dark)**
- Background: dark gradient (`#202633 → #080a0f`) with red glow
- Inner glass panel: frosted effect with radial gradient
- Price card: white, bottom-anchored within dark card

---

### Spacing system
- Section padding: `clamp(54px, 8vw, 110px)` vertical, `clamp(18px, 5vw, 64px)` horizontal
- Max content width: `1180px`, centered
- Grid gap: `18px` (model), `28px` (two-col)

---

### What's missing from the design system
- No icon set defined (trust strip, FAQ, and steps sections lack icons)
- No loading/skeleton state for model images
- No defined focus/keyboard state beyond browser default
- No color-blind safe check on red-only category badges

---

## 6. UX Review Report

### What works

| Area | Notes |
|------|-------|
| Page flow | Section order (hero → trust → about → models → process → FAQ → location) follows a logical commitment ladder |
| Mobile layout | Responsive breakpoints at 760px, 520px, 380px cover common devices well |
| WhatsApp integration | Per-model pre-filled WhatsApp messages are a strong conversion mechanic |
| Hero card | Dark card with car image creates visual anchor without being garish |
| Process steps | 4-step numbered list clearly answers "what happens after I tap?" |
| Model breadth | 12 models cover the full Toyota Malaysia lineup |

### What needs fixing (pre-launch blockers)

| Issue | Severity | Fix |
|-------|----------|-----|
| Placeholder WhatsApp number `60000000000` in every CTA | Critical | Replace with real number |
| Placeholder testimonials rendered live | High | Replace with real quotes or swap section for "Why Lim" reasons list |
| Placeholder branch address | High | Replace with real dealership info |
| FAQ item about placeholder number | High | Remove before launch |
| `response-note` text in hero is a dev note, not user-facing copy | High | Replace with real response time signal |
| No advisor photo slot in About section | Medium | Add avatar slot; even silhouette placeholder is better |

### What needs improvement (UX debt)

| Issue | Severity | Recommendation |
|-------|----------|----------------|
| 12 model cards in one flat grid — no category filter | Medium | Add tab bar or anchor group: Sedan / SUV / MPV / Pickup / EV |
| No WhatsApp CTA at bottom of process steps section | Medium | Add CTA button after the 4 steps |
| No WhatsApp CTA after About section | Low | Add inline CTA before model grid |
| Trust strip lacks icons | Low | Add small SVG icons for faster parsing |
| Sticky WhatsApp bar lacks WhatsApp logo | Low | Add SVG icon for instant recognition |
| No "Why Lim vs. any dealer" section | Medium | Currently missing; mentioned in brief as "Why buy through Lim" |
| Model card link is plain text, not button-styled | Low | Raise tap target and visual weight |

---

## 7. Developer Handoff Spec

### File structure
```
design/
  index.html          Main prototype — reference for all section structure
  styles.css          All styles — single file, no preprocessor
  assets/cars/        12 local car PNG/JPG images
  DESIGN_SPEC.md      Prior design notes
uiux/
  UIUX_PROPOSAL.md    This document
```

### Content blockers (must resolve before launch)
All instances below use the token `60000000000` which must be replaced globally:

```html
<!-- Occurs in: -->
<!-- Header CTA -->
<a href="https://wa.me/60000000000?text=...">

<!-- Hero CTA -->
<a href="https://wa.me/60000000000?text=...">

<!-- 12 model card CTAs -->
<a href="https://wa.me/60000000000?text=...">

<!-- Finance section (implicit) -->

<!-- Location section -->
<a href="https://wa.me/60000000000?text=...">

<!-- Sticky WhatsApp bar -->
<a class="sticky-whatsapp" href="https://wa.me/60000000000?text=...">
```

**Recommendation:** Centralise the WhatsApp number in a single JS const at top of a `<script>` tag or a `config.js` file so it only needs to change in one place.

```js
const WA_NUMBER = "60XXXXXXXXX"; // replace before launch
const WA_BASE = `https://wa.me/${WA_NUMBER}?text=`;
```

### Sections to add before launch

**1. Category filter tabs above model grid**
```html
<div class="model-filter" role="tablist">
  <button data-filter="all">All</button>
  <button data-filter="sedan">Sedan</button>
  <button data-filter="suv">SUV</button>
  <button data-filter="mpv">MPV</button>
  <button data-filter="pickup">Pickup</button>
  <button data-filter="ev">EV</button>
</div>
```
Each `.model-card` needs a matching `data-category` attribute. 12 lines of vanilla JS handles show/hide.

**2. WhatsApp CTA after process steps**
```html
<a class="btn btn-primary" href="[wa-link]">Start your enquiry on WhatsApp</a>
```

**3. Advisor avatar slot in About section**
```html
<div class="advisor-avatar">
  <!-- Replace src with real photo -->
  <img src="assets/advisor-placeholder.jpg" alt="Lim, Toyota Sales Advisor Penang" />
</div>
```

**4. "Why Lim" section (replaces or supplements testimonials until real quotes available)**
```html
<section class="section why-lim">
  <h2>Why buyers in Penang contact Lim directly</h2>
  <!-- 3–4 reason cards: fast response, clear guidance, local follow-up, loan help -->
</section>
```

### Known CSS gaps to address
- `.model-card a` needs `padding: 10px 0; display: inline-block` for better mobile tap target
- Sticky bar should include WhatsApp SVG icon before label text
- `nav` is hidden below 760px; no hamburger menu — acceptable for this page length but should be documented
- Footer `padding-bottom: 96px` (mobile) exists to clear sticky bar — correct, keep

### Accessibility checklist
- [ ] All `<img>` have meaningful `alt` text (model cards: done; hero showcase: `aria-hidden` — correct)
- [ ] Sticky WhatsApp link needs visible focus outline (currently relies on browser default)
- [ ] `<details>/<summary>` FAQ is keyboard accessible by default — correct
- [ ] Color contrast: white text on `--red` (#d71920) — check passes at AA for large text; verify body-size instances
- [ ] `lang="en"` set on `<html>` — correct

### Deployment
- GitHub Pages, `gh-pages` branch, no build step required
- `.nojekyll` present — required for asset paths with underscores to work correctly
- No environment variables; all config is inline HTML

---

## 8. UIUX Quality Score: 27/50

| Dimension | Score | Max | Notes |
|-----------|-------|-----|-------|
| Information architecture | 4 | 5 | Good section order; anchor nav works; missing category grouping in model section |
| Visual design quality | 4 | 5 | Clean, professional; dark hero card is distinctive; minor polish gaps |
| Mobile experience | 4 | 5 | Breakpoints thorough; sticky CTA correct; model grid could use filter for 12-item scroll |
| Conversion design | 3 | 5 | CTAs present everywhere but placeholder number means 0 real conversions; missing CTA in process section |
| Content strategy | 2 | 5 | Copy is honest and avoids fake claims (good); but too generic and Lim has no real identity signal |
| Trust architecture | 1 | 5 | Placeholder testimonials + no advisor photo + no real dealership = trust score near zero at launch |
| Accessibility | 2 | 5 | Semantic HTML, ARIA labels on key elements; focus states and contrast not fully verified |
| UX research depth | 1 | 5 | Audience defined; no interviews, no analytics baseline, no competitor benchmarking |
| Developer handoff | 4 | 5 | Clear file structure; all blockers documented; WhatsApp centralisation not yet implemented |
| Launch readiness | 2 | 5 | Prototype is strong but 5 critical blockers must be resolved before public use |

**27/50 — Solid prototype foundation, blocked on content.**

The design system, layout, and conversion mechanics are well-constructed for the scope. The score is held back by the volume of placeholder content that would cause real trust damage if the site launched as-is. Once the WhatsApp number, advisor details, and testimonials are replaced with real content, this design could realistically score 38–42/50 with minor UX improvements.
