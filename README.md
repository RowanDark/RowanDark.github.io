# RowanDark.github.io

Site for [Rosec Cyber LLC](https://github.com/RowanDark) — penetration
testing and security assessment for small and mid-sized businesses, based in
Covington, Georgia.

**Live site:** https://rowandark.github.io

---

## Structure

```
RowanDark.github.io/
├── _config.yml            # Jekyll site config
├── _layouts/
│   └── default.html       # page shell, renders {{ content }}
├── _includes/
│   ├── head.html
│   ├── header.html        # brand lockup + nav
│   ├── footer.html
│   └── lightbox.html      # gallery lightbox markup + script (Work page only)
├── index.html              # home page
├── services.html           # /services/
├── methodology.html        # /methodology/
├── work.html                # /work/  — screenshots/output samples
├── tools.html               # /tools/ — open-source tool cards + snippets
├── about.html               # /about/
├── contact.html             # /contact/
├── assets/
│   ├── images/
│   │   ├── logo_final.jpg      # not rendered directly (portrait, letterboxes at small sizes)
│   │   └── logo_mark.png       # optional — square/transparent mark, 40px in the header
│   ├── css/
│   │   └── rosec.css
│   └── snippets/           # drop .sh / .txt snippets here
└── README.md
```

## Adding content

**Logo mark** — the header renders a text lockup ("Rosec Cyber LLC") by
default. To show a mark alongside it, add a square or transparent-background
image at `assets/images/logo_mark.png`; it renders at 40px. If the file is
absent, the header ships the text lockup alone — no letterboxed image.

**Nav** — the six nav links (Services · Methodology · Work · Tools · About ·
Contact) live in `_includes/header.html`, each pointing at a page with a
matching `permalink`. The current page gets `aria-current="page"` and a red
underline automatically via a `page.url` comparison — no JS involved.

**Snippets** — add raw files to `assets/snippets/`, then add a
`<div class="snippet-card">` block in the Snippets section of `tools.html`.

**Work / gallery** — add `<figure class="gallery-item">` entries to
`work.html`, pointing at images in `assets/images/`.

**Tool cards** — copy an existing `<article class="tool-card">` block in
`tools.html` and update the name, description, tags, and link.

## Deployment

GitHub Pages builds the `main` branch with Jekyll automatically. Push to
`main` — no custom build step required.

## License

For authorized security research, CTF, and educational use only.
