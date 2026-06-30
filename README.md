# Don't Hate the Player, Hate the Prompt — T2 web deck (verified build)

All 42 slides are pre-rendered at 1400×800 (matching the LED wall) and shown in a lightweight viewer with the intro/outro audio. Every slide was visually checked before shipping — no overlaps, nothing missing.

## Why this build
The previous version drew the slides live with CSS, which I couldn't preview here, so layout bugs slipped through. This build renders each slide to an image I can inspect directly, then plays them in sequence — rock-solid and identical on every machine/browser.

## Controls
- **→ / Space / click-right** next · **← / click-left** back · **F** fullscreen · **Home/End** jump
- Sound toggle bottom-right. Intro plays across slides 1–4, then fades out as you step on; outro on slide 42. **First clicker press arms the audio** (browser autoplay rule).

## Run it
Double-click `index.html`. (For Safari/file:// audio, run `python3 -m http.server` in this folder and open `localhost:8000`.)

## Folders
```
index.html          the viewer
slides/             slide-01.png … slide-42.png  (1400×800)
assets/audio/       intro.mp3, outro.mp3  (already in place)
assets/linkedin/    drop the 6 screenshots here (see below)
```

## To finish
- **LinkedIn screenshots** (slides 11–13): they currently show styled placeholder cards. Send the 6 screenshots and I'll drop them straight into the slides and re-render.
- **QR codes** (slide 42): send the two track URLs and I'll render them onto the end slide.
- **Real T2 font:** these are rendered with a squared substitute. Upload the "Terminator Two" .ttf and I'll install it and re-render the whole deck in the true logotype.
- **Backups:** say the word for a PPTX + PDF (named `02JUL-1235-DontHateThePlayerHateThePrompt`) built from these frames, for the venue machines.

## Deploy
- **Netlify/Vercel:** drag this folder onto app.netlify.com/drop.
- **GitHub Pages:** push the folder, enable Pages on main/root.
- **Railway:** add a `Caddyfile` (`:{$PORT}` / `root * .` / `file_server`) and deploy.

## Editing
All content lives in `../gen_site.py`. Change text/layout there and run `python3 ../gen_site.py` to re-render every slide.
