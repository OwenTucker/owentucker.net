# owentucker.net

Personal site built with Jekyll. GitHub Pages builds it automatically on push, so there's no build step.

## Where things live

| To change…                   | Edit                                   |
|------------------------------|----------------------------------------|
| Photo                        | `assets/img/profile.jpg` (square works best) |
| Name / "MS @ Emory" / links  | `author:` block in `_config.yml`       |
| Home page intro text         | `index.html`                           |
| Header links                 | `nav:` / `nav_right:` in `_config.yml` |
| Blog posts                   | `_posts/YYYY-MM-DD-slug.md`            |
| T1D project pages            | `_resources/<name>.md` → `/t1d/<name>/` |
| Publications                 | `_data/publications.yml`, with PDFs in `assets/papers/` |

## Writing a blog post

Create `_posts/YYYY-MM-DD-short-title.md` (the date and title in the filename set the URL):

```
---
title: My post title
description: One line shown under the title in post lists.
---

Post body in Markdown.
```

The two `---` lines must be plain dashes at the very top of the file. Some
Markdown editors (Typora, Obsidian, etc.) turn them into `\---`; if that
happens, the title and description show up as body text.

## Adding a T1D project page

Copy `_resources/drrl.md` to a new file. The front matter holds these lists (datasets aren't listed per page; every page links to Glucose-ML, set under `datasets:` in `_config.yml`):

- `repos`: `name`, `url`, `language`, `description`
- `works` (shown as "Related work"): `title`, `authors`, `venue`, `year`, `url`, `note`

The Markdown body below the front matter is the long description. Set `order:` to control where it appears on `/t1d/`. Add `math: true` to use LaTeX.

## Local preview (optional)

Install Ruby (e.g. `winget install RubyInstallerTeam.RubyWithDevKit.3.3`), then:

```
bundle install
bundle exec jekyll serve
```
