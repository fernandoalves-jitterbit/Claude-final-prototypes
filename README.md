# Claude final prototypes

Static hosting for interactive UX prototypes, served with GitHub Pages at
<https://fernandoalves-jitterbit.github.io/Claude-final-prototypes/>.

## Adding a prototype

Commit the `.html` file to the repository root. Nothing else — the index page
lists whatever `.html` files are in the root, so a new prototype appears on its
own after the deploy finishes.

Give the file a name that reads well, because the name is the label shown in the
list: `apim-import-export.html` becomes "apim-import-export".

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Lists the prototypes. Reads the repository contents from the public GitHub API at page load. |
| `view.html` | Generic wrapper. `view.html?p=file-name.html` shows that prototype in a full-height iframe with a title bar. |
| `*.html` | The prototypes themselves — self-contained bundles with every asset inlined. |

Each prototype is also reachable without the wrapper, at
`https://fernandoalves-jitterbit.github.io/Claude-final-prototypes/file-name.html`.

## Notes

The index needs no build step and no dependencies. It calls the GitHub API
anonymously, which is rate-limited to 60 requests per hour per IP address; past
that the page explains the direct URL pattern instead of the list. The `p`
parameter accepts only a plain `.html` file name from this repository, so the
wrapper cannot be pointed at another site.
