# המשחקים של זואי

Sixteen small browser games for a three-year-old, played with four big coloured
buttons (a USB keypad) or by touching the screen. Hebrew, with a recorded voice.

**Play it:** https://rlasaf12.github.io/zoey-play/

On an iPad or iPhone, open that address in Safari and use **Share → Add to Home
Screen**. It then opens full-screen and keeps working with no network at all.

## About this repository

This repo is **generated output, not source.** `index.html` is one self-contained
page: the games, the art and every voice clip are inlined into it, and it makes no
network request of any kind once loaded. It is built from a private repository by
`tools/build-pwa.js`, and editing anything here by hand would be overwritten by the
next build.

| File | What it is |
|---|---|
| `index.html` | the whole app, one file |
| `manifest.webmanifest` | so it can be installed to a home screen |
| `sw.js` | the service worker that keeps it working offline |
| `icon-*.png`, `apple-touch-icon.png` | the home-screen icons |
| `.nojekyll` | serve these files as they are, with no Jekyll processing |

## Credits

- Font: **Varela Round** by Noam Levy, under the SIL Open Font License, embedded in
  the page so that nothing is fetched.
- Animation: **GSAP 3.13.0** by GreenSock, vendored; its licence header travels
  inside the page (https://gsap.com/standard-license).
- Voice: generated speech, one Hebrew voice throughout.
- Art: generated illustration, drawn for this project.
