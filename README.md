# RowanDark.github.io

Portfolio and reference hub for [Rosec Cyber LLC](https://github.com/RowanDark) security tooling, code snippets, and project assets.

**Live site:** https://rowandark.github.io

---

## Structure

```
RowanDark.github.io/
├── index.html            # main portfolio page
├── assets/
│   ├── images/
│   │   └── logo_final.jpg
│   ├── css/
│   │   └── style.css
│   └── snippets/         # drop .sh / .txt snippets here
└── README.md
```

## Adding content

**Logo** — replace `assets/images/logo_final.jpg` with your preferred logo file and update the `<img src>` in `index.html`. A styled text fallback renders automatically if the image fails to load.

**Snippets** — add raw files to `assets/snippets/`, then add a `<div class="snippet-card">` block in the Snippets section of `index.html`.

**Gallery** — replace the `gallery-item` stub divs in `index.html` with `<img>` tags pointing to `assets/images/screenshots/`.

**Tool cards** — copy an existing `<article class="tool-card">` block and update the name, description, tags, and link.

## Deployment

GitHub Pages serves the `main` branch root automatically. Push to `main` — no build step required.

## License

For authorized security research, CTF, and educational use only.
