# Ashgrove Academy — School Website

A single-page website for a fictional independent day school, built with plain
HTML, CSS and JavaScript. It leans hard on motion: a curtain intro, masked
headline reveals, scroll-driven text and timeline drawing, tilting cards, and a
video lightbox.

**Live:** https://ashgrove-academy.vercel.app/

## What's in it

- **Hero** — drifting light orbs, a slow dashed ring, and a headline that rises
  line by line once the intro curtain lifts.
- **About** — a statement that fills word by word as you scroll, plus stat
  counters that animate into view.
- **Programmes** — four year-group cards that flood with colour on hover.
- **Campus** — a photo grid (classroom, library, sixth-form study, main
  building) that warms from grayscale on hover.
- **Faculty** — six teacher portraits with subject and degree, revealed in a
  staggered wave.
- **Guest classroom** — a 16:9 player card that opens a YouTube embed in a
  lightbox, with Escape/backdrop close and focus restored afterwards.
- **Voices** — auto-rotating testimonials with arrows and progress dots.
- **Admissions** — a four-step timeline whose line draws as you scroll.
- **CTA + footer** — a full-bleed accent panel and marquee.

The whole thing is responsive, keyboard reachable, and respects
`prefers-reduced-motion`.

## Tech

No framework, no build step required to view it. Vite is included for local
development, and the page loads its stylesheet directly so it also works from
any static file server.

```
index.html        all markup and content
src/style.css     design system, layout, animation
src/main.js       scroll reveals, counters, slider, menu, video lightbox
worker/index.js   tiny static-asset Worker (optional hosting helper)
deploy.json       static deployment manifest
```

## Run locally

With Bun or Node installed:

```sh
bun install
bun run dev
```

Or without any toolchain, from the project folder:

```sh
python3 -m http.server 5173
```

Then open http://127.0.0.1:5173/.

To produce a production build (Vite):

```sh
bun run build
bun run preview
```

## Deploy

The site is static, so any host works:

- **Vercel** — import the repo and leave the framework preset as "Other"
  (no build command, output directory is the repo root), or deploy the files
  as-is.
- **Freebuff Sites** — use the included `deploy.json`.
- **GitHub Pages** — serve the repo root from the `main` branch.

## Make it yours

Everything is in `index.html` and `src/style.css`:

- School name, contact details and copy: edit the markup directly.
- Colours and type: the `:root` custom properties at the top of `style.css`
  (`--ink`, `--paper`, `--lime`, `--coral`, `--display`, `--sans`).
- Photos: replace the Unsplash URLs with your own images.
- Video: swap the YouTube ID in `src/main.js` (`iG9CE55wbtY`) and the poster
  image in the guest-classroom section.

## Credits

- Photography from [Unsplash](https://unsplash.com) — replace with licensed
  school photography before going live.
- Guest video: ["Do schools kill creativity?"](https://www.ted.com/talks/sir_ken_robinson_do_schools_kill_creativity)
  by Sir Ken Robinson, TED — embedded via `youtube-nocookie.com`.
- Typefaces: Fraunces and Inter, served from Google Fonts.

Ashgrove Academy is a fictional school; all names, quotes, statistics and staff
profiles are placeholders written for the demo.
