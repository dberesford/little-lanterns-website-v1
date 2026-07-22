# LIT-75 — Hosting & deploy notes (v1)

## Live URL (shareable)

**https://dberesford.github.io/little-lanterns-website-v1/**

GitHub Pages · HTTPS · all v1 routes verified 2026-07-22.

| Path | Status |
|------|--------|
| `/` Home | live |
| `/books/` | live |
| `/books/the-softest-glow/` | live |
| `/about/` | live |
| `/caregivers/` | live |
| `/privacy/` | live |
| `/our-story/` → About | alias page present |
| `/for-caregivers/` → Caregivers | alias page present |

Repo: https://github.com/dberesford/little-lanterns-website-v1  
Deploy pipeline: `.github/workflows/pages.yml` (push to `main` → Pages)

## What to serve

Static root = this project folder (`_default/`):

```
index.html
about/ books/ caregivers/ privacy/ our-story/ for-caregivers/
assets/ design-system/
netlify.toml  _redirects  wrangler.toml
```

No build step. No secrets. Do **not** publish retailer listings from an agent session.

## Local preview

```bash
cd <project-_default>
python3 -m http.server 4173 --bind 127.0.0.1
# open http://127.0.0.1:4173/
```

## Hosting choice (v1)

| Layer | Choice |
|-------|--------|
| Primary public host | **GitHub Pages** (workflow deploy) |
| Alternate drop configs | Netlify (`netlify.toml` + `_redirects`), Cloudflare Pages (`wrangler.toml`) |
| Custom domain `littlelanterns.*` | **Board** — DNS + Pages custom domain (or Netlify/CF) |

## Domain (board)

Canonical host for `littlelanterns.*` is a **board** decision. Alias folders already present:

- `/our-story/` → About
- `/for-caregivers/` → Caregivers

When ready: add custom domain in GitHub Pages settings (or migrate drop to Netlify/CF with same static root) and set apex/www canonical.

## Go-live checklist (human / board)

1. ✅ Static site published (GitHub Pages URL above)
2. ☐ Attach `littlelanterns.*` DNS (CNAME → `dberesford.github.io` or chosen host)
3. ☐ Confirm HTTPS + apex/www canonical
4. ☐ Paste retailer URL into Softest Glow CTA when listing exists
5. ☐ Smoke Home → Softest Glow → Caregivers path on the custom domain
