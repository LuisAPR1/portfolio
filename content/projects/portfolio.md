---
title: "Personal Portfolio"
description: "Personal portfolio website built with Hugo and deployed automatically on every push to main. Showcases projects, blog posts, and CV — the very site you're reading right now."
tech_stack:
  - "Hugo"
  - "Markdown"
  - "HTML"
  - "CSS"
live_url: "https://github.com/LuisAPR1/portfolio"
live_label: "View source on GitHub"
group: "Full-Stack & Web"
weight: 110
---

<div>

The site you're currently looking at. A static portfolio built with **Hugo** and a custom layout, deployed automatically on every push to `main`.

## What's in here

- **Project pages** — every public repo on [github.com/LuisAPR1](https://github.com/LuisAPR1) gets a card and a deep-dive page (this very one is meta-documenting itself).
- **Resume** — the same content as the LaTeX-built PDF, kept in Markdown so it's editable and search-engine friendly.
- **Blog** — short technical write-ups on whatever I'm building.
- **About / Contact** — pages for the human side and the get-in-touch side.

## Why Hugo

Hugo gives me Markdown content + Go templates + zero runtime dependencies. The site builds in under a second locally and deploys as a pile of static files — no server, no database, no cold starts. It's the right shape for a personal site: edits are commits, content is text, and there's nothing that can break in production except DNS.

## Stack

- **Hugo** for content + templating, with custom layouts in `layouts/`.
- **Tailwind-style utility classes** plus a small custom CSS layer.
- **Markdown** for all content — including this page.
- **Static deploy** — runs anywhere that serves files (Netlify today, with a `*.is-a.dev` subdomain in flight).

## Why it matters

A personal site is a low-stakes excuse to keep your front-end / build-pipeline / writing muscles warm. It also doubles as the cleanest reference for "how does Luís actually structure a project" — every layout decision and content schema choice is on display.

</div>
