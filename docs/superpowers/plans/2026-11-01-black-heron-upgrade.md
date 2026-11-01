# Black Heron Tattoo & Piercing — Luxury Upgrade Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Upgrade the existing Black Heron Tattoo & Piercing single-page site to world-class atelier standards: warm luxury palette, fixed hero layout and seams, 100svh work rail sizing, stacked artist cards with work-photo hover reveals, dual marquee strips, SVG stroke self-drawing text and icons, organic scrubbed ink-edge hero transition, two-row drifting reviews, and a complete architectural rebuild of the multi-step consultation booking section.

**Architecture:** Single-file `index.html` structure with clean modular CSS architecture, responsive design tokens, and robust GSAP ScrollTrigger + Lenis smooth scroll choreography. Python build scripts in `scratch/` generate, validate, and test the code against Playwright headless Chromium audits across 5 viewports.

**Tech Stack:** Semantic HTML5, Vanilla Modern CSS with CSS custom properties, Vanilla JavaScript (ES6+), GSAP 3.12.5 + ScrollTrigger 3.12.5, Lenis 1.1.18, Google Fonts (Anton, Allura, Barlow).

---

## Global Constraints

- **Single Deliverable File**: Complete updated `index.html` with inline `<style>` and `<script>`.
- **Palette Tokens**: `--ivory #F7F2EA`, `--bone #EDE4D6`, `--ink #0E0C0B`, `--oxblood #5A0F1B`, `--crimson #B5121B`, `--brass #B8975A`, `--ash #4A4238`. Zero blue or purple.
- **Section Color Rhythm**:
  1. Hero: photo band + dark overlay
  2. Studio intro: `--ivory`
  3. Two disciplines: `--bone`
  4. Selected work: `--ivory`
  5. The standard: `--oxblood`
  6. Artists: `--ivory`
  7. Process: `--bone`
  8. Pricing: `--ivory`
  9. Reviews: `--ink`
  10. FAQ: `--ivory`
  11. Booking: `--oxblood`
  12. Footer: `--ivory`
- **Typography Scale**: Anton (headlines, uppercase, line-height 0.95), Allura (script accent, >= 4rem), Barlow (19px body, line-height 1.65, max 62ch; 16px labels uppercase 0.12em tracking; nothing under 15px except 14px legal/badge).
- **Section Gaps**: <= 96px on desktop (<= 64px on mobile).
- **No Custom Cursor**, no magnetic effects, no big numerals.
- **Scroll Stability Priority**: Animate transform and opacity only. Respect `prefers-reduced-motion`. Turn off ink-edge, stacked cards, and badge speed-up under 768px. Call `ScrollTrigger.refresh()` after fonts and images load.

---

## Review Focus

1. **A1 Hero Headline & Script Word Layout**: The script word "atelier" must sit on its own line below "PIERCING", right-aligned, with zero letter collision, and headline masked lines must have line-height >= 1, padding-bottom 0.08em, and `will-change: transform` to eliminate thin vertical seams.
2. **A3 Work Rail Sizing**: Cards must fit completely inside `100svh` minus header and heading at 1366x768, 1440x900, and 1920x1080 without card titles or metadata cutting off at the bottom.
3. **A6 & Part E Booking Wizard Architecture**: The booking form must be completely rebuilt with a full-bleed oxblood section, sticky left column (5/12), right ivory card (7/12) with brass border and soft shadow, custom tile radios with visually hidden native inputs, dynamic chip selections, client-side reference file uploader (up to 5 previews with removal), summary box with edit jumps, 56px action buttons, inline crimson error messaging with `aria-live`, and an SVG-drawing success confirmation hidden via `[hidden]{display:none !important}` until submit.
4. **Part C Landing Page Enhancements**: Under 1.4s preloader with `sessionStorage` skip, slow continuous zoom (1 to 1.08 over 18s), 4% SVG noise film grain, "Now booking: [Month]" pill with pulsing crimson dot, rotating circular text badge with scroll velocity, 4-item brass-separated trust strip, and an organic scrubbed SVG ink-edge transition.
5. **Part D Interactive Refinements**: Dual opposing marquee strips, artists sticky stacked cards (desktop), reviews two opposing drift tracks on ink band with brass stars, brass icon SVG stroke-dashoffset self-draw on scroll in The Standard.

