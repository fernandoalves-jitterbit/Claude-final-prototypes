# Claude final prototypes

Static hosting for interactive UX prototypes, served with GitHub Pages.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Landing page. Embeds the prototype in a full-height iframe with a title bar and a full-screen link. |
| `APIM_Import_Export_Prototype.html` | The self-contained prototype bundle (~14 MB, all assets inlined). |
| `.nojekyll` | Tells GitHub Pages to serve files as-is instead of running them through Jekyll. |

## Publishing

1. Commit all files to the `main` branch, at the repository root.
2. Repository **Settings → Pages**.
3. Under **Build and deployment**, set Source to *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. Wait for the first deploy (1–2 min), then open:

```
https://fernandoalves-jitterbit.github.io/Claude-final-prototypes/
```

The prototype is also reachable directly, without the wrapper:

```
https://fernandoalves-jitterbit.github.io/Claude-final-prototypes/APIM_Import_Export_Prototype.html
```

## Adding another prototype

Drop the new `.html` file at the root and copy `index.html` to a second wrapper (for
example `apim-v3.html`), changing the `<h1>` text and both references to the file name.
The wrapper has no build step and no dependencies.
