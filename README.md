## Stacking Cake — Happy Birthday!

An animated, single‑file birthday card. A colorful cake stacks itself, candles wiggle, confetti falls, and a message appears that you can personalize.

## Features
- **Layered cake animation**: Smooth, responsive stacking with subtle easing
- **Candles + wiggle**: Cute motion loop using the Web Animations API
- **Confetti**: Lightweight canvas confetti with auto‑density on resize
- **Personal message**: Click the message to set a name on the fly

## Project structure
```
Birthaday/
  ├─ img/
  │  ├─ stitch.png   (current sticker image)
  │  └─ b.webp       (alternative sticker image)
  └─ index.html      (all CSS + JS in one file)
```

## Quick start
- Option A: Double‑click `index.html` to open it in your browser.
- Option B (recommended for consistency): Serve locally.
  - Python: `python -m http.server 5500`
  - Node (npx): `npx serve -l 5500`
  - Then open `http://localhost:5500` in your browser.

## Customize
- **Default name**: In `index.html`, change the text inside the element with id `messageText`.
  - Also, you can click the message in the page to set a name via a prompt.

- **Sticker image**: The sticker is loaded from `img/stitch.png`.
  - Replace `img/stitch.png` with your own image file (PNG/WebP works well), or update the `src` on the sticker `<img>` tag:
    ```html
    <img class="sticker" src="img/your-image.png" alt="Cute character" />
    ```

- **Colors**: Tweak background gradient via CSS variables at the top of `index.html`:
  - `--bg1`, `--bg2` control the background sky
  - Layer gradients are defined per `.layer.l1` … `.layer.l6`

- **Timing**: Adjust the stacking speed in `stackLayers()` by changing `baseDelay` and the per‑layer increment.

- **Confetti look**: Edit the `colors` array in `startConfetti()`.

- **Candles**: Add/remove `<div class="candle"></div>` inside the `.candles` container to change the count.

## Troubleshooting
- **Image not showing**:
  - Ensure the file exists in `img/` and the `src` path matches exactly (including extension/casing).
  - Try using a local server (see Quick start) if your browser blocks some features over the `file://` protocol.

- **Confetti not visible**:
  - Make sure your browser supports `<canvas>` (all modern browsers do).
  - Resize the window to force a canvas resize/density recalculation.

## Deploy
- **GitHub Pages**: Push this folder to a GitHub repo → Settings → Pages → Deploy from branch → select the branch and root. Your page will be live at the provided URL.
- **Netlify/Vercel**: Drag‑and‑drop the folder or connect the repo. No build step required.

## Attribution
Made with plain HTML/CSS/JS. No external dependencies.


