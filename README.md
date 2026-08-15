# meta-suite — static site (Vercel-ready)

## Deploy
```
cd meta-suite-site
vercel --prod        # or: drag this folder into vercel.com/new
```
Any static host works (Netlify, GitHub Pages, S3, `python -m http.server`).

## Structure
- `index.html` — entry, redirects to `Portfolio Hub.dc.html`
- 20 page files + `support.js` (must stay siblings — pages fetch sibling `.dc.html` files at runtime)
- `vercel.json` — root rewrite to `index.html`

Serve over http(s), not `file://`.

## Mobile
All pages carry a mobile layer: fluid grids collapse to one column under 760px,
side padding drops to 18px, SVG diagrams and code blocks scale/scroll instead of
overflowing, and `overflow-x` is pinned so there is no horizontal drift.
Fonts load from the Google Fonts CDN; everything else is local.
