---
title: Collections
---

# Auto-collections

Every root sub-folder in the source folder (default `src/`) which name doesn't start with an underscore (`_`) automaticaly becomes a collection.

# Permalinks

Any `permalink` property set directly in a content's Front Matter will not be overriden by the global one here after.

For all pages at once, you can decide with the `permalinkFolders` property in [the configuration file](../configuration/) how you want permalinks to behave:

- to preserve Eleventy's default behavior where every Markdown file becomes a folder and an `index.html` file, set it to`true` (default)
- to generate less folders, set it to `false`

Examples:

| source                                    | `permalinkFolders` = `true`                 | `permalinkFolders` = `false`          |
| ----------------------------------------- | ------------------------------------------- | ------------------------------------- |
| `index.md`                                | `index.html`                                | `index.html`                          |
| `about.md`                                | `about/index.html` &#x26A0;&#xFE0E;         | `about.html`                          |
| `about/index.md`                          | `about/index.html` &#x26A0;&#xFE0E;         | `about/index.html`                    |
| `about/other.md`                          | `about/other/index.html`                    | `about/other.html`                    |
| `articles/2020/04/first-article/index.md` | `articles/2020/04/first-article/index.html` | `articles/2020/04/first-article.html` |

::: warning
As you can see, you can't have both `/about.md` and `/about/index.md` with Eleventy default behavior (`permalinkFolders` = `true`), as they would try to create the same HTML file.
:::

# Layouts

Any `layout` property set directly in a content's Front Matter will not be overriden by the global ones here after.

If the content comes from a collection and a layout with the name of the collection exists, it is used. Else, the `pages` layout is used.

Examples with existing `articles` and `notes` layouts:

| source                                    | layout     |
| ----------------------------------------- | ---------- |
| `index.md`                                | `pages`    |
| `about.md`                                | `pages`    |
| `about/index.md`                          | `pages`    |
| `about/other.md`                          | `pages`    |
| `articles/index.md`                       | `articles` |
| `articles/2020/04/first-article/index.md` | `articles` |
| `articles/first-article.md`               | `articles` |
| `notes/2020/0001/first-note.md`           | `notes`    |

# Pagination

_WIP_

# Atom feeds

_WIP_
