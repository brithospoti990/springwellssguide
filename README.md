# springwellssguide.com

Static affiliate site for SpringWell salt-based water softeners. Plain HTML/CSS — **no build step**. Deploys to Vercel from GitHub.

## Structure

```
/
├─ index.html              HOMEPAGE = the full ~3,000-word "SpringWell Water Softener Reviews"
│                          money article (Scott Murley byline → /about), with topic clusters below
├─ about.html              About / author (Scott Murley) / review process
├─ contact.html            Contact (real email + mailing address)
├─ affiliate-disclosure.html
├─ privacy.html            Privacy Policy
├─ terms.html              Terms of Use
├─ css/style.css           Shared styles (teal brand system)
├─ assets/logo.svg         Brand mark (also the SVG favicon)
├─ assets/logo-512.png     PNG logo (social/OG fallback)
├─ assets/scott-murley.png Author headshot
├─ favicon.ico             32/16px favicon (legacy browsers)
├─ apple-touch-icon.png    180px iOS home-screen icon
├─ robots.txt              Allows all; disallows /go/; points to sitemap
├─ sitemap.xml             6 canonical URLs
└─ vercel.json             Clean URLs + /go/ affiliate redirects + old-slug 301
```

The homepage **is** the money page: the root URL `https://springwellssguide.com/` carries the full
"SpringWell Water Softener Reviews" article so it ranks for the primary keyword. The old
`/springwell-water-softener-reviews` URL **301-redirects to `/`** (in `vercel.json`). In-article
anchor links (`/#sizing`, `/#cost`, `/#saltfree`, etc.) all live on the homepage.

## Affiliate links (cloaked) — all confirmed

CTAs point to `/go/springwell-*` paths, which `vercel.json` 302-redirects to SpringWell with `affid=40`:

| Cloaked path | Product | oid |
|---|---|---|
| `/go/springwell-softener` | Salt-based softener (money link) | 9 |
| `/go/springwell-cf` | Whole-house filter | 1 |
| `/go/springwell-combo` | Filter + salt softener combo | 10 |
| `/go/springwell-2in1` | 2-in-1 (MMV) combo | 21 |
| `/go/springwell-futuresoft` | FutureSoft salt-free | 2 |
| `/go/springwell-well` | ULTRA Well + salt combo | 22 |

All six `oid`s are now filled in `vercel.json`. On-page anchors use `rel="sponsored nofollow noopener" target="_blank"`. Coupon code referenced in CTAs: **SSGUIDE**.

To add a new product link later, follow the same convention: add a `/go/springwell-<slug>` redirect in
`vercel.json` pointing to the SpringWell product URL with `?oid=<N>&affid=40`.

## Deploy: GitHub → Vercel

1. Push this folder to a new GitHub repo:
   ```bash
   git init && git add . && git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<you>/springwellssguide.git
   git push -u origin main
   ```
2. Vercel: **Add New → Project → Import** the repo. Framework preset **Other** (no build command, output dir = root / leave default).
3. Deploy, then add domain `springwellssguide.com` under **Settings → Domains** and point DNS to Vercel.
4. In Google Search Console, submit `https://springwellssguide.com/sitemap.xml`.

## Before you go live — checklist

- [x] **Author:** Scott Murley, headshot at `assets/scott-murley.png`; byline links to `/about`.
- [x] **Footer details:** business name, mailing address (Bellefontaine, OH), and email `Scott@springwellssguide.com` now in every footer.
- [x] **Contact email:** real address set in `contact.html` (was a placeholder).
- [x] **Affiliate oids:** all six confirmed in `vercel.json`.
- [x] **Logo + favicon:** `logo.svg`, `favicon.ico`, `apple-touch-icon.png` created and wired into every page head.
- [x] **Legal pages:** `privacy.html` and `terms.html` added.
- [x] **robots.txt + sitemap.xml** added.
- [ ] **Coupon code:** confirm `SSGUIDE` is your live SpringWell code (or remove the coupon line in CTAs).
- [ ] **Legal review:** have `privacy.html` / `terms.html` reviewed for your jurisdiction.
- [ ] **Analytics:** add your analytics snippet when ready.
- [ ] **Expand:** build the cluster articles from the content strategy and add their `/go/` links as needed.
```
