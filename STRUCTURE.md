# Structure — Toyota Sales Representative Website (Malaysia)

## Current phase goal
Refine the existing single-page landing page into a stronger conversion-focused Toyota sales advisor website for Malaysia users.

## Route plan
### Current
- `/` — main landing page

### Future-friendly expansion
- `/models/<model-slug>` — individual model pages later
- `/promotions` — manual promo page later
- `/about` — advisor profile page later
- `/contact` — location / contact page later

## Recommended landing page structure (next pass)
1. **Hero**
   - clear Toyota Penang positioning
   - one-sentence value proposition
   - strong WhatsApp CTA
   - supporting trust note
   - hero visual using featured Toyota model or grouped lineup

2. **Trust strip**
   - Penang support
   - quotation help
   - financing guidance
   - test drive / booking assistance

3. **About Lim**
   - advisor introduction
   - what Lim helps with
   - why buyers contact Lim instead of waiting

4. **Model browsing section**
   - grouped or card-based current Toyota lineup
   - easy scan by category
   - direct WhatsApp CTA per model or category

5. **How the enquiry works**
   - WhatsApp → needs / model discussion → quotation / financing guidance → booking / test drive
   - reduce user uncertainty

6. **Why buy through Lim**
   - faster response
   - clearer guidance
   - local support
   - smoother follow-up

7. **Finance / quotation support**
   - explain what user can ask for
   - avoid fake exact promo data unless provided
   - keep wording flexible and accurate

8. **Social proof / trust section**
   - testimonial cards, delivery photos, or proof placeholders
   - if placeholders remain, structure should still feel honest and not overclaim

9. **FAQ**
   - model comparison
   - loan / documentation guidance
   - test drive
   - trade-in / booking
   - Penang coverage

10. **Location / coverage**
   - branch / dealership area
   - Penang service coverage
   - optional map CTA

11. **Final CTA**
   - short reassurance copy
   - WhatsApp button with strongest intent

12. **Footer**
   - disclaimer
   - quick anchors
   - lightweight contact / attribution info

## UX goals
- Users understand immediately that this is a Toyota advisor site for Penang enquiries
- WhatsApp CTA is visible at all important moments
- Model exploration feels simple, not cluttered
- Trust improves despite limited real-world assets
- Mobile users can act quickly without scrolling confusion

## Content/data model (static for now)
- Sales rep profile
  - name
  - role/title
  - phone / WhatsApp number
  - branch / dealership
  - service area
  - profile image

- Model items[]
  - name
  - category
  - short description
  - image
  - WhatsApp CTA text
  - WhatsApp prefilled message

- Trust items[]
  - short title
  - short description

- FAQ[]
  - question
  - answer

- Social proof items[]
  - quote or caption
  - customer name / area
  - image optional

## Implementation notes for development phase
- Keep static HTML/CSS/JS unless a clear reason appears to add tooling
- Preserve GitHub Pages compatibility
- Centralize WhatsApp number/message generation if possible to avoid placeholder misses
- Prefer sections/components that can later map cleanly to reusable partials or a simple data file

## Key content blockers before final public launch
- Real WhatsApp number
- Real branch / dealership details
- Real testimonials / proof assets
- Confirmed brand-safe image usage
