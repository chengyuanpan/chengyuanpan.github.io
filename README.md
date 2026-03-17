## Chengyuan Pan's Tech Blog

This repository contains the **generated static site** for Chengyuan Pan’s Tech Blog, hosted with **GitHub Pages** and built using **Hexo 8** with the **Redefine** theme.

Because this repo holds the compiled output (HTML/CSS/JS) rather than the Hexo source, you typically **don’t edit posts or configuration here directly**. Instead, you:

- **Edit content and config** in your separate Hexo source project.
- **Generate** the static site there (e.g. `hexo generate` / `hexo g`).
- **Deploy or sync** the generated files into this repo so GitHub Pages can serve them.

### Repository Structure

Key files and directories:

- **`index.html`**: Main landing page of the blog.
- **`2026/`**: Year-based archive containing generated post pages (for example, the “Randomized Quicksort Implementation” article).
- **`about/`, `archives/`, `categories/`, `tags/`**: Generated standalone and listing pages.
- **`css/`, `js/`, `assets/`, `images/`, `fonts/`, `fontawesome/`, `webfonts/`**: Theme styles, scripts, and other static assets.
- **`search.json`**: Pre-generated search index used by the theme’s search component.
- **`404.html`**: Custom 404 page used by GitHub Pages.

### Local Preview

This is a purely static site, so you can preview it locally with any static file server. For example, using Python:

```bash
cd chengyuanpan.github.io
python -m http.server 4000
```

Then open `http://localhost:4000` in your browser.

### Editing Content (Hexo Source Repo)

To add or modify posts, categories, or tags:

1. **Go to your Hexo source project** (the one containing `_config.yml`, `source/`, and the Redefine theme).
2. Create or edit posts there (for example: `hexo new post "My New Article"`).
3. Run `hexo clean && hexo g` to regenerate the static site.
4. Copy or deploy the generated `public` output into this repository, then commit and push so GitHub Pages updates.

### Deployment Overview

A typical deployment workflow looks like:

1. Make changes in the Hexo source project.
2. Run `hexo clean && hexo g` to get fresh static output.
3. Sync the generated files into this repo (commonly the `main` or `gh-pages` branch of `chengyuanpan.github.io`).
4. Push to GitHub; GitHub Pages will serve the latest static files automatically.

This README documents that **this repository is the static output of a Hexo + Redefine blog**, not the authoring environment itself.

