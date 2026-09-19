# UniSource Resources

Markdown learning resources for [UniSource](https://unisource.vercel.app).

This repo is mounted as a git submodule at `src/content/resources/` in the
UniSource site. Every resource is an Astro content entry rendered as a static
page at `/resources/<category>/<slug>`. Adding a resource here makes it appear
on the site — no code changes required.

## Structure

Each resource is a Markdown file grouped by topic:

```
<category>/
  <resource-name>.md
```

Supported categories:

- `web-dev` — Web Development
- `mobile-dev` — Mobile Development
- `game-dev` — Game Development
- `programming` — Programming
- `data` — Data & Databases
- `study-guide` — Study Guide

## Frontmatter

Every resource needs YAML frontmatter:

| Field         | Type                         | Required | Notes                                        |
| ------------- | ---------------------------- | -------- | -------------------------------------------- |
| `title`       | string                       | yes      | Page title                                   |
| `description` | string                       | yes      | Short summary used in cards and search       |
| `category`    | string (enum above)          | yes      | Groups the resource and forms the URL        |
| `level`       | `beginner` / `intermediate` / `advanced` | yes | Filterable difficulty                  |
| `tags`        | string[]                     | no       | Used by the search (defaults to `[]`)        |
| `order`       | number                       | no       | Lower sorts first on the index (default 100) |
| `createdAt`   | date (YYYY-MM-DD)            | yes      | Shown on the page and used for RSS            |
| `author`      | string                       | no       | Defaults to `UniSource`                       |
| `links`       | `{ label, url }[]`           | no       | Call-to-action links in the page header       |
| `pdf`         | string                       | no       | Optional PDF URL (`/files/...` or Drive link) |

The body of the file is the resource content and is rendered with standard
Markdown (tables, lists, code blocks all supported).

## Example

```markdown
---
title: "My resource"
description: "One-line summary."
category: "web-dev"
level: "beginner"
tags: ["html", "css"]
order: 5
createdAt: 2026-09-10
links:
  - label: "Docs"
    url: "https://example.com"
---

Write the content here. It renders under the resource header.
```

## License

Your contributions here are published publicly on UniSource. By submitting a
PR you agree to publish the content under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).