---
# ─────────────────────────────────────────────────────────────────────
# UniSource resource template
# Copy this file into a category folder, e.g. web-dev/my-resource.md,
# rename it, and replace every value below. The page URL becomes
# /resources/<category>/<filename>.
# ─────────────────────────────────────────────────────────────────────

title: "Learn React hooks with one project"
description: "A short one- or two-sentence summary. It shows on cards, in search results, and in page meta."
category: "web-dev"
# One of: web-dev | mobile-dev | game-dev | programming | data | study-guide

level: "beginner"
# One of: beginner | intermediate | advanced

tags: ["official", "react", "hooks"]
# "official" marks a UniSource-maintained resource. Contributors can add
# topic tags like the ones here — they make the resource searchable.

order: 100
# Lower values sort first on the resources index. 100 is a safe default.

createdAt: 2026-01-01
# Use YYYY-MM-DD. Shown on the page and used in the RSS feed.

author: "UniSource"
# Optional. Defaults to "UniSource".

links:
  - label: "React docs"
    url: "https://react.dev"
# Optional call-to-action links shown in the page header.

# Optional: paste a matching "Download PDF" link here (omit if none).
# pdf: "/files/my-resource.pdf"
---

Write the body in plain Markdown. It renders under the resource header. Use
headings, lists, tables, and code blocks freely.

## A section title

Explain the concept step by step. Keep each section focused so a student can
follow it in one sitting.

- A bullet list
- Of the exact steps
- Or skills involved

> A tip, warning, or callout renders as a blockquote.

### A sub-section

Concrete examples beat theory. Show real code:

```js
function useCount() {
  const [count, setCount] = React.useState(0);
  return [count, setCount];
}
```

## Learning milestones

| Milestone | What you practice |
| --------- | ----------------- |
| First hook | Reading `useState` and `useEffect` |
| Custom hook | Extracting reusable logic |
| Deploy it | Shipping the final app |

## Closing notes

End with a short paragraph telling them what to build next, then link out.
Keep the resource evergreen: avoid version-specific jargon where you can.