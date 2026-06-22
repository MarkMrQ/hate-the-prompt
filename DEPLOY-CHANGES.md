# Lily Ray slide + source QR codes — what happened & how to ship

## Why it looked broken
- The **live site was never updated** — it's still the old 42-slide version, so there was no QR and no Lily Ray. Nothing was wrong with your machine.
- The earlier zip was a **drop-in for the repo** (just `index.html` + the new asset) — it doesn't contain the slide PNGs, so opening it on its own makes every slide image 404 → blank ("slide 5 broke"). That's expected for a drop-in; it only works once dropped into the repo that already has the slides.
- The QR codes were built **opt-in (press S)**, so they were invisible by default. **Fixed:** QRs now appear automatically (fade in ~1.6s) on the 8 source slides; press **S** (or the ◆ SOURCES button) only if you want to *hide* them.

## Two zips
**1. `hate-the-prompt-FULL.zip` — to TEST.** A complete, self-contained site. Unzip, double-click `index.html`, and everything works offline: 43 slides, Lily Ray at 27, QR codes visible on the 8 source slides, audio, nav. Use this to verify before you deploy.
**2. `hate-the-prompt-update.zip` — to DEPLOY.** The changed files (`index.html` + `assets/lilyray-27.png` + `slides/slide-25.png`) for a clean commit.

## Deploy
```bash
cd ~/Downloads/hate-the-prompt
# copy in index.html (overwrite) + assets/lilyray-27.png (new) + slides/slide-25.png (overwrite), then:
git add index.html assets/lilyray-27.png slides/slide-25.png
git commit -m "Add Lily Ray slide (27) + auto source QR + hash deep-linking + slide 25 copy fix"
git pull --rebase origin main && git push
```
> **slide-25.png** is the OUT-SEO slide with the new sub-line *"Not a ranking problem. Not a hack you can buy."* (was "…rap I can rhyme with"). If your live slides are Zlatko's hand-designed versions, this one is my T2 render — give Zlatko the new line for exact parity, or deploy mine.

## ⚠ Important — which slides are live?
The FULL test zip contains **my rendered slide PNGs** so you can test offline. If your live `/slides/` are **Zlatko's hand-designed versions** (different from mine), do **NOT** deploy the `slides/` folder from the full zip — deploy **only `index.html` + `assets/lilyray-27.png`** (the update zip). That preserves Zlatko's locked slides; the viewer just plays the new Lily Ray asset in sequence.
- If your live slides are actually my renders, you can deploy the whole FULL folder — same result.
- Either way, the new **Lily Ray slide is my T2 render**; swap in a Zlatko version later by replacing `assets/lilyray-27.png` (no other change needed).

## What's in the change (all additive — atmospherics, audio chain, gate, JUDGEMENT DAY, rotate-prompt untouched)
- New slide 27 (Lily Ray) → deck is 43; existing PNGs not renamed/re-exported.
- 8 source QRs (on by default, appear ~0.2s after the slide loads; press **S** or the ◆ SOURCES button to hide). Small 84px badge pinned to the **slide's bottom-right corner** — positioned inside the stage so it scales with the slide and lands in the same spot on every screen. Position was pixel-checked against all 8 source slides to clear the attribution lines, stat/quote boxes and footer. Slides: 6, 7, 17, 21, 24, 26, 27, 42. None on 35 (Floate webinar, password-protected).
- Hash deep-linking: `/#27` jumps straight to slide 27; URL updates as you navigate.
- Cosmetic note: Zlatko's baked "REC NN/42" counters are now off-by-one after slide 26 (the live bottom counter reads correctly as NN/43). Zlatko can re-export if it bugs you.
