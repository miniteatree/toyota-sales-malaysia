# DESIGN_SPEC — Toyota Sales Advisor Landing Page (Design B)

**Version:** 1.0  
**Date:** 2026-06-16  
**Direction:** Premium dark automotive / cinematic showroom

---

## 1. Intent

Design B is the alternative to the current trust-first light design.

It should feel:
- more premium
- more cinematic
- more showroom-like
- higher contrast
- more editorial

It must still keep the same business job:
- Toyota model discovery
- direct WhatsApp conversion
- Penang-focused sales advisor trust
- mobile-first usability

This is not meant to be a generic luxury website cosplay. It still has to sell, not just brood dramatically in dark mode.

---

## 2. Visual Direction

### Core mood
- Deep black / charcoal backgrounds
- Brushed gold as accent color
- Warm off-white text instead of harsh pure white
- Large serif display headlines for premium feel
- Sharp buttons and tighter card corners
- Car visuals presented like showroom hero objects, not catalog thumbnails

### Contrast with Design A
Design A is:
- lighter
- more practical
- more approachable
- more advisor / trust-first

Design B is:
- darker
- more premium
- more visual-first
- more campaign / showroom-first

---

## 3. Color Tokens

| Token | Value | Usage |
|---|---|---|
| `--bg` | `#080809` | page background |
| `--bg-soft` | `#111214` | darker section transitions |
| `--panel` | `#121316` | cards / blocks |
| `--panel-2` | `#17191d` | richer panel variation |
| `--line` | `rgba(255,255,255,.10)` | strong borders |
| `--line-soft` | `rgba(255,255,255,.06)` | subtle borders |
| `--text` | `#f7f4ef` | primary text |
| `--muted` | `#b8b0a3` | secondary text |
| `--muted-2` | `#8b8378` | lighter captions |
| `--gold` | `#c9a84c` | primary accent |
| `--gold-dark` | `#a8862d` | darker gold states |
| `--wa` | `#25d366` | WhatsApp CTA only |

Rule: gold is the main accent. Toyota red is intentionally not the dominant accent in this direction.

---

## 4. Typography

### Heading system
- **Display / H1 / H2:** `Playfair Display`
- **Body / UI / buttons / labels:** `Inter`

### Type behavior
| Role | Font | Weight | Notes |
|---|---|---|---|
| H1 | Playfair Display | 700 | dramatic, editorial |
| H2 | Playfair Display | 700 | premium section titles |
| H3 | Inter | 700 | strong and compact |
| Eyebrow | Inter | 800 | uppercase, tracked |
| Body | Inter | 400 / 500 | readable and modern |
| CTA | Inter | 800 | direct, clear |

### Tone guidance
- Headlines should feel premium but still understandable.
- Don’t write vague “luxury for luxury’s sake” nonsense.
- The typography should sell confidence, not perfume.

---

## 5. Layout Principles

### Global
- Mobile-first
- Full-width dark canvas
- Generous vertical rhythm
- Fewer but stronger cards
- Horizontal rail for model browsing instead of a dense grid

### Structural decisions
1. Hero is split into:
   - editorial copy block
   - dark cinematic stage with featured vehicle
2. Trust content uses bold segmented band cards
3. Model exploration uses horizontal scroll cards for a showroom shortlist feel
4. WhatsApp remains visible as a sticky CTA
5. Final CTA is strong, direct, and not diluted by too many extra links

---

## 6. Components

### Header
- Sticky
- Dark translucent background with blur
- Gold CTA on desktop
- Simplified on small mobile

### Hero stage
- Large dark panel
- Featured Vios image floating with dramatic shadow
- Supporting feature blocks at bottom
- Gold label chip + serif heading

### Buttons
- Primary: gold fill, dark text
- Secondary: transparent, light border
- Sticky WhatsApp: green, floating, always visible

### Model rail
- Horizontal scroll on mobile
- Dark cards with featured Vios first
- Small gold type chips for category
- CTA link inside each card

### Advisor card
- Dark panel with placeholder avatar
- Simple checklist rhythm
- Human trust without pretending we have final assets already

### FAQ
- Native `<details>` pattern
- Dark cards
- Light borders

---

## 7. Section Order

1. Hero
2. Trust band
3. Advisor intro
4. Toyota lineup rail
5. Process
6. Why this direction works
7. FAQ
8. Final CTA
9. Footer

This order keeps the page fast, visual, and still conversion-safe.

---

## 8. Mobile Notes

- Header nav collapses away on small screens
- Sticky WhatsApp remains the primary persistent action
- Hero stage scales down but keeps the featured car visible
- Model cards stay horizontally scrollable
- Buttons become full-width or near-full-width where needed

---

## 9. Placeholder Rules

Keep these as placeholders for now:
- WhatsApp number
- advisor photo
- final dealership / branch details
- any pricing / promo specifics not confirmed

This preview is about choosing a visual direction first.
Do not fake final business details just to make the comp look “finished”. That’s how people end up shipping polished nonsense.

---

## 10. Approval Lens

Choose Design B if the preferred direction is:
- more premium
- more cinematic
- more visually differentiated from generic advisor pages
- more like a branded campaign landing page

Do **not** choose Design B if the goal is maximum simplicity and warmth above all else — Design A is better for that.
