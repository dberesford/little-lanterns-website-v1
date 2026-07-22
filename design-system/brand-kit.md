# Little Lanterns — Visual Design System & Brand Kit (Web)

**Issue:** [LIT-69](/LIT/issues/LIT-69)  
**Owner:** Web Designer  
**Visual system:** Porch Lantern Folklore  
**Aligned to:** [LIT-15](/LIT/issues/LIT-15) · [LIT-59](/LIT/issues/LIT-59) · [LIT-65](/LIT/issues/LIT-65)  
**Version:** 1.1  
**Date:** 2026-07-22  
**A11y:** LIT-74 

---

## 1. Intent

A lightweight, reusable web design system for the Little Lanterns marketing site (Home, Books, About, For Caregivers). Tone: **warm, cozy, storybook** — soft focal light, calm edges, honest emotion. Soft light is the hero; never scary dark, never “failed” glow.

**Signature:** Night Teal type on Mist Paper, with **Lantern Amber used as local glow / primary CTA only** — matching cover cue (Amber rim on glass, not wallpaper).

---

## 2. Files

| File | Role |
|------|------|
| `tokens.css` | CSS custom properties (color, type, space, motion) |
| `tokens.json` | Machine-readable token mirror + contrast rules |
| `components.css` | Buttons, book tiles, care panels, imagery, forms |
| `a11y.css` | Skip link, focus rings, nav chrome, reduced-motion, print (LIT-74) |
| `preview.html` | Operator-facing style board |

Import order for site pages:

```html
<link rel="stylesheet" href="/design-system/tokens.css" />
<link rel="stylesheet" href="/design-system/components.css" />
<link rel="stylesheet" href="/design-system/a11y.css" />
```

---

## 3. Color (locked AD palette)

| Role | Hex | Web use |
|------|-----|---------|
| Lantern Amber | `#E4A01A` | Accent CTA, focus ring, local lantern glow |
| Night Teal | `#163A3F` | Brand text, primary buttons, inverse bands |
| Mist Paper | `#EEF2EF` | Page ground |
| Ember Coral | `#D45A3A` | Stakes / rare alert — sparingly |
| Soft Sage | `#8FA88A` | Calm accents, Grandma-adjacent calm UI |
| Porch Blue | `#2C4A62` | Dusk bands, links |
| Firefly Lime | `#C6D96A` | Neighbor / “bright variety” chips (decorative) |
| Window Warm | `#F3D9A0` | Settle highlights, care panels |

### Avoid (from AD lock)

- Purple → indigo gradients  
- Cream + terracotta farmhouse stack  
- Pure-black crushed vignettes  
- Glitter sparkle swarms  
- Page-wide amber washes (glow stays **local** to lantern imagery)

### Contrast (WCAG AA)

**Do:** Night Teal on Mist Paper (10.9:1); Mist Paper on Night Teal / Porch Blue; Night Teal on Window Warm / Amber CTA; Porch Blue links; muted `#3d5a5e`; stakes text `--ll-color-stakes-text` (`#a63f28`).  
**Don’t:** Amber, Soft Sage, Firefly Lime, or raw Ember Coral as small body text on Mist Paper.

See `deliverables/LIT-74-a11y-responsive-qa.md` for the full QA checklist (LIT-74).

---

## 4. Typography

| Role | Face | Notes |
|------|------|-------|
| Display / brand | **Fraunces** | Soft optical sizing; storybook warmth without farmhouse cliché |
| Body / UI | **Source Sans 3** | Clear for caregivers; AA-friendly sizes |

Scale: `display-xl` → `caption` in `tokens.css`. Brand name uses `.ll-brand` and must remain a **hero-level** signal on marketing surfaces (not nav-only).

---

## 5. Spacing & layout

- 4px base scale (`--ll-space-1` … `--ll-space-9`)
- Section rhythm: `--ll-section-y`
- Content max: `68rem`; prose max: `38rem`
- Soft radii (`sm/md/lg`) — pills only for true chip/tag UI, not primary buttons

---

## 6. Components

### Buttons

| Class | Use |
|-------|-----|
| `.ll-btn--primary` | Default Night Teal action |
| `.ll-btn--glow` | Primary conversion (Shop / Meet the book) — Amber |
| `.ll-btn--quiet` | Secondary |
| `.ll-btn--on-dark` | Inverse / dusk bands |

### Interactive surfaces (not decorative cards)

- **`.ll-book-tile`** — Books browsing (cover + meta); hover lift; local glow under cover  
- **`.ll-care-panel`** — For Caregivers read-aloud tips / tools  

Decorative bordered “info cards” are out of scope for heroes.

### Imagery

- **`.ll-media-bleed`** — full-bleed story art (edge-to-edge)  
- **`.ll-media-frame--lantern-glow`** — soft halo **under** lantern region only  
- **`.ll-media-mat`** — Mist Paper mat for interior art excerpts  

Hero rule for landing pages: brand + one headline + one supporting line + one CTA group + one dominant full-bleed image. No overlay badges/chips on hero art.

---

## 7. Motion

- Ease: `--ll-ease-out`
- Durations: fast / med / slow  
- `prefers-reduced-motion` zeroes durations  
- Intentional motions for site build: soft hero fade-in, book-tile lift, amber CTA glow settle

---

## 8. Voice (web copy alignment)

- Warm, plain, caregiver-respectful  
- Soft light = shy / forced / true — never “failed”  
- Brand *Little Lanterns* first; title *The Softest Glow* second on Book 1 surfaces  

---

## 9. Handoffs

| Partner | Action |
|---------|--------|
| **Art Director** | Brand-alignment review of web token mapping vs Porch Lantern Folklore |
| Web Designer (LIT-70+) | Consume tokens on Home / Books / About / Caregivers |
| Editor / Marketing | Keep cover cue + refrain language consistent |

---

## Document control

| Field | Value |
|-------|-------|
| Version | 1.1 |
| Status | Ready for page builds (LIT-70–73); a11y foundation locked (LIT-74) |
| Supersedes | 1.0 |
