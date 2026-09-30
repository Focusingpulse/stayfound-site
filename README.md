# stayfound-site

Source for **stayfoundoptimized.com** — the Stayfound Optimized website.

Static HTML. Served by GitHub Pages from the `main` branch root.

## Files

| File | Purpose |
|---|---|
| `index.html` | The site. One self-contained page with a full JSON-LD `@graph`. |
| `robots.txt` | Explicitly allows AI crawlers (GPTBot, ClaudeBot, PerplexityBot, Applebot, Bingbot). |
| `sitemap.xml` | Single-URL sitemap. |
| `CNAME` | Tells GitHub Pages to serve on `stayfoundoptimized.com`. |
| `.nojekyll` | Disables Jekyll — ship the files exactly as written. |

## Deploy

Settings → Pages → Source: `main` / `(root)`. Custom domain is read from the `CNAME` file.

DNS for the apex domain points at GitHub Pages' four A records plus the four AAAA records.
Do not enable a proxy in front of them until GitHub has issued the HTTPS certificate.

## Editing

Edit `index.html`, commit, push. Pages rebuilds automatically.
