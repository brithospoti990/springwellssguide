# springwellssguide.com — complete static site

Reader-first affiliate guide to SpringWell salt-based water softeners. Static HTML/CSS/JS,
no build step. Deploy via GitHub → Vercel (or drag-drop to Vercel).

## What's in this package
- **50 content pages** (index.html = the SpringWell SS softener review + 49 cluster articles),
  each keyword-slug named and serving at a clean extensionless URL.
- **5 support pages**: about, contact, affiliate-disclosure, privacy, terms.
- `css/style.css`, `assets/` (logo, author photo), favicon + apple-touch-icon.
- `vercel.json` (clean URLs + affiliate `/go/` redirects), `sitemap.xml`, `robots.txt`.

## Deploy
1. Push the entire contents of this folder to the repo root of your GitHub repo.
2. Vercel auto-deploys. `cleanUrls: true` means `foo.html` serves at `/foo`.

## URLs
Every article URL is a keyword-based clean path, e.g.
`/how-long-does-water-softener-resin-last`, `/best-water-test-kits`, `/hard-water-problems`.
No `.html` in any internal link. All URLs are listed in `sitemap.xml`.

## Navigation
Site-wide mega-dropdown nav (in `css/style.css`, markup in each page's `<nav class="nav-links">`):
Reviews · Hard Water · Buying Guides · Filtration · Maintenance · Testing · About + a CTA.
Hover-to-open on desktop; hamburger + flat-expand on ≤1024px.

## ⚠️ VERIFY THESE 5 REDIRECT DESTINATIONS before relying on them
The affiliate `/go/` cloaks carry the correct `?oid=N&affid=40` tracking, but confirm each
destination PATH resolves on springwellwater.com (product URLs may differ). Update in `vercel.json`:
- `/go/test-kit`        → oid=8  (water test kit)  ← star CTA, used on ~25 pages
- `/go/springwell-iron` → oid=3  (well iron filter)
- `/go/springwell-ro`   → oid=11 (reverse osmosis)
- `/go/springwell-uv`   → oid=12 (UV system)
- `/go/springwell-csf`  → oid=4  (filter + salt-free combo)
The other 6 `/go/` redirects were already live/verified.

## Persona / contact
Scott Murley · Scott@springwellssguide.com · 1880 N County Road 9, Bellefontaine, OH 43311.
Coupon code: SSGUIDE.
