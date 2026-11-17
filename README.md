# V Poovarasan — Apps (home page)

The home page for my Android apps, served by GitHub Pages at
**https://v-poovarasan-github.github.io/**

It is a launcher: one card per app, each linking to that app's own site, its
latest APK, and its source. All apps are 100% offline — no accounts, no ads,
no analytics.

## Apps

| App | What it is | Site | Source |
| --- | --- | --- | --- |
| **GlowBack** | Offline neon memory duel — challenge a friend with a single line of text | [/GlowBack-Game/](https://v-poovarasan-github.github.io/GlowBack-Game/) | [GlowBack-Game](https://github.com/V-Poovarasan-Github/GlowBack-Game) |
| **SilentSums** | Offline personal finance tracker with PIN/biometric lock | [/Silent-Sums/](https://v-poovarasan-github.github.io/Silent-Sums/) | [Silent-Sums](https://github.com/V-Poovarasan-Github/Silent-Sums) |

## How it is organised

- This repository (`v-poovarasan-github.github.io`) is the **user site**: its
  `index.html` is the page at the domain root.
- Each app keeps its own website in **its own repository** and is published as a
  **project site** under the same domain (`/<repo-name>/`). The apps' pages,
  privacy policies, issues and release history stay with each app.
- The home page links to the app sites with root-relative paths
  (`/GlowBack-Game/`, `/Silent-Sums/`) and loads each app's `logo.png` from its
  site, so those app sites must be published for the cards' links and icons to
  work.

## Files

- `index.html` — the whole page (HTML + CSS, plus a small script for the
  light/dark toggle and the mouse effects; no build step). The theme choice is
  kept in the visitor's own browser (`localStorage`) and is never sent anywhere.
  The mouse effects (card tilt and glow, cursor-lit dots) run only with a mouse
  and are off when the visitor prefers reduced motion. The two app logos load
  from the app sites (see above).
- `fonts/` — the web fonts (Inter and Space Grotesk, SIL Open Font License),
  served from this site so the page makes no third-party requests.
  Licences are in `fonts/LICENSES.txt`.
- `README.md` — this file.

## Adding another app

1. Publish the app's site from its own repo (Settings → Pages → `main`, root),
   with a `logo.png` in that repo's root.
2. Replace the "Coming soon" card in `index.html` (or copy one
   `<article class="app-card …">` block), give it its own colour class, and
   update the name, tagline, description, chips and the three links
   (`/<repo-name>/`, the repo's `releases/latest`, the repo).
3. Commit to `main`. Pages redeploys in a minute or two.

## Preview locally

Open `index.html` in a browser. To check the root-relative links and logos the
way GitHub Pages serves them, run a local server from a folder that contains
this file alongside the app folders, e.g. `python3 -m http.server`.

## License

Copyright (c) 2026 V Poovarasan. All rights reserved. The source is provided
for viewing purposes only; no permission is granted to use, copy, modify, or
distribute it, in whole or in part, for any purpose.
