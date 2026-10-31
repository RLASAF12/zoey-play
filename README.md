# המשחקים של זואי

Sixteen small browser games for a three-year-old, played with four big coloured
buttons (a USB keypad) or by touching the screen. Hebrew, with a recorded voice.

**Play it:** https://rlasaf12.github.io/zoey-play/

On an iPad or iPhone, open that address in Safari and use **Share → Add to Home
Screen**. It then opens full-screen. On the first visit leave it open for a minute:
the page is playable at once, but the voice is being stored for offline use behind
your back. After that it works with no network at all.

## About this repository

This repo is **generated output, not source.** It is built from a private repository
by `tools/build-pwa.js`, and editing anything here by hand would be overwritten by
the next build.

`index.html` is the whole app in one page — the games, the art, the font and the
code — and it loads nothing from any other site. The only thing it fetches is its
own voice: 328 recordings, as files, from this same folder. They used to be inlined
into the page too, which made it 15.4 MB and a first visit 26.9 MB; taking them out
brought the page to 2.8 MB and a first visit to 11.7, of which only 1.4 MB comes
before you can play.

| File | What it is |
|---|---|
| `index.html` | the whole app: games, art, font, code |
| `voice/<set>/<key>.mp3` | the 328 recorded lines, one file each |
| `manifest.webmanifest` | so it can be installed to a home screen |
| `sw.js` | the service worker. It stores the page and the icons when you first arrive, then the voice behind you, and serves everything from its own store afterwards |
| `icon-*.png`, `apple-touch-icon.png` | the home-screen icons |
| `.nojekyll` | serve these files as they are, with no Jekyll processing |
| `.gitattributes` | `* -text`: every file is stored and served as the exact bytes the build wrote. Without it, git on Windows rewrote the line endings in `index.html` on commit and what was served was no longer the file that had been tested |

## Credits

- Font: **Varela Round** by Noam Levy, under the SIL Open Font License, embedded in
  the page so that nothing is fetched.
- Animation: **GSAP 3.13.0** by GreenSock, vendored; its licence header travels
  inside the page (https://gsap.com/standard-license).
- Voice: generated speech, one Hebrew voice throughout.
- Art: generated illustration, drawn for this project.
