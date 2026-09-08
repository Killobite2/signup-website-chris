# Signup Website — Chris

Standalone newsletter signup page for CL Growth Academy, built on the brand's
existing design tokens (Workshop Ink / Oxblood / Paper / Mustard / Cream —
Alfa Slab One, Yellowtail, Work Sans). Subscribes to
`https://clgrowth.beehiiv.com/subscribe`.

Copied out of the main [cl-growth-academy-website](https://github.com/Killobite2/cl-growth-academy-website)
project so it can be deployed and tracked on its own.

**This is the repo Vercel deploys**, as the `signup-website-chris` project at
`signup-website-chris.vercel.app`. There is also a
[website-sign-up](https://github.com/Killobite2/website-sign-up) repo holding an
older copy of the same page; it is not connected to any Vercel project and is
superseded by this one. Check which repo you are in before editing.

## Keeping it in sync

`newsletter.html`, `css/styles.css` and `js/main.js` are **straight copies** from
the main repo. They used to be trimmed to just what this page needs, and that is
exactly what went wrong: the page picked up `.form-pill`, the drawn-tick success
state, `.sr-only`, `.section-callout` and `.keep-together` upstream, and none of
the styling came with it. Whole files cost about 55KB more and remove the
failure mode.

To sync, copy those three files across, then re-point the two self-references
this repo owns:

- `<link rel="canonical">` and `og:url` &rarr; `signup-website-chris.vercel.app`

Everything else, the brand link included, still points at the main site on
purpose. After copying, check that every class the page uses is defined in its
CSS; that single check is what catches a bad sync.

## Layout notes

- `vercel.json` rewrites `/` to `/newsletter.html` — there is no `index.html`,
  so the bare domain would otherwise 404.
- `video/newsletter-hero.mp4` is the hero background: 1600x598, 24fps, no audio
  track, `faststart`. Encoded with the montage's bottom 20% cropped away, which
  removes the burned-in subtitles that would otherwise compete with the
  headline. `img/newsletter-hero-poster.jpg` is its first frame, so playback
  starts without a visual jump and reduced-motion visitors get a matching still.
- The hero scrim in `css/styles.css` (section 25) is tuned to this footage's
  brightness. Recut material may need its gradient stops moved.

## Running it

Open `newsletter.html` directly, or serve the folder with any static file
server (e.g. `python3 -m http.server`).
