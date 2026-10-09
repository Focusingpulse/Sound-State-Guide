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

- Homepage: WebSite, Organization, WebPage
- Guide: WebPage, Article
- Thompson lineage: WebPage, Article, Person, Organization
- Tools: WebPage, ItemList
- About: WebPage, AboutPage

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

## Notes

- This site is educational, not medical.
- Keep claims cautious and human.
- Keep schema aligned with visible content.
- Keep the Thompson and Skye surfaces distinct.
