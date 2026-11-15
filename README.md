# 🍞 Bakery QC — Acrylamide Colour Checker

> A Progressive Web App for real-time crust colour analysis in Flourish Bakery production.  
> Built for bakers, QA supervisors, and line workers — works offline, installs on any phone.

---

## What it does

Snap or upload a photo of freshly baked bread straight from the rack.  
The app samples **8 zones** across the crust, calculates a **darkness score (0–100)** using the same luminance formula as the Flourish Acrylamide Shade Cards, and instantly tells you:

| Verdict | Meaning |
|---|---|
| 💧 **Too Light** | Under-baked — acrylamide risk low but texture/flavour not optimal |
| ✅ **Proper** | On target — matches Flourish shade card standard |
| 🔥 **Too Dark** | Over-baked — acrylamide formation concern |

---

## Products supported

| Product | Target range |
|---|---|
| Ancient Grain 800g | 50 – 62 |
| Ancient Grain 400g | 52 – 61 |
| Ancient Bloomer 800g | 53 – 61 |
| Classic Sourdough 800g | 54 – 60 |
| Rustic Sourdough | 42 – 60 |
| Country Sourdough | 53 – 59 |
| Tiger Bread | 44 – 68 |

---

## How to use

1. Open **[bakery-qc.flourish.app](https://timson974.github.io/bakery-qc/)** on your phone
2. Tap **Add to Home Screen** to install as PWA
3. Select product → take/upload photo → tap **Analyse**
4. Read the verdict and per-zone breakdown
5. Tap **What is this? ›** on the shade card for the full acrylamide reference scale

---

## Languages

🇬🇧 English · 🇷🇺 Русский · 🇰🇿 Қазақша · 🇵🇱 Polski

---

## Tech stack

- Vanilla HTML/CSS/JS — zero dependencies, zero build step
- Canvas API for pixel sampling
- PWA (Service Worker + Web App Manifest) — works offline
- Hosted on GitHub Pages

---

## Thresholds & calibration

Darkness scores are calibrated against physical **Flourish Acrylamide Shade Cards** (Ref. 1–4).  
RGB values extracted from production photos under consistent lighting.  
Formula: `darkness = 100 − (luma / 255) × 100`, where `luma = 0.299R + 0.587G + 0.114B`

---

## Development

See [`DEVLOG.md`](DEVLOG.md) for the full build history.

---

*Internal tool — Flourish Bakery QA team*
