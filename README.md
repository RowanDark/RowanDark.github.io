# RowanDark.github.io

Site for [Rosec Cyber LLC](https://github.com/RowanDark) — penetration
testing and security assessment for small and mid-sized businesses, based in
Covington, Georgia.

**Live site:** https://rowandark.github.io

---

## Structure

```
RowanDark.github.io/
├── _config.yml               # Jekyll site config (title, description, url, includes)
├── _layouts/
│   └── default.html          # page shell, renders {{ content }}
├── _includes/
│   ├── head.html              # <head> — title/description, OG/Twitter tags, favicons, fonts, canonical
│   ├── header.html            # brand lockup + nav
│   ├── footer.html            # footer links
│   └── lightbox.html          # gallery lightbox markup + focus-trapping script
├── index.html                  # home page — hero, services summary, engagement steps, JSON-LD schema
├── services.html                # /services/
├── methodology.html             # /methodology/
├── work.html                     # /work/  — sample report, case studies, public research
├── tools.html                     # /tools/ — open-source tool cards, snippets, gallery
├── about.html                      # /about/
├── contact.html                     # /contact/
├── 404.html                          # matches site design, links back to Services and Contact
├── sitemap.xml                        # generated from site.html_pages
├── robots.txt                          # allows everything, points at the sitemap
├── site.webmanifest                     # PWA manifest, icons
├── favicon.ico                           # multi-size favicon
├── apple-touch-icon.png                   # 180×180 touch icon
├── .well-known/
│   └── security.txt                        # RFC 9116 — contact + expiry date
├── assets/
│   ├── images/
│   │   ├── logo_final.jpg      # portrait master logo — not rendered directly (letterboxes at small sizes)
│   │   ├── logo_mark.png       # square mark, renders at 40px in the header
│   │   ├── og-card.png         # 1200×630 Open Graph / Twitter card share image
│   │   ├── favicon-192.png     # PWA icon
│   │   ├── favicon-512.png     # PWA icon
│   │   └── *_ss.png            # tool output screenshots used in the Tools gallery
│   ├── css/
│   │   ├── rosec.css           # design tokens + all page styles
│   │   └── fonts.css           # self-hosted @font-face declarations
│   ├── fonts/                  # self-hosted woff2 files (Archivo, Source Serif 4, JetBrains Mono) + OFL license text
│   └── snippets/                # reserved for downloadable raw snippet files (currently empty)
└── README.md
```

## Adding content

**Logo mark** — the header renders a text lockup ("Rosec Cyber LLC") by
default. `assets/images/logo_mark.png` (square, 512×512) is checked for at
build time and rendered at 40px alongside the text if present. If it's ever
removed, the header falls back to the text lockup alone — no letterboxed
image.

**Nav** — the six nav links (Services · Methodology · Work · Tools · About ·
Contact) live in `_includes/header.html`, each pointing at a page with a
matching `permalink`. The current page gets `aria-current="page"` and a red
underline automatically via a `page.url` comparison — no JS involved.

**Per-page SEO** — every page sets `title` and `description` in its front
matter; `_includes/head.html` uses those (falling back to `site.title` /
`site.description` when a page doesn't set them) to drive the `<title>`,
meta description, canonical link, and Open Graph/Twitter tags.

**Snippets** — the code blocks in the Snippets section of `tools.html` are
hand-authored `<div class="snippet-card">` blocks with inline `<pre>`
markup, not pulled from files. `assets/snippets/` exists for raw,
downloadable snippet files if that's ever needed, but nothing currently
reads from it — to add a new snippet card, copy an existing block in
`tools.html` and edit the command text directly.

**Work** — `work.html` holds the sample report (findings table; the PDF
download is not yet published), anonymized case studies, and public
research links. No client names, hostnames, IPs, or engagement-identifying
dates go on this page without the client's written permission — see the
standing note at the bottom of the page.

**Tool cards** — copy an existing `<article class="tool-card">` block in
`tools.html` and update the name, description, tags, and link.

**Gallery** — screenshots in the Tools gallery are shown at thumbnail size
in `.gallery-grid` and open full-size in the lightbox (`_includes/lightbox.html`)
on click or Enter/Space. The lightbox traps focus while open and restores it
to the trigger button on close.

## SEO & infrastructure

- `sitemap.xml` is generated from `site.html_pages`; a page can opt out by
  setting `sitemap: false` in its front matter (see `404.html`).
- `robots.txt` allows all crawlers and points at the sitemap.
- `.well-known/security.txt` follows [RFC 9116](https://www.rfc-editor.org/rfc/rfc9116);
  `_config.yml` explicitly `include`s `.well-known` since Jekyll excludes
  dot-directories by default. Keep its `Expires` date current.
- Fonts (Archivo, Source Serif 4, JetBrains Mono) are self-hosted from
  `assets/fonts/` — no request ever leaves the visitor's browser to a
  third-party font host.
- No analytics, trackers, or third-party JavaScript are loaded anywhere on
  the site.

## Deployment

GitHub Pages builds the `main` branch with Jekyll automatically. Push to
`main` — no custom build step required.

## License

For authorized security research, CTF, and educational use only. Fonts in
`assets/fonts/` are distributed under the SIL Open Font License 1.1 — see
the `OFL-*.txt` files in that directory.
