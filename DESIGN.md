# Richill Pest Control Design System

## Colour strategy

**Committed**: one saturated colour (Racing Red) plus tinted dark anchors (Night Bordeaux, Dark Coffee) carries the brand. Antique White is the cream baseline, never pure white. Light Coral is a decorative accent only.

| Token | Hex | Role |
|---|---|---|
| Racing Red | `#EE1C20` | Primary CTAs, key icons, brand sparks. Used at 100% on Antique White surfaces; never as body text on Night Bordeaux. |
| Night Bordeaux | `#4E0110` | H1 hero, footer, contact section. The brand anchor. |
| Dark Coffee | `#251605` | Body text on light surfaces. Story section background. |
| Antique White | `#FEEFDD` | Default page background. Warmer than pure white. |
| Light Coral | `#F8777B` | Accents only, dividers, hover halos. Never carries meaning. Never used for body text. |

### Combinations that work

- Antique White surface + Dark Coffee body + Night Bordeaux H1/H2. Default layout.
- Night Bordeaux surface + Antique White body + Racing Red CTAs. Hero, quote section, footer.
- Dark Coffee surface + Antique White body + Light Coral pull-quote. Story section only.

### Combinations to avoid

- Racing Red on Night Bordeaux for text. Reds clash. Use Antique White on Bordeaux instead.
- Light Coral on Antique White as body text. Contrast too soft.
- Pure white anywhere. The brand has a warm cream baseline; white looks alien beside it.

## Theme

Light cream baseline with deep red and bordeaux anchors. The scene: a Perth homeowner on their phone, mid-afternoon, just spotted a cockroach. They want the site to feel like a friend's recommendation, not an emergency alarm. Warm light cream with red and bordeaux accents matches.

## Typography

- **Display & headings:** Rufina (Google Fonts). Regular for H1 and H2. Italic for the wordmark and pull quotes.
- **Body & UI:** Average Sans (Google Fonts). Regular for paragraphs. Bold for buttons and labels.

Pair these two and only these two. A third typeface muddies the rhythm.

### Type scale (desktop)

| Use | Font | Size | Line height | Weight |
|---|---|---|---|---|
| H1 (hero) | Rufina | 56px | 1.15 | 400 |
| H2 (section) | Rufina | 40px | 1.2 | 400 |
| H3 | Rufina | 24px | 1.3 | 400 |
| Pull quote | Rufina italic | 28px | 1.4 | 400 |
| Body | Average Sans | 17px | 1.6 | 400 |
| Small | Average Sans | 14px | 1.5 | 400 |
| Button | Average Sans bold | 16px (uppercase, 0.04em tracking) | 1 | 700 |
| Nav | Average Sans | 15px | 1 | 400 |

Mobile under 768px: H1 36px, H2 28px, H3 22px, body 16px.

### Type rules

- Sentence case for H1, H2, H3. Avoid Title Case (reads American).
- All caps only on buttons and small section labels. Never on headlines.
- Don't track-out Rufina; it carries its own spacing.
- One H1 per page (hero).

## Geometry

- **Corner radius:** 8px on every surface. Buttons, cards, inputs, image containers. The previous mix of 8/12/16 was scattered; 8 is the only radius now.
- **Borders:** 1px Antique White or Dark Coffee at 10 to 15 percent opacity. No coloured side-stripe borders. No `border-left` accents.
- **Shadows:** very restrained. `0 6px 18px rgba(37, 22, 5, 0.06)` on hover only, never as a baseline elevation.

## Layout

- 12-column grid, 80px gutters, 1200px max content width on desktop.
- 4-column grid, 24px gutters on mobile.
- Section padding 120px top/bottom desktop, 64px mobile.
- Alternate Antique White and Night Bordeaux (or Dark Coffee) sections so the page reads like chapters.

## Components

### Buttons