---

## Tasks

### Task 1: Assets & Artist At-Work Photos Generation
**Files:**
- Create: `assets/images/artist_1_at_work.jpg`
- Create: `assets/images/artist_2_at_work.jpg`
- Verify: `assets/images/artist_1_work.jpg`, `assets/images/artist_2_work.jpg`, `assets/images/artist_3_work.jpg`
- Output: Authentic editorial photos showing gloved hands, rotary tattoo machine, ink caps, and jewellery tray.

- [ ] **Step 1: Generate authentic at-work photo for Caleb Vance (fine line artist with gloves & rotary needle)**
- [ ] **Step 2: Generate authentic at-work photo for Maren Croft (blackwork artist with heavy ink & gloves)**
- [ ] **Step 3: Copy images to `assets/images/` and verify dimensions and file sizes**

---

### Task 2: Design Tokens, Typography, and Global Styling Upgrade (Part B & Part F)
**Files:**
- Modify: `index.html` (via build script in `scratch/build_complete_site_upgrade.py`)

- [ ] **Step 1: Define updated color tokens in `:root` (`--ivory`, `--bone`, `--ink`, `--oxblood`, `--crimson`, `--brass`, `--ash`)**
- [ ] **Step 2: Implement sepia 0.15 warm tone filter on photos with `transition: filter 0.6s ease` to full color on hover**
- [ ] **Step 3: Implement oxblood multiply overlays on dark bands (`#standards`, `#booking`) and ink multiply on `#reviews`**
- [ ] **Step 4: Update button styling: ink fill with ivory text & oxblood hover wipe; on dark bands, ivory fill with ink text & brass hover wipe**
- [ ] **Step 5: Add SVG "BH" favicon, meta description, OG tags, Schema.org `TattooParlor` JSON-LD, skip-to-content link, and 8px spacing utility classes**

---

### Task 3: Fix Landing Page & Hero Bugs (A1, Part C)
**Files:**
- Modify: `index.html`

- [ ] **Step 1: Implement preloader (<1.4s) with Anton "BLACK HERON", subline, lifting curtain, and `try/catch` `sessionStorage` guard**
- [ ] **Step 2: Re-architect Hero headline: place script word "atelier" on its own right-aligned line below "PIERCING", eliminate mask seams with line-height >= 1, padding-bottom 0.08em, and `will-change: transform`**
- [ ] **Step 3: Implement slow continuous hero background zoom (1 to 1.08 over 18s alternate) and 4% film grain overlay**
- [ ] **Step 4: Implement SVG stroke-dashoffset self-draw for "atelier" that fills crimson upon completion**
- [ ] **Step 5: Add "Now booking: [Month]" pill with pulsing crimson dot under header**
- [ ] **Step 6: Add rotating circular text badge ("TATTOO · PIERCING · CHRISTCHURCH ·") with scroll velocity speedup**
- [ ] **Step 7: Replace hero bottom meta strip with 4-item trust strip separated by brass hairlines (4.9 on Google / Sterile, single-use / Implant-grade jewellery / Free touch-up)**
- [ ] **Step 8: Implement organic scrubbed ivory ink-edge SVG transition between hero and marquee**

---

### Task 4: Fix Studio Intro & Work Rail (A2, A3, Part D Marquee)
**Files:**
- Modify: `index.html`

