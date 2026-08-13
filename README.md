# SIMKO — Personal DevSecOps Website

Personal website and digital command center of Szymon Scherb (aka SIMKO), a DevSecOps engineer. Built as a static, dependency-free site with a hacker/terminal aesthetic (black + green).

## Features

- **Static & lightweight** — plain HTML + CSS, no frameworks, no build step, no JavaScript.
- **Hacker style** — monospace font, green-on-black, ASCII dividers, CRT scanline overlay, blinking terminal cursor.
- **Mobile readable** — responsive layout so the site stays readable on phones.
- **Individual project pages** — `projects.html` is a hub that links to one HTML file per project. Shared projects are listed newest-first (ongoing projects on top) and each entry shows its date via an `<i>` label.
- **SEO / sharing ready** — each page has a meta description, Open Graph tags, an absolute `og:url` + `og:image` (to `img/simko-logo-og.jpg`), a `<link rel="canonical">`, and a `theme-color`.
- **Custom 404** — `404.html` with a geeky "SEGMENTATION FAULT" message.

## Project structure

```
.
├── index.html                     # Home / hub page
├── resume.html                    # Resume (work experience, certificates, education)
├── projects.html                  # Projects overview — only links to project pages
├── contact.html                   # Contact page — email reference + GitHub link
├── 404.html                       # Custom 404 page
├── robots.txt                     # Crawler rules (points to sitemap.xml)
├── sitemap.xml                    # Sitemap for the GitHub Pages site
├── style.css                      # Global stylesheet
├── img/                           # Images (logo.svg, simko-logo-og.jpg, simko-logo.png source)
├── projects/                      # One HTML file per project
│   ├── kubernetes-hetzner-cluster.html
│   ├── ai-home-integration.html
│   ├── smart-home-iot.html
│   └── bt-chatbot.html
└── README.md
```

## Running locally

No dependencies, no build step. Just serve the directory:

```bash
# Python
python3 -m http.server 8000

# or any static file server of your choice
```

Then open <http://localhost:8000> in your browser.

> **Note:** the site is published on GitHub Pages, so `sitemap.xml`, `robots.txt` and every `canonical`/`og:` URL point to the base URL `https://s-i-m-k-o.github.io/web-app/`. If you move the site to a custom domain, update that base URL everywhere and keep `og:image` pointing at an absolute URL.

## Adding a new project

1. **Create the project page** — copy any existing project page (e.g. `projects/smart-home-iot.html`) and replace the title, summary and details. Keep the same `<header>`/`<nav>`/`<footer>` so navigation stays consistent. Remember that files inside `projects/` use `../` prefixed relative paths (e.g. `../style.css`, `../index.html`).
2. **Link it in the hub** — add a `<li class="project-item">` entry in `projects.html`. Keep the list sorted **newest first** (ongoing projects at the top) and append the date as an `<i>` label, e.g. `<i>(JAN 2026 · RUNNING)</i>`.
3. **Optional: link it on the home page** — add an entry to the "LATEST PROJECTS" list in `index.html` in the same order.
4. **Add it to `sitemap.xml`** — add a `<url>` entry with `lastmod`, `changefreq` and `priority`.
5. **Add the project page to `projects/` listing** — make sure the `<h1>` in the content is the page title (one `<h1>` per page).

## Coding conventions

- Styling lives exclusively in `style.css`; do not add inline styles or `<style>` blocks.
- Use the existing utility classes: `.button`, `.row`, `.row.end`, `.project-list`, `.project-item`, `.project-card`, `.ascii-divider`, `.prompt`, `.ok`.
- **Exactly one `<h1>` per page** for the page title (usually the `.typewriter` intro heading). The site name in the header is a non-heading `<p class="site-title">` + `<p class="site-subtitle">`; use `<h2>`/`<h3>` for section/subsection headings.
- Mark the active page in the header nav with `class="active"` **and** `aria-current="page"` on the matching link.
- ASCII dividers are `<p class="ascii-divider">` elements, not `<div>`s.
- Each page head should carry `<link rel="canonical">`, `<meta name="theme-color" content="#000">`, a `description`, and matching `og:` tags (with absolute `og:url`/`og:image`).
- Keep text content in the tone of the site: short, technical, slightly geeky.
- All pages use `lang="en"`.

## Contributing

Contributions to this site are welcome. To contribute:

1. Fork the repository and create a dedicated branch.
2. Follow the coding conventions above.
3. Test locally (see "Running locally") at desktop and mobile widths.
4. Open a pull request with a clear description of the change.

Bug reports and feature requests can be raised via the issue tracker of this repository, or by getting in touch via the [contact page](contact.html) (`contact.html`), which also links my GitHub profile.

## License

&copy; 2026 SIMKO. All rights reserved.