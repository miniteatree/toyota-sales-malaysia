# Design Spec — Toyota Vios Penang Landing Page

## Visual direction
Modern, trustworthy automotive landing page for Lim, a Toyota sales advisor in Penang. The page is mobile-first, direct, and conversion-focused with repeated WhatsApp calls-to-action.

## Palette
- Toyota red: `#d71920`
- Deep ink: `#10131a`
- Muted text: `#5d6675`
- Soft background: `#f6f7f9`
- Border line: `#e6e8ee`
- WhatsApp green: `#20b15a`

## Typography
System sans-serif stack using Inter-compatible metrics. Headings use tight line-height and negative letter spacing for a premium sales-page feel. Body text stays readable at 16-18px.

## Spacing scale
- Small: 12-18px
- Card padding: 20-28px
- Section padding: 56-110px responsive clamp
- Max content width: 1180px
- Border radius: 18-34px depending component size

## Layout / grid
- Single-page responsive layout
- Mobile: one-column vertical flow
- Tablet/desktop: two-column hero, advisor, finance, and location sections
- Feature cards use 1 column on mobile, 3 columns on desktop
- Trust strip uses 2 columns on mobile, 4 columns on desktop

## Reusable components
- Sticky translucent header
- Brand mark
- Pill CTA buttons
- Hero card with car placeholder visual
- Trust strip items
- White rounded panels
- Feature cards
- Step list
- FAQ details blocks
- Sticky WhatsApp CTA

## Responsive behavior
- Header navigation hides on mobile
- Header CTA hides on very small screens because sticky WhatsApp CTA remains visible
- Sticky WhatsApp CTA spans full width on mobile and becomes a compact floating pill on desktop
- Hero and content grids collapse to a single column below 760px

## Content / asset checklist before launch
- Replace placeholder WhatsApp number `60000000000`
- Add Lim’s actual dealership / branch name and address
- Add official or approved Toyota Vios imagery
- Add Lim’s profile photo if available
- Replace placeholder testimonials with real customer proof
- Confirm current promotion wording with official campaign terms
- Confirm disclaimer wording if dealership has required legal copy
