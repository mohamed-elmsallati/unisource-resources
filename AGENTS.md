# AGENTS.md — unisource-resources

Guidance for AI coding agents working in this repo. Follow these rules unless a
task explicitly overrides them.

## Purpose

This repo holds Markdown learning resources. Each file is published by the
UniSource site as a static page at `/resources/<category>/<slug>`. The site
loads only `<category>/*.md` files; anything else in this repo is documentation
and is ignored.

## Adding a resource

When asked to add or edit a resource:

1. Place one file per resource at `<category>/<kebab-slug>.md` (e.g.
   `web-dev/learn-http.md`). Create the category folder if it is missing.
2. Use valid frontmatter (see schema below). Copy `EXAMPLE.md` when a full
   example is helpful.
3. Write the body as plain Markdown: headings, lists, tables, code blocks.
4. Do not add `.md` files at the repo root for new resources — they are not
   published. Root-level files are reserved for docs (`README.md`,
   `CONTRIBUTING.md`, `EXAMPLE.md`, `AGENTS.md`).

## Required frontmatter schema

| Field         | Type                      | Rule                                   |
| ------------- | ------------------------- | -------------------------------------- |
| `title`       | string                    | Required                               |
| `description` | string                    | Required; one or two sentences         |
| `category`    | enum                      | `web-dev` \| `mobile-dev` \| `game-dev` \| `programming` \| `data` \| `study-guide` |
| `level`       | enum                      | `beginner` \| `intermediate` \| `advanced` |
| `tags`        | string[]                  | Optional                               |
| `order`       | number                    | Default 100 (lower sorts first)        |
| `createdAt`   | date (`YYYY-MM-DD`)       | Required                               |
| `author`      | string                    | Default `UniSource`                    |
| `links`       | `{ label, url }[]`        | Optional; `url` must be `https://`     |
| `pdf`         | string                    | Optional; omit if none                 |

## Hard rules

- The `official` tag is reserved for UniSource-maintained resources. Only add
  it when the user explicitly asks. Never add it to contributed resources.
- Filenames are kebab-case, lowercase, no spaces. The slug becomes the URL.
- One slug per category; never create a duplicate.
- Do not edit `README.md`, `CONTRIBUTING.md`, or `EXAMPLE.md` unless asked.
- Do not commit non-resource files (scratch notes, images served elsewhere)
  into a category folder.
- Description must summarize the resource and appear in search/cards.
- Avoid em dashes (`—`); use plain punctuation (commas, colons).
- Keep links to stable, well-known https sources.

## Verification

The frontmatter schema mirrors `src/content/config.ts` in the UniSource site.
The site's `pnpm build` validates every resource and fails on bad data. When
tasks require confirmation here, run:

```sh
git status --short
git diff
```

and only modify files if the task says so.