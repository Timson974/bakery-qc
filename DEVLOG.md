# 🛠️ Bakery QC — Development Log

A running record of every feature added, fixed, or changed.

---

## v0.9 — Multi-zone sampling + Shade Modal
**2026-11-15**

### ✨ Added
- **8-zone sampling grid** — 2 rows × 4 columns covering the full photo frame  
  Previously only 4 zones on the lower half; now catches multiple loaves top and bottom
- **Tiger Bread exception** — 3 zones across the top stripe (crust pattern is on top, not sides)
- Per-zone verdict chips in results screen: `1: 54 ✅  2: 58 ✅  3: 62 🔥`
- **Acrylamide Shade Modal** — "What is this? ›" button opens a full reference sheet:
  - Gradient bar 0–100 with live result marker
  - Three verdict zone cards with product-specific thresholds
  - Flourish Shade Card RGB swatches (Light / Target / Too Dark)
  - Science explainer: what acrylamide is, why colour matters, EU regulation
- All modal text i18n'd in 4 languages

### 🐛 Fixed
- `Identifier 'L' has already been declared` — duplicate `const L` inside `showResult()` removed

---

## v0.8 — 4 Languages
**2026-11-15**

### ✨ Added
- Full i18n system: English, Русский, Қазақша, Polski
- Language switcher in header (flag chips)
- `I18N` object with all UI strings per language
- `setLang(lang)` / `applyLang()` / `t(key)` helpers
- Product names, descriptions and advice localised per language

---

## v0.7 — Shade Card QC Standards
**2026-11-15**

### ✨ Added
- Flourish Acrylamide Shade Cards integrated: RGB values extracted from card photos
- Per-product shade swatches (Light / Target / Too Dark) shown below photo
- Darkness score calibrated against physical cards
- Section header "ACRYLAMIDE SHADE REFERENCE" with swatch row

### 🔧 Changed
- Thresholds refined for all 7 products using card measurements + production photos

---

## v0.6 — More Products & Calibration Photos
**2026-11-15**

### ✨ Added
- Ancient Grain 800g, Ancient Grain 400g, Classic Sourdough 800g, Ancient Bloomer 800g — additional calibration photos supplied
- Country Sourdough and Tiger Bread added to product list

### 🔧 Changed
- Improved pixel masking: exclude orange Flourish card background (`luma < 160`, `R − B < 90`)
- Rustic Sourdough: flour-dusted top treated as reference artefact, not under-baked crust

---

## v0.5 — PWA + Dual Input
**2026-11-14**

### ✨ Added
- Service Worker with offline cache (`bakery-qc-v1`)
- Web App Manifest injected as Blob URL (no separate manifest file needed)
- Two separate `<input>` elements: gallery picker + camera capture
- Install banner (`beforeinstallprompt`) for Add to Home Screen

### 🐛 Fixed
- Gallery button was opening camera on mobile — fixed by `accept="image/*"` without `capture` attribute
- Icon missing on mobile home screen — 192×192 and 512×512 PNG base64-inlined

---

## v0.4 — Multi-Product Support
**2026-11-13**

### ✨ Added
- Product selector grid (7 products)
- Per-product darkness thresholds (underbaked / proper / overbaked)
- Product-specific advice lists per verdict
- Screen navigation: select → photo → result → back

---

## v0.3 — Canvas Colour Analysis
**2026-11-13**

### ✨ Added
- Photo drawn to hidden `<canvas>`, pixel data sampled via `getImageData`
- Darkness score formula: `100 − (luma/255) × 100`
- Colour bar visualisation with cursor at current score
- RGB swatch + hex value display

---

## v0.2 — Photo Capture UI
**2026-11-12**

### ✨ Added
- Camera / gallery input
- Photo preview in `<img>` with overlay zone indicator
- Analyse button (enabled after photo loaded)

---

## v0.1 — Initial scaffold
**2026-11-12**

### ✨ Added
- Dark-themed single-page app shell
- Header with Flourish branding
- Screen routing system (`goTo()`)
- Toast notification component

---

*Log maintained by the QA team. Each entry reflects a deployed change.*
