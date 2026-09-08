# Claude final prototypes

Interactive UX prototypes, hosted with GitHub Pages at
<https://fernandoalves-jitterbit.github.io/Claude-final-prototypes/>.

## Adding a prototype

Commit the `.html` file to the repository root. The index page lists whatever
`.html` files are in the root, so a new prototype appears on its own once the
deploy finishes. Nothing to edit.

The file name is the label shown in the list, so name it well:
`apim-import-export.html` appears as "apim-import-export".

## Admin view

Open the site with `?admin=1`:

```
https://fernandoalves-jitterbit.github.io/Claude-final-prototypes/?admin=1
```

That adds **New prototype** in the header and three actions per row — change
file, rename, delete. Each one opens the matching GitHub screen in a new tab,
where the commit happens under your own login. Without the flag the page is a
clean read-only list, which is what reviewers should get.

Rename takes three steps, because GitHub's web editor refuses files over 1 MB:
download, upload under the new name, delete the old copy. The rename panel
sequences them with the links ready.

**Copy link** works in either view and needs no login.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The list. Reads the repository contents from the public GitHub API at page load. Jitterbit logo inlined, no image request. |
| `view.html` | Generic wrapper. `view.html?p=file-name.html` shows that prototype in a full-height iframe under the site header. |
| `*.html` | The prototypes themselves — self-contained bundles with every asset inlined. |

Each prototype is also reachable without the wrapper, at
`https://fernandoalves-jitterbit.github.io/Claude-final-prototypes/file-name.html`.

## Notes

No build step, no dependencies. The list calls the GitHub API anonymously, which
is rate-limited to 60 requests per hour per IP address; past that the page shows
the direct URL pattern instead. The `p` parameter accepts only a plain `.html`
file name from this repository, so the wrapper cannot be pointed at another site.
