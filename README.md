<p align="center">
  <img src="apps/web/public/favicon.svg" alt="R7 logo" width="128" height="128">
</p>

<h1 align="center">me.rinn7e.com</h1>

<p align="center">
  The casual personal website: a face as colour ASCII art that breathes, blinks and turns its eyes red, and a second screen with the links.
</p>

<p align="center">
  <a href="https://github.com/rinn7e/me/actions/workflows/deploy.yml"><img src="https://github.com/rinn7e/me/actions/workflows/deploy.yml/badge.svg" alt="Deploy"></a>
  <a href="https://me.rinn7e.com/"><img src="https://img.shields.io/website?url=https%3A%2F%2Fme.rinn7e.com&label=me.rinn7e.com" alt="me.rinn7e.com"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/rinn7e/me" alt="License: GPL-3.0"></a>
</p>

Screen 1 is the face; screen 2 shows the links. Both share one field of characters, and the face fades out of it to open screen 2.

## Layout

```
apps/web/              the website: React with react-tea-cup (the Elm Architecture), Vite, Tailwind v4
  src/portrait/        the ASCII portrait, its drawn animation frames and the switch to screen 2
  public/              the R7 logo: favicon.svg, favicon-32.png and apple-touch-icon.png
packages/codec/        io-ts helpers: readable decode errors
packages/design-tokens/ colours and fonts as CSS variables
doc/code-convention.md how the code is written, including the frame by frame animation rule
```

The animation frames in `apps/web/src/portrait` are drawn ahead of time by the design tools of the portrait.

## Requirements

Node 24 or newer and pnpm 11.

## Commands

Run from the repo root:

| Command                            | What it does                          |
| ---------------------------------- | ------------------------------------- |
| `pnpm install`                     | installs every workspace package      |
| `pnpm dev`                         | starts the website dev server         |
| `pnpm run build`                   | builds the website into apps/web/dist |
| `pnpm run check`                   | type checks every package             |
| `pnpm run lint`                    | ESLint over the repo                  |
| `pnpm run format` / `format:check` | Prettier                              |
| `pnpm test`                        | Vitest in every package               |

The debug controls (frame rate, pause, blink, red eye and its style) show in the dev build only.

## Deploy

GitHub Pages serves the website at [me.rinn7e.com](https://me.rinn7e.com/). `.github/workflows/deploy.yml` checks every push and pull request (format, lint, types, tests, build) and deploys every push to `master`. The custom domain is set in the Pages settings of the repository, with "GitHub Actions" as the source.

Until Nov 2026 this site lived in the repository `rinn7e/rinn7e.github.io`, at `rinn7e.com`, which now holds a placeholder for a future professional website. The old Elm site that lived there is kept in the branch `archive/elm-site` and the tag `elm-site-final`.

## License

The code is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.

The portrait and the logo are not covered by it: the photos and the ASCII frames made from them in `apps/web/src/portrait` (the `.jpg` and `.txt` files), and the R7 logo in `apps/web/public`, are copyright Moremi Vannak, all rights reserved. They may not be reused without permission.
