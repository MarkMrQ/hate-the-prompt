# Don't Hate the Player — Lily Ray slide, source QRs, copy + audio fixes

## Two zips
**1. `hate-the-prompt-FULL.zip` — to TEST.** Complete self-contained site. Unzip, double-click `index.html`, works offline: 43 slides, Lily Ray at 27, QR codes on the 8 source slides, audio, nav. Verify here before deploying.
**2. `hate-the-prompt-update.zip` — to DEPLOY.** Just the changed files for a clean commit: `index.html` + `assets/lilyray-27.png` + `slides/slide-07.png` + `slides/slide-14.png` + `slides/slide-25.png`.

## Deploy
```bash
cd ~/Downloads/hate-the-prompt
# copy in the changed files from the update zip (overwrite index.html + the 3 slides, add lilyray-27.png), then:
git add index.html assets/lilyray-27.png slides/slide-07.png slides/slide-14.png slides/slide-25.png
git commit -m "Lily Ray slide 27 + auto source QR + deep-linking + audio gate fix + copy fixes (slides 7,14,25)"
git pull --rebase origin main && git push
```

## What changed
- **New slide 27 — Lily Ray** ("69%" empirical proof). Deck is now 43; no existing PNG renamed or re-exported.
- **Source QR codes — 8 slides** (6, 7, 17, 21, 24, 26, 27, 42; none on 35 — Floate webinar is password-protected). Now **always on, no toggle** (removed the SOURCES button — it looked bad on mobile). The QR lives **completely outside the slide artwork**: the slide now scales to leave a thin black "telemetry band" at the bottom of the screen on every display, and the QR sits in that band in the bottom-right corner, next to the SOUND ON button. It never overlaps slide content. Appears ~0.2s after a source slide loads.
- **Audio gate fix** — audio no longer plays until you click the warning screen. Previously the intro track could start under the gate; now nothing plays before "INITIATE BRIEF" is clicked.
- **Copy fixes (re-rendered slides):**
  - **Slide 7** — "EGR ask Mark to write it up" → **"EGR asked me to write it up"** (first person).
  - **Slide 14** — "Founder of Growth?" → **"Founder or Growth?"**
  - **Slide 25** — "Not a rap I can rhyme with" → **"Not a hack you can buy."**
- **Hash deep-linking** — `/#27` jumps straight to slide 27; URL updates as you navigate (skips the warning gate when deep-linked).

All additive otherwise — atmospherics, JUDGEMENT DAY end-card, rotate-phone prompt untouched.

## ⚠ Which slides are live?
The FULL zip contains **my rendered slide PNGs**. If your live `/slides/` are **Zlatko's hand-designed versions**, deploy **only the changed files listed above** (the update zip) — that preserves Zlatko's other slides; the viewer just plays the new/edited assets in sequence. **slides 7, 14, 25** in the update zip are *my* T2 renders of those three — if your live versions are Zlatko's, give him the new wording for exact parity, or deploy mine. The **Lily Ray slide** is also my T2 render; swap in a Zlatko version later by replacing `assets/lilyray-27.png`.

Cosmetic: Zlatko's baked "REC NN/42" counters read off-by-one after slide 26 (the live bottom counter is correct at NN/43). Zlatko can re-export if it bugs you.

## One thing left for you to decide
Slide 6's quote attribution still reads *"— Mark Hald, ranting on LinkedIn about Google."* That's a byline/signature rather than third-person narration, so I left it — but if you want it gone too, say so and I'll change it.
