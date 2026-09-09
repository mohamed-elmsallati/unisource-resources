# Contributing a resource

Thanks for contributing! Resources live in this repo and are published to the
UniSource site automatically once merged.

## Adding a new resource

1. Find the folder for the topic — see the list of `category` values in the
   [README](README.md). Create the folder if it doesn't exist yet.
2. Create a Markdown file named with a short, kebab-case slug, e.g.
   `web-dev/learn-http.md`. The slug becomes the page URL:
   `/resources/web-dev/learn-http`.
3. Fill in the required frontmatter (`title`, `description`, `category`,
   `level`, `createdAt`) — copy the example in the README.
4. Write the content. Use tables, lists, and code snippets where they help.
5. Open a pull request against `main`.

## Checklist

- [ ] File is at `<category>/<kebab-case-slug>.md`
- [ ] Frontmatter passes the [schema](README.md#frontmatter) — categories and
      levels must match the exact enum values
- [ ] `createdAt` is a `YYYY-MM-DD` date
- [ ] Description is one or two sentences — it's used in cards and search
- [ ] Links use https and point to stable, well-known sources

## Editing in the UniSource site

If you also have the site checked out, the resources folder is a submodule
mounted at `src/content/resources`. After merging upstream changes, update it
from inside the site repo:

```sh
git submodule update --remote src/content/resources
```

Then verify locally with `pnpm build` and `pnpm dev` to preview your page.