# Prime Theory Labs website

The site for **Prime Theory Labs LLC**, live at [primetheorylabs.com](https://primetheorylabs.com).

It is plain HTML and CSS with no build step. GitHub Pages publishes whatever is on the `main` branch, so every push goes live within a minute or two.

## What's here

```
index.html              Home page (hero, services, apps, approach, contact)
404.html                "Page not found" page (GitHub Pages uses it automatically)
templates/page.html     Starting point for new pages (not linked or indexed)
assets/css/site.css     All styles; brand tokens are at the top
assets/img/             Logos, favicons, link-preview image
assets/img/apps/        App icons for the Apps section
CNAME                   Custom domain for GitHub Pages (don't delete)
.nojekyll               Tells GitHub Pages to serve files as-is
robots.txt, sitemap.xml Search engine hints
```

## Preview locally

```bash
python3 -m http.server 8790
```

Then open http://localhost:8790. Use a local server rather than opening the file directly, because the pages use root paths like `/assets/...`.

## Common changes

**Add an app.** In `index.html`, find the `APP CARD` comment in the Apps section, copy the whole `<article class="card app-card">` block, and edit it. Put the icon (a square PNG, 256px or larger) in `assets/img/apps/`. The grid rearranges itself for any number of apps.

**Add a service.** In the Services section of `index.html`, copy the `Custom iOS apps` card or replace the dashed "More to come" placeholder. Remove `card-wide` from a card if you don't want it to span two columns.

**Turn on the contact email.** Once email works for the domain (for example Cloudflare Email Routing or Google Workspace), open `index.html`, find the Contact section, update the "coming soon" sentence, and uncomment the email button below it.

**Add a page.** Copy `templates/page.html` to a folder named after the page, for example `about/index.html`, which becomes primetheorylabs.com/about/. Follow the steps in the comment at the top of the template, including adding the link to the header and footer nav on every page and adding the URL to `sitemap.xml`.

The header and footer are copied into each page. That keeps the site simple with a handful of pages. If it grows past five or so, it's worth moving to a static site generator (GitHub Pages supports Jekyll natively) so the header and footer live in one file.

## Brand

Colors, type and spacing come from the Prime Theory Labs design system and are defined as CSS variables at the top of `assets/css/site.css`:

| Token | Value | Use |
| --- | --- | --- |
| `--brand-cobalt` | `#2A45C9` | Primary buttons, icon tile |
| `--brand-ink` | `#121A3A` | Dark backgrounds, text on light |
| `--brand-paper` | `#E9EEF8` | Light background |
| `--brand-gold` | `#F2B33D` | Accent on dark only, once per screen |

Type is Sora from Google Fonts: 600 for headings, 400 for body. The site follows the visitor's light or dark mode setting automatically.
