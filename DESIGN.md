# DESIGN.md — Eesti Maakeskus

## Color strategy: Committed (the brand IS green)

Deep forest green carries the brand. The hero sits under a dark-green wash; the closing
CTA is fully green-drenched. Everything else breathes on white and a warm-neutral surface.
Sage is the single living accent (growth, nature). Neutrals are tinted toward the green hue.

| Token | Hex | Use |
| --- | --- | --- |
| `primary` | `#003E36` | Headings, primary buttons, dark sections, logo mark |
| `primary-hover` | `#00302A` | Pressed/hover on primary |
| `accent` | `#7A9B57` | Emphasis, hovers, section details, icon accents |
| `accent-hover` | `#6A8A49` | Pressed/hover on accent |
| `ink` | `#15241F` | Body text (green-tinted near-black, never #000) |
| `muted` | `#5C6B63` | Secondary text |
| `line` | `#E3E8E2` | Hairline borders / dividers (1px) |
| `surface` | `#F7F7F7` | Alternating section backgrounds |
| `canvas` | `#FFFFFF` | Primary background |

Built in `src/index.css` `@theme` (Tailwind v4). Use OKLCH-equivalent tints; never pure
black or pure white for text.

## Typography

Two grotesques, committed weight contrast. Premium and trustworthy, not editorial-serif.

- **Display:** `Bricolage Grotesque` (700/800) — big Estonian headlines, tight tracking.
- **Body / UI:** `Hanken Grotesk` (400/500/600/700) — warm, highly readable.
- Body measure capped ~65ch. Heading scale fluid via `clamp()`, ≥1.25 step ratio.

## Layout

- Editorial split hero: copy left, inquiry-form card right (form above the fold).
- Generous macro-whitespace (`py-24`+). Max content width ~1200px.
- Land types are image-led tiles, not identical icon cards. No 3-equal-card feature rows.
- `min-h-[100dvh]` for full-height, never `h-screen`.

## Motion

- Scroll reveals: fade + 16px rise, ~700ms, `cubic-bezier(0.16,1,0.3,1)`, once.
- Buttons: `scale(0.98)` on `:active`; transition `transform`/`opacity` only.
- Respect `prefers-reduced-motion` (drop translate, keep opacity).

## Components / conventions

- Icons: `lucide-react` (already the project's set — do not introduce a second library).
- Sticky nav: white + backdrop blur, hairline bottom border.
- Floating WhatsApp button (always visible) + mobile fixed bottom action bar.
- Grain overlay: fixed, `pointer-events-none`, very low opacity.

## Imagery

Curated Unsplash drone/landscape photography of Estonian-style farmland, forest, and land.
Verify every URL resolves before shipping; descriptive Estonian alt text.
