# fofo-studio.github.io

Official website for [FOFO Studio](https://github.com/fofo-studio) — an independent
AI design and engineering studio focused on education and the arts.

**Live:** https://fofo-studio.github.io/

## Stack

- Static HTML, CSS, and vanilla JavaScript — no build step
- GitHub Pages, deployed with GitHub Actions
- English at `/`, Simplified Chinese at `/zh/`, Traditional Chinese at `/zh-tw/`
- Black-and-white identity with automatic light/dark logo switching

## Structure

```
site/
├── index.html          # English
├── zh/index.html       # 简体中文
├── zh-tw/index.html    # 繁體中文
├── 404.html
├── assets/
│   ├── style.css
│   ├── script.js
│   ├── mark-light.png  # dark ink, for light backgrounds
│   ├── mark-dark.png   # light ink, for dark backgrounds
│   ├── icon.png
│   ├── apple-touch-icon.png
│   └── og.png
├── robots.txt
└── sitemap.xml
```

## Local preview

```bash
python3 -m http.server 8787 --directory site
```

Then open http://localhost:8787.

## Deploy

Push to `main`. The workflow in `.github/workflows/deploy.yml` uploads `site/` and
publishes it to GitHub Pages.

First-time setup (already done for this repository):

```bash
gh api -X POST /repos/fofo-studio/fofo-studio.github.io/pages \
  -f build_type=workflow
```

## Notes

GitHub Pages is a good fit for an organization profile, open-source project, or
studio showcase. If this site becomes the primary commercial site for lead
generation, consider moving it to Cloudflare with a custom domain.