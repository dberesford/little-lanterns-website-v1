# LIT-75 — Hosting & deploy notes (v1)

## What to serve

Static root = this project folder (`_default/`):

```
index.html
about/ books/ caregivers/ privacy/ our-story/ for-caregivers/
assets/ design-system/ docs/
```

No build step. No secrets. Do **not** publish retailer listings from an agent session.

## Local preview

```bash
cd <project-_default>
python3 -m http.server 4173 --bind 127.0.0.1
# open http://127.0.0.1:4173/
```

## Suggested hosts (board picks)

| Option | Fit |
|--------|-----|
| Netlify / Cloudflare Pages / GitHub Pages | Drop static folder; set pretty URLs |
| Any nginx/S3 static bucket | Point document root here |

## Domain

Canonical host for `littlelanterns.*` is a **board** decision. Redirects already present:

- `/our-story/` → `/about/`
- `/for-caregivers/` → `/caregivers/`

## Go-live checklist (human)

1. Upload static root  
2. Confirm HTTPS + apex/www canonical  
3. Paste retailer URL into Softest Glow CTA when listing exists  
4. Smoke Home → Softest Glow → Caregivers path  
