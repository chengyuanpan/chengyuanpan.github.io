## Chengyuan Pan's Personal Website

A personal website hosted on **GitHub Pages**, built with **[Hexo 8](https://hexo.io/)** and the **[Redefine](https://github.com/EvanNotFound/hexo-theme-redefine)** theme.

Live site: [chengyuanpan.github.io](https://chengyuanpan.github.io)

---

## Build Your Own GitHub Pages Blog — Step by Step

This guide walks you through creating your own personal website (like this one) from scratch. By the end you will have a live site at `https://<your-username>.github.io`.

### Prerequisites

- [Node.js](https://nodejs.org/) v18+ and npm
- [Git](https://git-scm.com/)
- A free [GitHub](https://github.com/) account

---

### Step 1 — Create Your GitHub Pages Repository

1. Log in to GitHub and click **New repository**.
2. Name it exactly `<your-username>.github.io` (replace `<your-username>` with your actual GitHub username).
3. Set the visibility to **Public**.
4. Leave it empty for now and click **Create repository**.

GitHub Pages will automatically serve whatever is on the `main` branch of this repository at `https://<your-username>.github.io`.

---

### Step 2 — Install Hexo

Hexo is a fast, Node.js-powered static site generator designed for blogs.

```bash
npm install -g hexo-cli
```

Create a new Hexo project in a local folder (this is your **source / authoring repo**, separate from the GitHub Pages repo):

```bash
hexo init my-blog
cd my-blog
npm install
```

---

### Step 3 — Install a Theme (Redefine)

Install the Redefine theme via npm:

```bash
npm install hexo-theme-redefine@latest
```

Then open `_config.yml` in your project root and set:

```yaml
theme: redefine
```

Create a theme config file by copying the default one:

```bash
cp node_modules/hexo-theme-redefine/_config.yml _config.redefine.yml
```

Edit `_config.redefine.yml` to personalise the site name, avatar, social links, navigation, and more. The [Redefine docs](https://redefine-docs.ohevan.com/) cover every option in detail.

---

### Step 4 — Configure Your Site

Open `_config.yml` and fill in the basic details:

```yaml
title:       Your Name's Personal Website
subtitle:    A short tagline about you
description: A short tagline about you
author:      Your Name
language:    en
timezone:    'America/New_York'   # your timezone

url: https://<your-username>.github.io
```

For deployment, add the following block at the bottom:

```yaml
deploy:
  type: git
  repo: https://github.com/<your-username>/<your-username>.github.io.git
  branch: main
```

Install the Git deployer plugin:

```bash
npm install hexo-deployer-git --save
```

---

### Step 5 — Write Your First Post

```bash
hexo new post "Hello World"
```

This creates `source/_posts/hello-world.md`. Open it and write in Markdown:

```markdown
---
title: Hello World
date: 2026-03-18
categories:
  - General
tags:
  - intro
---

Welcome to my blog! This is my first post.
```

---

### Step 6 — Preview Locally

```bash
hexo clean && hexo server
```

Open `http://localhost:4000` in your browser to preview the site before publishing.

---

### Step 7 — Generate & Deploy

When you are happy with your changes:

```bash
hexo clean && hexo generate && hexo deploy
```

- `hexo clean` — removes the previous build cache.
- `hexo generate` — compiles your posts and theme into static HTML/CSS/JS inside `public/`.
- `hexo deploy` — pushes the `public/` folder to the `main` branch of your GitHub Pages repo.

Within a minute or two, your site will be live at `https://<your-username>.github.io`.

---

### Step 8 — Keep Improving

Some popular next steps:

| Goal | How |
|---|---|
| Custom domain | Add a `CNAME` file to `source/` and configure DNS |
| Search | Enable the built-in search in `_config.redefine.yml` |
| Comments | Integrate Waline, Disqus, or Twikoo |
| Analytics | Add a Google Analytics or Umami tag |
| CI/CD | Use GitHub Actions to auto-deploy on every push |

---

## This Repository

This repo holds the **compiled static output** (HTML/CSS/JS) served by GitHub Pages — not the Hexo source files. The authoring workflow is:

1. Write posts and tweak config in the local Hexo source project.
2. Run `hexo clean && hexo generate` to produce fresh static files.
3. Run `hexo deploy` (or manually sync `public/`) into this repo and push.
4. GitHub Pages picks up the changes automatically.

### Repository Structure

| Path | Description |
|---|---|
| `index.html` | Blog landing page |
| `2026/` | Year-based archive of generated post pages |
| `about/`, `archives/`, `categories/`, `tags/` | Generated listing pages |
| `css/`, `js/`, `assets/`, `images/`, `fonts/` | Theme styles, scripts, and static assets |
| `search.json` | Pre-built search index |
| `404.html` | Custom 404 page |

### Local Preview of This Repo

Because this is purely static HTML, you can serve it with any static file server:

```bash
python -m http.server 4000
# then open http://localhost:4000
```

---

Questions or suggestions? Feel free to open an issue or reach out.
