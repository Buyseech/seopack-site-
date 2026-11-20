# SEOpack.net

One-page static sales site for SEOpack, a Buyseech SEO product. No build step: Cloudflare serves the files in `public/` as they are. Same setup as `Buyseech/buyseech-site`.

## Where things are

- `public/index.html`: the whole page (hero, numbers, the problem, what's inside, what you receive, "plan, not audit" band, who it's for, how it works, packs already shipped, team, pricing, FAQ, order form)
- `public/styles.css`: all styling. The top part is copied from buyseech.com so both sites look the same. SEOpack-only parts are at the bottom, prefixed `sp-`. The accent colour is `--accent` at the top.
- `public/site.js`: scroll-in animation (`.reveal`), order form handling, phone menu
- `public/privacy.html`: privacy & company info (BUYSEECH d.o.o.)
- `public/assets/`: photos and self-hosted fonts (Manrope body text, Anton headlines, Barlow Condensed labels; no Google Fonts requests)
- `public/404.html`, `robots.txt`, `sitemap.xml`, `_headers`, `favicon.svg`: standard site files
- `wrangler.jsonc`: tells Cloudflare to publish the `public/` folder

## Cloudflare settings

- Build command: none
- Output directory: `public`

## Order form

Sends to Web3Forms (same account as buyseech.com), which emails each order to igor@buyseech.com with the subject "New SEO Pack order from seopack.net".

## Still to do

- **Payment:** the form collects the order; add a Stripe (or similar) payment link if you want people to pay on the page
- **Google Analytics:** create a separate GA4 property for seopack.net and paste its snippet where the comment says, in `index.html` and `privacy.html`
- **Social sharing image** (1200 x 630); Igor's photo is used until then
