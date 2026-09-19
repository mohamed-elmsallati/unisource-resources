# Contributing a resource

Thanks for contributing! Resources live in this repo and are published to the
UniSource site automatically once merged.

## Adding a new resource

1. Find the folder for the topic — see the list of `category` values in the
   [README](README.md). Create the folder if it doesn't exist yet.
2. Copy [`EXAMPLE.md`](EXAMPLE.md) as your starting point — it shows every
   frontmatter field and Markdown pattern in one file.
3. Rename the copy to a short, kebab-case slug, e.g. `web-dev/learn-http.md`.
   The slug becomes the page URL: `/resources/web-dev/learn-http`.
4. Fill in the frontmatter (`title`, `description`, `category`, `level`,
   `createdAt`) and remove the `official` tag unless UniSource has asked you
   to mark it as an official resource.
5. Write the content. Use tables, lists, and code snippets where they help.
6. Open a pull request against `main`.

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