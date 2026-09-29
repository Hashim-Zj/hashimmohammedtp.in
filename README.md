# hashimmohammedtp.in

> A personal developer portfolio — single-page static site, live on GitHub Pages.

A one-page portfolio for **Hashim Mohammed TP**, built as a static site with
HTML, CSS and a small amount of jQuery. Sections are Home, About, Skills,
Work, Education and Contact, all reachable from a sticky Bootstrap navbar via
in-page anchor links.

Published at <https://hashim-zj.github.io/hashimmohammedtp.in/>.

## Features

- **Single page, six sections** — `#home`, `#about`, `#skills`, `#work`,
  `#Education`, `#contact`.
- **Sticky responsive navbar** — Bootstrap collapse on mobile, dark-mode
  toggle, smooth-scroll anchor links.
- **Scroll-spy navigation** — the active nav link highlights as you scroll
  through sections.
- **ScrollReveal animations** — elements fade/slide in on scroll.
- **Skills section** — technology chips with proficiency bars.
- **Work section** — three project cards linking to the live clone sites in
  this account.
- **Education timeline** — 2018 to 2022 entries.
- **Working contact form** — posts to a Google Apps Script web app and shows
  an alert on success.

## Tech Stack

- **HTML5** — one `index.html` (333 lines).
- **CSS3** — one `styles.css` (729 lines), CSS custom properties for theming.
- **jQuery 3.5.1** — Google CDN, used for the contact form `$.ajax` call and
  Bootstrap 5's jQuery-free components.
- **Bootstrap 5.2.0** — jsDelivr CDN, with SRI `integrity` hashes.
- **Boxicons 2.0.5** and **Font Awesome** (kit) — icon CDNs.
- **ScrollReveal** — unpkg CDN.
- **Google Fonts** — `Roboto`, `Qwitcher Grypen`, plus a self-hosted
  `Sole Sans Extended` (`font/font.woff2`).

This is a CDN-heavy, no-build site. There is no bundler, no package manager
and no `node_modules`.

## Installation

There is nothing to install:

```bash
git clone https://github.com/Hashim-Zj/hashimmohammedtp.in.git
cd hashimmohammedtp.in
```

## Usage

Open `index.html` in any browser, or serve it locally:

```bash
python3 -m http.server 8000
# -> http://localhost:8000
```

An internet connection is required — the navbar, icons, fonts and animations
all come from CDNs.

## Project Structure

```text
hashimmohammedtp.in/
├── index.html        The entire site
├── styles.css        Theme, layout, all sections
├── js/
│   └── main.js       Mobile menu, scroll-spy, dark-mode toggle
├── img/              Profile, logo and work-card images
├── font/
│   └── font.woff2    Self-hosted "Sole Sans Extended"
└── favicon/
    └── favicon.ico
```

## Configuration

No build step and no environment variables. One thing is worth knowing:

- **Contact form endpoint.** The submit handler in `index.html` posts to a
  Google Apps Script web-app deployment URL hard-coded in the markup. If that
  Apps Script project is ever deleted, moved, or redeployed to a new version,
  the form will silently stop delivering mail and will report a generic
  "Something Error". The URL is intentionally not documented here.

## Development

There is no build step and no test suite. Edit `index.html`, `styles.css` or
`js/main.js` and reload the browser.

All local asset references are relative (`img/...`, `styles.css`, `js/main.js`,
`favicon/favicon.ico`, `font/font.woff2`), so the site works when served from
a subdirectory such as a GitHub Pages project path.

### Fixed on 29 September 2026

`index.html` previously loaded `assets/js/main.js`, but the file lives at
`js/main.js`. The script request 404'd, which silently killed the mobile menu
toggle, the scroll-spy nav highlighting and the ScrollReveal setup. The path
has been corrected.

## Credits

- **Bootstrap 5.2.0**, **jQuery 3.5.1**, **Boxicons 2.0.5**,
  **ScrollReveal** — loaded from public CDNs.
- **Font Awesome** — loaded via kit script.
- **Google Fonts** — Roboto, Qwitcher Grypen.
- The three Work cards link to static recreations of YouTube, GoDaddy and
  Sparkbox home pages that live in this same GitHub account.

## License

No license file is present. Add one before redistributing this code.
