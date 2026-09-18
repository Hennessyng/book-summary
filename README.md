# The Reading Room

## https://hennessyng.github.io/book-summary/

A small static library of visual book summaries. Open `index.html` in a browser,
or serve this directory locally:

```sh
python3 -m http.server 8000
```

Visit <http://localhost:8000>. There is no installation or build step. All landing
page artwork, styles, and search logic are included in `index.html`; no external
fonts, images, libraries, or API calls are required.

## Publish

For GitHub Pages, select the publishing branch and **/ (root)** in the repository's
**Settings > Pages**. `index.html` is the entry point. Links are relative, so the
library also works under a repository subpath. Keep the original
`how to know a person-summary.html` file at its current path.

## Add a Book

Uploading an HTML file does **not** automatically add it to the library.

1. Upload the standalone summary, preferably as `books/your-book-summary.html`.
2. In `index.html`, duplicate the entire `<article class="book-card" data-book ...>`
   element inside `<div class="catalog" id="catalog">`.
3. Change the title, author, category, description, language metadata, and both
   links to the uploaded file, for example `./books/your-book-summary.html`.
   Also update the reading link's `aria-label` and the `data-topics` keywords.
4. Adapt the decorative SVG cover's title, author, and original artwork. Keep its
   `aria-hidden="true"` wrapper; the accessible book information is outside it.
   Use the palette in `DESIGN.md`, and avoid duplicate SVG IDs if adding gradients.
5. Update the initial text of `#result-count` (for example, `2 books on the shelf`)
   so the count remains accurate without JavaScript. JavaScript calculates it
   automatically when enabled.
6. Open the page, search for the title and author, and follow **both** book links.

Use URL-encoded spaces (`%20`) in links when a filename contains spaces. Escape
HTML-sensitive characters in text and attributes (`&amp;`, `&lt;`, `&quot;`).

## Behavior and Design

- Every book is ordinary HTML and remains readable and linked without JavaScript.
- Search appears only after initialization and matches title, author, description,
  category, language, and `data-topics`. Multiple words must all match; case and
  surrounding whitespace do not matter.
- An empty search result includes a clear button and a live result count.
- Keyboard focus is visible, and system reduced-motion preferences disable motion.
- `DESIGN.md` documents the palette, type, layout, components, and motion contract.
- Book-cover artwork is an original visual interpretation, not publisher cover art.

The existing summary is maintained independently; adding a catalog entry does
not require modifying it.