- **Primary:** Racing Red fill, Antique White text, 8px radius, 14px vertical / 24px horizontal padding, Average Sans bold uppercase 16px, 0.04em tracking. Hover: shift to Night Bordeaux fill, subtle 2px Light Coral underline 4px offset.
- **Secondary on light:** outline only, 1.5px Racing Red border, Racing Red text. Hover fills to Racing Red.
- **Secondary on dark:** outline only, 1.5px Antique White border, Antique White text. Hover fills to Antique White, text flips to Night Bordeaux.

### Cards

- Antique White fill, no border by default. 8px radius. 24px internal padding.
- Hover only: 200ms shadow lift, no transform. (Movement on hover feels twitchy; shadow is enough.)
- Review cards may take a 1px Light Coral border for slight separation on dark surfaces.
- Never nest cards. Never use side-stripe accents.

### Forms

- Antique White input fill, Dark Coffee text, 1px Dark Coffee 10% border, 8px radius, 12/16px padding, Average Sans 16px.
- Focus state: 2px Racing Red border, no layout shift.
- Error state: Racing Red border + helper text below in Racing Red.
- Labels: Average Sans bold 14px Dark Coffee, sit above each field, never inside.

## Motion

Restrained. The brand isn't flashy.

- **GSAP** is the motion engine. Default ease `power3.out` (exponential ease out). No bounce, no elastic.
- **Scroll reveals:** stagger entry by 60ms across siblings, 24px translateY, 600ms duration. Run once, then unobserve.
- **Hover lifts:** shadow only, 200ms. No transform on cards.
- **Buttons:** 150ms colour transition on hover.
- **Sticky nav:** transparent over hero, fades to Antique White with a 1px Dark Coffee 5% shadow when scrolled past hero.
- **Accordion:** GSAP-driven height + opacity, 280ms `power3.out` open, 200ms `power3.in` close.
- **Hero ambient:** subtle canvas particle drift in Light Coral at 8% opacity. Restrained, slow (60s loop), respects `prefers-reduced-motion`.

### Bans

- No parallax. No autoplay video. No mouse trails. No flashing or strobing.
- Never animate CSS layout properties (top, left, width, height directly). Use transform and opacity only.
- Never use bounce or elastic eases. Never animate longer than 800ms.

## Iconography

Single family across the site: Material Symbols Outlined (regular weight). Free, covers everything we need including bug_report, pest_control, hive, policy, eco.

- Icon colour: Night Bordeaux on light surfaces, Light Coral on dark surfaces, Racing Red for emphasis only.
- Icon container: 48px circle for service cards (Racing Red fill on light, Antique White at 10% opacity on dark). No 64px containers; they dominate.

## Imagery direction

- Hero photo: Mike on a real Perth front yard, ute visible, warm afternoon light. Until that's shot, use a Night Bordeaux to Dark Coffee gradient placeholder with a centred icon and caption.
- Story section: heritage photo if available, otherwise a present-day photo of Mike beside the ute.
- For pest illustrations, stylised line marks in Racing Red, not photographs.
- Reviews use initials in Antique White on Light Coral circles, not Google avatars.
- Service area uses a stylised SVG of Perth metro, not Google Maps.

## Accessibility

- All text and background combinations must hit 4.5:1 (WCAG AA) at body sizes.
- Visible focus states on every interactive element (2px Racing Red outline, 3px offset).
- Form labels visible above fields, never just placeholders.
- Skip-to-content link is the first focusable element.
- Semantic HTML: nav, main, section, article, footer. One H1, then H2 per section.
- Accordion uses `<details>` for no-JS resilience, GSAP only enhances.

## Copy rules

- Australian English. Organise, colour, defence, centre, behaviour, analyse.
- No em or en dashes anywhere. Use commas, colons, hyphens for ranges (1959 to 2026, not 1959 – 2026).
- Phone formatting: 0426 427 299. With spaces, not dashes or brackets.
- Mike, not Michael, in copy. Reviewers use both; Mike is on-brand.
- No "leading provider", "industry standard", "comprehensive solutions". Mike doesn't talk like that.
- Specifics over adjectives: "around $250" beats "affordable"; "same day or next day" beats "rapid response".
