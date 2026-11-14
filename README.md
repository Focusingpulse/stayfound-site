# stayfound-site

Source for **stayfoundoptimized.com**: the Stayfound Optimized website.

Static HTML. Served by GitHub Pages from the `main` branch root.

## Files

| File | Purpose |
|---|---|
| `index.html` | The homepage with the entity, audit, answer-receipt, method, offer, and fit narrative. |
| `audit/` | The Public Record Audit detail page. |
| `how-it-works/` | The step-by-step process page. |
| `method/` | The public method and evidence-label page. |
| `results/` | The permissioned proof and answer-receipt library draft. |
| `about/` | Chris's operator-story page. |
| `assets/draft-pages.css` | Shared CSS for the supporting draft pages. |
| `favicon.svg` | The cairn mark. Stack of irregular stones on pine. |
| `apple-touch-icon.png` | 180x180 home-screen icon, same mark. |
| `og.png` | 1200x630 social card, referenced by `og:image` and `twitter:image`. |
| `robots.txt` | Allows search and answer-engine crawlers. |
| `sitemap.xml` | Sitemap for the homepage and supporting draft pages. |
| `llms.txt` | Concise, human-checked context for AI systems and agents. |
| `CNAME` | Maps GitHub Pages to `stayfoundoptimized.com`. |
| `.nojekyll` | Disables Jekyll: ship the files exactly as written. |

## Deploy

Settings → Pages → Source: `main` / `(root)`.

DNS for the apex domain points at GitHub Pages' four A records plus the four AAAA records.
Do not enable a proxy in front of them until GitHub has issued the HTTPS certificate.

## Custom domain

`stayfoundoptimized.com` now resolves through IONOS to GitHub Pages. The one-line `CNAME`
file is present, and GitHub Pages has an approved certificate for the apex and `www` host.
The repository Pages setting still needs **Enforce HTTPS** enabled manually when convenient.

## Domain-absolute URLs

These are final values and are intentionally domain-absolute so the entity `@id`s remain stable.

- `<link rel="canonical">`
- `<meta property="og:url">` and `og:image` / `twitter:image`
- every `@id` in the JSON-LD graph
- `sitemap.xml` `<loc>` and the `Sitemap:` line in `robots.txt`

Relative references (`/favicon.svg`, `/apple-touch-icon.png`) work on both hosts, so the icons
are correct on the preview URL today and after the move.

## Editing

Edit `index.html`, commit, push. Pages rebuilds automatically.

**Schema parity is not optional:** the visible FAQ and the `FAQPage` `mainEntity` array must list
the same questions. If you add a `<details>` block, add the matching `Question` node, and vice versa.

**Copy rule:** no em dashes or en dashes in going-live copy (house rule, 2026-09-05). The only
dash-like glyph in the file is a U+2212 minus used as the open-accordion marker in CSS.
