# Luís Rosa — Portfolio

Personal portfolio website built with [Hugo](https://gohugo.io/).  
**Live site:** [https://luispar1.tech](https://luispar1.tech)

Deployed with GitHub + Vercel + Custom Domain.

## Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Local Development](#local-development)
- [Adding Content](#adding-content)
- [License](#license)

---

## Overview

A fast, minimal portfolio site showcasing projects and blog posts.  
Features automatic deployments on every push to `main` via GitHub Actions and Vercel, served on a custom domain.

---

## Project Structure

```
.
├── content/          # Markdown content (pages, posts, projects)
├── layouts/          # Hugo HTML templates
├── static/           # Static assets (CSS, JS, images, fonts, PDFs)
├── data/             # YAML data files (tech icons)
├── hugo.toml         # Hugo configuration
└── .github/workflows # GitHub Pages deploy pipeline
```

---

## Local Development

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.147.0+)

### Run locally

```bash
hugo server
```

Open [http://localhost:1313](http://localhost:1313) — edits reload automatically.

### Build for production

```bash
hugo --minify
```

Output goes to `public/`.

---

## Adding Content

### New project

```bash
hugo new projects/my-project.md
```

Then edit the frontmatter (`title`, `description`, `tech_stack`, etc.) and body.

### New blog post

```bash
hugo new posts/my-post.md
```

---

## License

© Luís Rosa. All rights reserved.
