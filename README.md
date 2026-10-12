# Sound State Guide

A practical site about sound-based tools, brainwave entrainment, and the Dr. Jeffrey Thompson lineage.

## Pages

- `/` — homepage
- `/guide/` — core guide
- `/thompson-lineage/` — lineage page
- `/tools/` — tools and affiliate comparison
- `/about/` — about page

## Design direction

- calm, grounded, human tone
- subtle motion and reverse parallax accents
- emphasis on responsibility, clarity, and self-control
- warm neutral palette with soft blue-gray and muted green accents
- simple navigation and readable layout

## Deployment

GitHub Pages is configured to deploy from a branch.

## Schema model

The `Organization` and `Person` entities are **defined once on the homepage** and referenced by `@id` from every other page. Each page also carries a **short local block with the same `@id`**, because Google resolves structured data page by page, and a bare `@id` reference with no local definition gives that page nothing.

Canonical `@id`s (permanent, pick them once):
- `.../#organization` — Sound State Guide
- `.../#person` — the person behind the site

| Page | Nodes |
|---|---|
| Homepage | WebSite, Organization *(canonical)*, WebPage, Person *(canonical)* |
| Guide | WebPage, Article, Organization (short), Person (short) |
| Thompson lineage | WebPage, Article, Person (Dr. Thompson, a subject), Organization (Center for Neuroacoustic Research) |
| Tools | WebPage, ItemList, Organization (short), Person (short) |
| About | WebPage, AboutPage, Organization (short), Person (short) |

**Known gap — `sameAs` is not set.** The site declares no social profiles anywhere, so there is no honest value for it. Add `sameAs` to the Person and Organization blocks once real profiles exist (an author page on this site, a YouTube channel, or a LinkedIn profile). Do not invent or borrow them.

**Domain caveat.** Every `@id` is currently anchored to `focusingpulse.github.io/Sound-State-Guide/`, which is a platform domain, not one we own. `@id`s are permanent, so settle the domain before this markup is treated as final, or every reference has to be rewritten at once.

## Structure

```text
Sound-State-Guide/
├── index.html
├── guide/
│   └── index.html
├── thompson-lineage/
│   └── index.html
├── tools/
│   └── index.html
├── about/
│   └── index.html
├── assets/
│   ├── css/
│   │   └── styles.css
│   ├── img/
│   └── js/
└── robots.txt
```

## Paths — read before adding a link or an asset

**Every path in this site is relative, and it has to stay that way.**

It was not always. Every link and asset was written root-absolute (`/guide/`, `/assets/css/styles.css`)
while the site is served from the `/Sound-State-Guide/` subpath, so the stylesheet and all four nav
targets returned **404 on the live site** and the homepage rendered as unstyled HTML. Fixed 2026-10-12.

The rule that follows:

- On the homepage, paths are bare: `assets/css/styles.css`, `guide/`
- On a subpage, they go up one: `../assets/css/styles.css`, `../guide/`, `../about/`
- Never write a leading `/`. It works nowhere this site is hosted, and it will still be wrong on a
  custom domain unless the site sits at the root.

Check with `grep -rohE '(href|src)="/[^"]*"' --include=*.html .` — it should return nothing.

## Notes

- This site is educational, not medical.
- Keep claims cautious and human.
- Keep schema aligned with visible content.
- Keep the Thompson and Skye surfaces distinct.
- **Content rule, stated by Chris 2026-10-12: no claims. First-hand experience only.** The site shares what has actually been experienced; it does not promise outcomes.
