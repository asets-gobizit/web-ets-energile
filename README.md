# ets.gmnrconsultants.com

Joint-venture landing page: **Energile Markets × GMNR Consultants** — EU ETS / carbon-credit advisory for Spanish companies.

## What's in here

```
ets-energile/
├── index.html        # Single-file landing page (HTML + CSS + JS, no build)
├── favicon.svg       # Wind-turbine favicon
├── robots.txt        # SEO crawl directives
├── sitemap.xml       # SEO sitemap with hreflang variants
└── assets/           # (empty) drop real Energile + GMNR logos here
```

## Preview locally

Just open `index.html` in any browser, or:

```bash
cd "C:\Users\dansk\claude\Websites\ets-energile"
python -m http.server 8000
# → http://localhost:8000
```

The Spanish toggle works locally. Try `http://localhost:8000/?lang=es` for direct ES.

## Logos to swap in

In `index.html` find the two HTML comments marked `Replace with: <img src="assets/...">` (header) and drop the real assets into `assets/`. The footer text-only line can stay or be swapped for image logos too.

## Deploy to GitHub Pages (after Danny approves)

1. Create repo: `github.com/asets-gobizit/web-ets-energile` (public).
2. Push these files to `master` (or `main`).
3. In repo Settings → Pages: source = `master` branch, `/ (root)`.
4. In repo Settings → Pages → Custom domain: enter `ets.gmnrconsultants.com`. GitHub auto-creates a `CNAME` file.
5. **Cloudflare DNS** (gmnrconsultants.com lives on Cloudflare per Danny's setup):
   - Type: `CNAME`
   - Name: `ets`
   - Target: `asets-gobizit.github.io`
   - Proxy: **DNS only** (grey cloud — required for GitHub Pages SSL).
6. Wait ~5–15 min for DNS + GitHub Pages SSL. Test `https://ets.gmnrconsultants.com/`.

## SEO baked in

- `<title>` + meta description + canonical
- OpenGraph + Twitter Card
- JSON-LD `Organization` schema (helps Google understand the JV)
- `hreflang` EN + ES + x-default
- `sitemap.xml` (hreflang per URL)
- `robots.txt` allowing all + sitemap pointer
- Favicon

## Editing copy

All on-page strings live in the `I18N` object near the bottom of `index.html` (one EN block, one ES block). Edit there — the page picks them up via `data-i18n` attributes.