- [ ] **Step 1: Restore plus sign on counter `850+` and update photo captions to "Piercing room" and "Oxford Terrace, Christchurch"**
- [ ] **Step 2: Add 2nd thin oxblood marquee strip with outlined ivory text moving in reverse, velocity-reactive**
- [ ] **Step 3: Recalculate work rail card sizing for 100svh minus header and heading across 1366x768, 1440x900, 1920x1080 (image height `min(54svh, 520px)`)**
- [ ] **Step 4: Implement work rail center-card focus effect (center card scale 1, non-center cards scale 0.94 and 70% opacity)**
- [ ] **Step 5: Verify lightbox opens and closes cleanly without layout shifts**

---

### Task 5: Upgrade The Standard, Artists, Process, Pricing, Reviews & FAQ (A4, A5, Part D)
**Files:**
- Modify: `index.html`

- [ ] **Step 1: In The Standard (oxblood band), implement SVG `stroke-dashoffset` self-drawing brass line icons and flourish divider**
- [ ] **Step 2: In Artists section, build stacked sticky horizontal cards for desktop (`top: 96px`, previous cards scale to 0.94 and dim as next slides over; plain stack on mobile)**
- [ ] **Step 3: Add work photo reveal on hover for all 3 artist cards**
- [ ] **Step 4: In Process section, update drawing hairline to fill step dots with crimson, turn titles from ash to ink, and draw brass underlines**
- [ ] **Step 5: In Pricing section, implement two-column grid per row (label/desc left, figure right-aligned) and animated figure count-up**
- [ ] **Step 6: In Reviews section (ink band), build 2 rows drifting in opposite directions with 6 cards, brass stars, pause-on-hover, and animated "4.9" count-up**
- [ ] **Step 7: In FAQ section, implement smooth accordion height animation with plus-to-cross rotation and active left crimson indicator bar**

---

### Task 6: Complete Rebuild of Booking Section (A6 & Part E)
**Files:**
- Modify: `index.html`

- [ ] **Step 1: Build full-bleed oxblood section layout with sticky left column (5/12) featuring trust chips and next steps**
- [ ] **Step 2: Build right ivory form card (7/12) with brass border, soft shadow, and 4-step segmented progress bar**
- [ ] **Step 3: Build Step 1 (Service): 2x2 grid of custom selectable label tiles with original icons, Anton 24px titles, hidden real radios, and crimson check badges**
- [ ] **Step 4: Build Step 2 (Your idea): dynamic conditional fields for Tattoo/Cover-up vs Piercing, interactive chips for style/placement/size/jewellery, textarea, and drag-and-drop reference uploader (up to 5 images with thumbnail removal)**
- [ ] **Step 5: Build Step 3 (Availability): interactive chips for days, time of day, artist preference, and budget select**
- [ ] **Step 6: Build Step 4 (Contact): input fields (56px tall, 18px text, 1px ash border, 3px brass focus ring), +64 mobile hint, custom checkboxes, and interactive enquiry summary box with edit links**
- [ ] **Step 7: Build self-drawing SVG checkmark success state hidden with `[hidden]{display:none !important}` until form completion**
- [ ] **Step 8: Add mobile sticky bottom Back/Continue action bar and smooth scroll triggers from all "Book a consult" buttons**

---

### Task 7: Comprehensive Multi-Breakpoint Testing & Final Verification (Part G)
**Files:**
- Create: `scratch/audit_luxury_upgrade.js`
- Test: Viewports 390x844, 768x1024, 1366x768, 1440x900, 1920x1080

- [ ] **Step 1: Test 0 console errors, 0 broken images, and 0 horizontal overflow**
- [ ] **Step 2: Measure and verify all section gaps <= 96px on desktop, <= 64px on mobile**
- [ ] **Step 3: Verify 100svh fit for studio intro and work rail across laptop and desktop**
- [ ] **Step 4: Test booking wizard validation, step transitions, drag-and-drop reference uploads, and success view**
- [ ] **Step 5: Visual inspection with browser subagent across the entire page**
