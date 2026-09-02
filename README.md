# Sign Up Website Page

Standalone newsletter signup page for CL Growth Academy, built on the brand's
existing design tokens (Workshop Ink / Oxblood / Paper / Mustard / Cream —
Alfa Slab One, Yellowtail, Work Sans). Subscribes to
`https://clgrowth.beehiiv.com/subscribe`.

Copied out of the main [cl-growth-academy-website](https://github.com/Killobite2/cl-growth-academy-website)
project so it can be deployed and tracked on its own. `css/styles.css` and
`js/main.js` are trimmed to what this one page uses.

The same page also exists at `/newsletter.html` in the main site. Any change
here needs mirroring there, or the two copies drift.

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
