# RowanDark.github.io

Portfolio and reference hub for [Rosec Cyber LLC](https://github.com/RowanDark) security tooling, code snippets, and project assets.

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
│   ├── header.html        # header + nav
│   ├── footer.html
│   └── lightbox.html      # gallery lightbox markup + script
├── index.html              # main portfolio page (layout: default)
├── assets/
│   ├── images/
│   │   └── logo_final.jpg
│   ├── css/
│   │   └── rosec.css
│   └── snippets/           # drop .sh / .txt snippets here
└── README.md
```

## Adding content

**Logo** — replace `assets/images/logo_final.jpg` with your preferred logo file and update the `<img src>` in `_includes/header.html`. A styled text fallback renders automatically if the image fails to load.

**Snippets** — add raw files to `assets/snippets/`, then add a `<div class="snippet-card">` block in the Snippets section of `index.html`.

**Gallery** — replace the `gallery-item` stub divs in `index.html` with `<img>` tags pointing to `assets/images/screenshots/`.

**Tool cards** — copy an existing `<article class="tool-card">` block and update the name, description, tags, and link.

## Deployment

GitHub Pages builds the `main` branch with Jekyll automatically. Push to `main` — no custom build step required.

## License

For authorized security research, CTF, and educational use only.
