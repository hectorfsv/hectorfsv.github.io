# hectorfsv.github.io

The front door for the domain root, and the only place icons can live for it.

Safari looks for a site's bookmark icon at the **domain root** — `/favicon.ico`, `/apple-touch-icon.png` — not inside a
project page's folder. Bookmarking `hectorfsv.github.io/lounge/` therefore fell back to a grey letter, however many
icons the Lounge itself declared. A user-site repository is the only way to serve files at that root on GitHub Pages.

- `index.html` redirects to [/lounge/](https://hectorfsv.github.io/lounge/).
- `favicon.ico` (48/32/16), `favicon-32.png`, `favicon-16.png`, `apple-touch-icon.png` — the Vader crop, cut by
  `projects/lounge/tools/build-icon.py`. Re-run that and copy the files here if the artwork ever changes.

The pages themselves live in their own repositories and are untouched: `hectorfsv/lounge`, `hectorfsv/render-rig`.
