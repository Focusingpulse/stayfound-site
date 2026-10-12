# stayfound-site

Source for **stayfoundoptimized.com** — the Stayfound Optimized website.

Static HTML. Served by GitHub Pages from the `main` branch root.

## Files

| File | Purpose |
|---|---|
| `index.html` | The site. One self-contained page with a full JSON-LD `@graph`. |
| `favicon.svg` | The cairn mark. Stack of irregular stones on pine. |
| `apple-touch-icon.png` | 180x180 home-screen icon, same mark. |
| `og.png` | 1200x630 social card, referenced by `og:image` and `twitter:image`. |
| `robots.txt` | Explicitly allows AI crawlers (GPTBot, ClaudeBot, PerplexityBot, Applebot, Bingbot). |
| `sitemap.xml` | Single-URL sitemap. |
| `.nojekyll` | Disables Jekyll — ship the files exactly as written. |

## Deploy

Settings → Pages → Source: `main` / `(root)`.

DNS for the apex domain points at GitHub Pages' four A records plus the four AAAA records.
Do not enable a proxy in front of them until GitHub has issued the HTTPS certificate.

## ⚠ The `CNAME` file is deliberately absent

It was removed in `d578554` (2026-10-03). With Pages enabled **and** a `CNAME` naming a domain
that does not resolve, GitHub serves the site on the dead domain and redirects the working
`github.io` URL to it. **Do not add it back until `stayfoundoptimized.com` actually resolves**
(its Route 53 hosted zone is gone; see `stayfound-vault/site/DOMAIN-STATUS.md`).

The value to restore when the time comes is one line: `stayfoundoptimized.com`

## Domain-absolute URLs pending the domain move

These are correct final values, and they are inert until `stayfoundoptimized.com` resolves.
They are intentionally left domain-absolute so the entity `@id`s survive the move.

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
