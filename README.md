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

## Maintenance notes

- If the site moves to a custom domain, update all `https://rogersac.github.io/` references in `index.html`, `robots.txt`, and `sitemap.xml`.
- When making meaningful site updates, refresh the `<lastmod>` date in `sitemap.xml`.
- If the GitHub username ever changes, update the `data-github-user` value in `index.html` and any hard-coded GitHub profile links.
- Recheck the page metadata after major content or branding changes so the title, description, and structured data stay accurate.
- Keep `/googleb402e994c33f8edf.html` in the site root so Google can continue verifying ownership in Search Console.
- Google Search Console for the verified site: <https://search.google.com/search-console?resource_id=https%3A%2F%2Frogersac.github.io%2F&after_verification_success=>

## Files

- `index.html`: site markup, styles, and client-side GitHub API logic
- `googleb402e994c33f8edf.html`: Google Search Console site ownership verification file
- `robots.txt`: crawler directives
- `sitemap.xml`: sitemap for search engines
