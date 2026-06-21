# Deploy — Lily Ray slide + source QR codes

Two files change in the `hate-the-prompt` repo. **No Zlatko slide PNGs are touched.**

## Files in `hate-the-prompt-update.zip`
1. **`index.html`** → replaces the existing one (root of repo)
2. **`assets/lilyray-27.png`** → NEW file, drop into `assets/`

Everything else (slides, audio, the existing overlays) is untouched.

## Commit
```bash
cd ~/Downloads/hate-the-prompt        # your local clone
# copy the two files in from the unzipped update, then:
git add index.html assets/lilyray-27.png
git commit -m "Add Lily Ray slide (27) + opt-in source QR codes + hash deep-linking"
git pull --rebase origin main && git push
```

## What changed (all additive)
- **New slide 27 — Lily Ray.** Inserted between Fable 5 (26) and ACT III (now 28) as `assets/lilyray-27.png`. Deck is now **43 slides**. The existing slide PNGs were NOT renamed or re-exported — the viewer just plays the new asset in sequence.
- **Source QR codes — opt-in, press `S`.** A bottom-left HUD card with the QR + domain. Off by default (clean delivery); press **S** (or the **◆ SOURCES** button) to reveal the source for the current slide. On these slides only:

  | Slide (of 43) | Source |
  |---|---|
  | 6 | Ryan Murton LinkedIn thread |
  | 7 | EGR article |
  | 17 | Search Engine Journal (Danny Sullivan) |
  | 21 | Jon Clark / Profound Zero-Click |
  | 24 | CL4R1T4S leaked prompts repo |
  | 26 | CL4R1T4S (Fable 5) |
  | 27 | Lily Ray substack |
  | 42 | EGR article |

  No QR on slide 35 (MACHINE TRUE / Floate webinar) — password-protected, deliberately omitted.
- **Hash deep-linking.** `…/#27` jumps straight to slide 27 (skips the start gate). The URL updates as you navigate, so any slide is linkable/shareable.
- **Untouched, as required:** the slide PNGs, the intro/outro audio chain (intro on 1–4, outro now on slide 43 — auto-derived), the click-to-begin gate, JUDGEMENT DAY end-card, rotate-phone prompt, and all T2 atmospherics (sweep, grain, REC dot, eye blinks, loader).

## Notes / your call
- **The Lily Ray slide is rendered in the deck's T2 style** (molten 69% hero, chrome/fire/yellow palette) as a faithful drop-in. If it sits next to Zlatko's hand-designed slides and you want pixel-exact parity, hand Zlatko the content and swap `assets/lilyray-27.png` for his version — nothing else needs to change.
- **Baked counters:** Zlatko's slides have their "REC NN/42" baked in; with 43 slides the baked top-right numbers are now cosmetically off by one after slide 26. The live bottom counter is correct (NN / 43). If that bugs you, Zlatko can re-export with /43 — but it's cosmetic.
- **QR scannability:** all 8 are generous on the LED wall. The Ryan Murton LinkedIn *comment* deep-link is a very long URL (dense QR) — fine on the wall, but phones may need to be close. Say the word and I'll point that one at a short link instead.
