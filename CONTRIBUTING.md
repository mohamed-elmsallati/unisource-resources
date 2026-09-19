# Contributing a resource

Thanks for contributing! Resources live in this repo and are published to the
UniSource site automatically once merged.

## Adding a new resource

1. Find the folder for the topic. See the list of `category` values in the
   [README](README.md). Create the folder if it doesn't exist yet.
2. Copy [`EXAMPLE.md`](EXAMPLE.md) as your starting point. It shows every
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
- [ ] Frontmatter passes the [schema](README.md#frontmatter): categories and
      levels must match the exact enum values
- [ ] `createdAt` is a `YYYY-MM-DD` date
- [ ] Description is one or two sentences: it's used in cards and search
- [ ] Links use https and point to stable, well-known sources
- [ ] No em dashes or long dash characters anywhere in the file

## Fixing mistakes in your pull request

A pull request is **not final until it's merged**. Every push to the same branch
updates your PR automatically. No need to open a new one. Common fixes:

- I accidentally left the `official` tag → delete `"official"` from `tags`.
- My PR failed the build / looks broken → fix the frontmatter, commit, push.
- I want to change the content → edit the file, commit, push.

**If you're using the GitHub website:**

1. Open your pull request, then click the **Files changed** tab.
2. Click the pencil icon on a file to edit it directly.
3. Make your fix, scroll down, pick **Commit changes**, and choose
   **Commit directly to the `<your-branch>` branch**.

Your PR updates itself. Wait for the checks to finish.

**If you're using Git on your computer:**

```sh
git checkout your-branch     # switch to your PR branch
# edit the file in your editor
git add .
git commit -m "Fix: remove official tag, fix category"
git push                     # this updates your pull request
```

Not sure you want to keep a change? Make a **new commit** to fix it. Avoid
`git reset` or rewriting history unless you already know what you're doing.
Maintainers can always tidy up the commit history when they merge.

Still stuck? Leave a comment in the PR (e.g. "I don't know how to remove the
official tag"). Maintaining PRs is a normal part of contribution, and someone
will help.

## Linking download files (PDFs, bundles, 10+ files)

The site is fully static and only publishes Markdown text. Files (PDFs,
slides, images, zips, 10+ file packs) cannot be uploaded to the site, so host
them in the cloud and link to them.

Best options for beginner contributors:

- **Google Drive** (15 GB free) is the most beginner-friendly. Upload the
  files or a folder, press **Share**, then **Anyone with the link** → *Viewer*,
  and copy the link. Put that link in the `links` section or in the body:
  ```yaml
  links:
    - label: "Download study pack (10 files)"
      url: "https://drive.google.com/drive/folders/<folder-id>"
  ```
- **Mega** (20 GB free) is great for bigger packs (videos, zips) and handles
  many files in one shared folder. Same pattern: share folder → copy link. Note
  anonymous downloads can be throttled by Mega's transfer limit.
- **Dropbox** works too and can be set to "Anyone with the link".

Tips:

- 10+ files are easiest for learners to grab as a **single ZIP**. Zip the
  folder, upload the one file, and link it.
- For one readable document, a **PDF** works better than a link to a
  spreadsheet or editor file.
- Test the link in an incognito window to make sure it opens without an
  account.

## Editing in the UniSource site

If you also have the site checked out, the resources folder is a submodule
mounted at `src/content/resources`. After merging upstream changes, update it
from inside the site repo:

```sh
git submodule update --remote src/content/resources
```

Then verify locally with `pnpm build` and `pnpm dev` to preview your page.