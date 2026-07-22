# LIT-74 — Accessibility & responsive QA (WCAG AA)

**Site root:** project `_default/` static tree  
**Date:** 2026-07-22  
**Owner:** Web Designer

## Automated / structural

| Check | Result |
|-------|--------|
| Skip link to `#main` on all pages | Pass |
| Single `h1` per page | Pass |
| Landmark header / main / footer | Pass |
| Primary nav `aria-current="page"` | Pass |
| Mobile nav toggle `aria-expanded` + Escape close | Pass |
| Focus-visible styles from design system | Pass |
| `prefers-reduced-motion` disables hero rise / tile motion | Pass |
| Images: cover + softproofs have alt (decorative hero `alt=""`) | Pass |
| Color: Night Teal on Mist Paper; Mist on Night Teal/Porch (AA body) | Pass (token lock) |
| Amber not used as small body text | Pass |

## Manual responsive

| Viewport | Notes |
|----------|-------|
| ~375px | Hamburger nav; hero stacks; book detail single column |
| ~768px | Nav may still toggle; feature split stacks under 820px |
| ≥1024px | Full primary nav + header CTA |

## Known v1 limits

- No live retailer link yet — “Coming soon” control is non-actionable (`aria-disabled`) until board provides URL.
- Softproof peeks are illustrative crops; full book remains print package on LIT-66.
- Privacy page is a stub (no analytics/forms in v1).

## Sign-off

Structural AA checklist complete for v1 pages. Recommend a human keyboard pass on the live URL after LIT-75 deploy.
