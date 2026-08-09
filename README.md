# SIMKO — Personal DevSecOps Website

Personal website and digital command center of Szymon Scherb (aka SIMKO), a DevSecOps engineer. Built as a static, dependency-free site with a hacker/terminal aesthetic (black + green).

## Features

- **Static & lightweight** — plain HTML + CSS, no frameworks, no build step, no JavaScript.
- **Hacker style** — monospace font, green-on-black, ASCII dividers, CRT scanline overlay, blinking terminal cursor.
- **Mobile readable** — responsive layout so the site stays readable on phones.
- **Individual project pages** — `projects.html` is a hub that links to one HTML file per project.

## Project structure

```
.
├── index.html                     # Home / hub page
├── resume.html                    # Resume (work experience, certificates, education)
├── projects.html                  # Projects overview — only links to project pages
├── contact.html                   # Contact form + GitHub link
├── style.css                      # Global stylesheet
├── img/                           # Images and the logo (logo.svg)
├── projects/                      # One HTML file per project
│   ├── kubernetes-hetzner-cluster.html
│   ├── ai-home-integration.html
│   └── smart-home-iot.html
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

## Adding a new project

1. **Create the project page** — copy any existing project page (e.g. `projects/smart-home-iot.html`) and replace the title, summary and details. Keep the same `<header>`/`<nav>`/`<footer>` so navigation stays consistent. Remember that files inside `projects/` use `../` prefixed relative paths (e.g. `../style.css`, `../index.html`).
2. **Link it in the hub** — add a `<li class="project-item">` entry in `projects.html`.
3. **Optional: link it on the home page** — add an entry to the "LATEST PROJECTS" list in `index.html`.

## Coding conventions

- Styling lives exclusively in `style.css`; do not add inline styles or `<style>` blocks.
- Use the existing utility classes: `.button`, `.row`, `.row.end`, `.project-list`, `.project-item`, `.project-card`, `.ascii-divider`.
- ASCII dividers are `<p class="ascii-divider">` elements, not `<div>`s.
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