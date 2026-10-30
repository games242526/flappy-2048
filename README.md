# Flappy 2048

A Flappy-Bird-style take on [2048](https://github.com/gabrielecirulli/2048), built from scratch with plain HTML/CSS/JavaScript (no framework, no build step). You are a 2048 tile in flight: flap through the gaps in a stream of green wall tiles, and every few walls you pass your tile merges up to the next number — 2, 4, 8 … all the way to 2048.

Demo: `https://<username>.github.io/<repo>/` (replace with your GitHub Pages link after deploying).

## How it plays

- **Flap**: tap or click anywhere, or press **Space**, **↑**, or **W**. Let go and you fall.
- **Score**: every wall you pass counts once. Pass **5** walls and the tile merges up (2 → 4 → 8 …). Reach **2048** (50 walls) to win, then keep flying for a higher score.
- **Crash**: touching a wall ends the run. The floor and ceiling are safe, so you can rest on the floor when the next gap is low.
- **Speed**: the walls scroll faster the more you pass, up to a cap.
- A small bar on the tile shows progress toward the next merge.

## Features

- Frame-rate-independent physics (fixed 120 Hz simulation step), so it feels the same on 60 Hz and 144 Hz screens.
- Tuned so it is hard but winnable — a reaction-time-limited autopilot used during development reaches 2048 on a good share of runs.
- Pauses automatically while the how-to-play window is open or the page is hidden, and resumes with a short grace period during which walls can't hurt you.
- Best score saved with `localStorage`.
- Win / game over overlays; after winning you can keep flying.
- Fully responsive — scales to the screen or to the iframe it's embedded in, and never scrolls the page regardless of how small or short the viewport is.
- Light/dark theme toggle.

## Run locally

Just open `index.html` in a browser, or serve it with any static server, e.g.:

```bash
npx serve .
```

## Deploy to GitHub Pages

1. Create a new GitHub repo and push the contents of this folder to the `master` (or `main`) branch.
2. Go to **Settings → Pages**, set the source to that branch, folder `/ (root)`.
3. After a minute or two, GitHub will give you a link like `https://<username>.github.io/<repo>/`.

## Embedding via iframe

```html
<iframe
  src="https://<username>.github.io/<repo>/"
  style="width:100%; height:100%; border:0;"
  loading="lazy"
></iframe>
```

## Credit

Inspired by [2048 by Gabriele Cirulli](https://github.com/gabrielecirulli/2048). The idea of a flapping 2048 tile is inspired by [Flappy 2048 by hcz](https://hczhcz.github.io/Flappy-2048/), which itself builds on Flappy Bird by Dong Nguyen — this project reuses that idea only, not its code; all HTML/CSS/JS here is written from scratch and the game rules and tuning are original. This fan project is not affiliated with either.
