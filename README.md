# rogersac.github.io

Static GitHub Pages site for `rogersac` that displays public repositories in a single landing page.

## Overview

- Built as a single static `index.html` file.
- Loads GitHub profile and repository data from the public GitHub REST API at runtime.
- Designed to be deployed with GitHub Pages.

## Features

- Responsive landing page for public repositories
- Live repository filtering by name, language, or description
- Profile summary pulled from GitHub
- Basic SEO setup:
  - `robots.txt`
  - `sitemap.xml`
  - canonical URL
  - Open Graph and Twitter metadata
  - Schema.org structured data
  - `llms.txt` and `llms-full.txt` for LLM-oriented discovery

## Search engine coverage

- Google, Bing, Yahoo, and DuckDuckGo all benefit from the standard crawl/indexing setup already present here: crawlable HTML, `robots.txt`, `sitemap.xml`, canonical metadata, and structured data.
- Yahoo Search documentation says it uses Yahoo's crawler (`Slurp`) and Bing's crawler, and that site owners can manage appearance with `robots.txt` and meta tags.
- DuckDuckGo says traditional links largely come from Bing, while it also uses its own crawler and other sources.
- LLM discoverability is handled with `/llms.txt` and `/llms-full.txt`. This is an emerging convention, not a formal web standard like `robots.txt`.
- Bing-specific ownership verification is not included yet because it requires a token-based meta tag or verification file from Bing Webmaster Tools.

## Local development

Because this is a static site, you can preview it with any simple HTTP server from the repository root.

Example:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

## Deployment

This repository is intended for GitHub Pages deployment at:

`https://rogersac.github.io/`

Google Search Console ownership verification is handled with the root-level file:

`/googleb402e994c33f8edf.html`

If the production domain changes, update:

- the canonical URL in `index.html`
- `robots.txt`
- `sitemap.xml`
- `llms.txt`
- `llms-full.txt`

## Maintenance notes

- If the site moves to a custom domain, update all `https://rogersac.github.io/` references in `index.html`, `robots.txt`, `sitemap.xml`, `llms.txt`, and `llms-full.txt`.
- When making meaningful site updates, refresh the `<lastmod>` date in `sitemap.xml`.
- If the GitHub username ever changes, update the `data-github-user` value in `index.html` and any hard-coded GitHub profile links.
- Recheck the page metadata after major content or branding changes so the title, description, and structured data stay accurate.
- Keep `/googleb402e994c33f8edf.html` in the site root so Google can continue verifying ownership in Search Console.
- Keep `/llms.txt` and `/llms-full.txt` aligned with the site's current purpose and key links if the site structure changes.
- Google Search Console for the verified site: <https://search.google.com/search-console?resource_id=https%3A%2F%2Frogersac.github.io%2F&after_verification_success=>

## Files

- `index.html`: site markup, styles, and client-side GitHub API logic
- `googleb402e994c33f8edf.html`: Google Search Console site ownership verification file
- `llms.txt`: compact LLM discovery file
- `llms-full.txt`: expanded plain-text summary for LLM consumption
- `robots.txt`: crawler directives
- `sitemap.xml`: sitemap for search engines
