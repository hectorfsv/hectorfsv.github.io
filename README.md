# hectorfsv.github.io

The front door for the domain root, and the only place icons can live for it.

Safari looks for a site's bookmark icon at the **domain root** — `/favicon.ico`, `/apple-touch-icon.png` — not inside a
project page's folder. Bookmarking `hectorfsv.github.io/lounge/` therefore fell back to a grey letter, however many
icons the Lounge itself declared. A user-site repository is the only way to serve files at that root on GitHub Pages.

- `index.html` redirects to [/lounge/](https://hectorfsv.github.io/lounge/).
- `favicon.ico` (48/32/16), `favicon-32.png`, `favicon-16.png`, `apple-touch-icon.png` — the Vader crop, cut by
  `projects/lounge/tools/build-icon.py`. Re-run that and copy the files here if the artwork ever changes.

The pages themselves live in their own repositories and are untouched: `hectorfsv/lounge`, `hectorfsv/render-rig`.

## `rig/` — the Render Rig's Favorites address on the Mac (2026-09-19)

Safari on the **Mac** keeps **one Favorites picture per website address**: its Touch Icons Cache
(`~/Library/Safari/Touch Icons Cache`, `TouchIconCacheSettings.db`, table `cache_settings`, keyed by `host`) files each
picture as `MD5(HOST).png`. The Lounge and the Rig are both `hectorfsv.github.io`, so the Rig's tile showed the Lounge's
Vader while its own tab showed Gargantua. The address bar and the iPhone are per page and were always right.

`https://hectorfsv.github.io./rig/` — **with the dot after `.io`** — is the same site to GitHub Pages (200, valid
certificate) and a different address to that cache. The Rig's favorite points there. `rig/index.html` only carries the
Rig's icons (`/render-rig/icon-*-v2.*`) and sends a page someone is looking at on to `https://hectorfsv.github.io/render-rig/`
with `location.replace`; a page nobody sees (how Safari fetches a favorite's picture) stays and reads the icons. The Rig
itself must run on the address **without** the dot: its saved history lives in that origin's storage and n8n answers
only that origin.

Never clear the Touch Icons Cache to "fix" a tile here: one host has one picture, so whichever page Safari fetches
first after the clear becomes the picture for every favorite on that host.
