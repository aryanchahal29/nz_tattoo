# Black Heron Tattoo & Piercing Atelier — Light Minimal Re-Theme Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Transform the Black Heron website into a light, minimal, trust-first luxury aesthetic while strictly preserving all existing Lenis + GSAP ScrollTrigger motion choreographies (pinned hero, clip reveals, velocity marquee, pinned work rail, process line draw, header hide/show, scroll-progress line).

**Tech Stack:** Vanilla HTML5, Vanilla CSS3 (no frameworks/Tailwind), JavaScript ES6+, GSAP 3.12.5 + ScrollTrigger, Lenis 1.1.18.
**Fonts:** Anton (Headlines), Allura (Script accent), Barlow 400/500/600 (Body/UI).

---

### Key Requirements & Constraints
1. **Palette:**
   - `--paper: #FFFFFF;`
   - `--paper-2: #F5F3EF;` (alternate section background)
   - `--ink: #0B0B0B;`
   - `--ash: #4A4A4A;` (secondary text)
   - `--line: #DAD6CF;` (hairlines)
   - `--red: #B5121B;` (accent for progress bar, dots, link underlines, button wipe)
2. **Typography:**
   - Anton for headlines: line-height 0.95, uppercase. Hero clamp(4rem, 12vw, 11rem), section titles clamp(2.8rem, 7vw, 6rem).
   - Allura script: exactly ONE word in hero ("atelier") and ONE in pricing heading (never below 4rem).
   - Barlow 400/500/600 for body and UI: body 19px, line-height 1.65, max 62ch; labels 16px uppercase, letter-spacing 0.12em.
3. **Photos:**
   - All photos black-and-white (`filter: grayscale(1) contrast(1.08) brightness(0.95)`).
   - Each photo clearly relates to tattooing or piercing (benches, gloved hands, machines, ear/face jewellery).
   - At least 40% of photos depict piercing.
4. **Sections (Strictly 14 sections in order):**
   1. Header
   2. Hero (pinned)
   3. Marquee strip
   4. Studio intro (fits in 1 screen on desktop)
   5. Two disciplines (side-by-side Tattoo & Piercing panels)
   6. Selected work (pinned horizontal rail with 8 pieces, 3 piercings, lightbox intact)
   7. The standard (trust band with 4 hand-drawn tattoo-flash SVG icons & engraved flourish)
   8. Artists (3 black-and-white portraits: 2 tattoo, 1 piercing)
   9. Process (4 horizontal steps along drawing hairline with red dots)
   10. Pricing (2 columns: Tattoo rate sheet + Piercing list in 2 sub-columns + 2 policies)
   11. Reviews (4.9 Google rating + 3 quote cards)
   12. FAQ (6 accordion items)
   13. Booking enquiry (re-skinned to light palette only; structure/fields untouched)
   14. Footer (4 columns, huge BLACK HERON wordmark, back to top, copyright)
5. **No empty frames, no custom cursor, section gaps ≤ 96px desktop (≤ 64px mobile).**

---

### Task Breakdown

- [ ] **Task 1: Prepare and verify image assets (at least 40% piercing)**
  - Ensure high-resolution black-and-white images for hero, intro, two disciplines, 8 work rail pieces (3 piercings), standard band, and 3 artists.
  - Verify every image relates to tattooing or piercing, with width/height/alt.

- [ ] **Task 2: Design original SVG flash icons & engraved flourish**
  - Draw 4 custom tattoo-flash style line icons for "The Standard":
    1. Sterile single-use (needle cartridge / autoclave blister)
    2. Implant-grade jewellery (threaded labret / ball & captive ring)
    3. Drawn for you (stencil quill / fine-line botanical flash needle)
    4. Free touch-up (healed droplet / dual cross star)
  - Draw 1 fine-line engraved flourish for the bottom edge of the standard band.

- [ ] **Task 3: Implement new Design Tokens & Typography in CSS**
  - Import Anton, Allura, Barlow from Google Fonts. Remove Cormorant & Hanken.
  - Define `--paper`, `--paper-2`, `--ink`, `--ash`, `--line`, `--red`.
  - Re-theme global buttons (black fill with red fill-wipe on hover, white on photo bands).
  - Update scroll-progress line to 2px red.

- [ ] **Task 4: Build Sections 1–5 (Header, Hero, Marquee, Intro, Two Disciplines)**
  - Header: Anton wordmark with "Tattoo & Piercing" subtext, navigation, consult button.
  - Hero: Pinned full-bleed photo, Anton headline with Allura script "atelier", dual CTA buttons, 18px meta strip.
  - Marquee: Thin white strip with Anton uppercase text and scroll velocity.
  - Intro: 1 screen desktop fit, black-and-white studio bench photo, 40-word text, 3 stats.
  - Two Disciplines: Side-by-side TATTOO and PIERCING panels with hover zoom and red drawing line.

- [ ] **Task 5: Build Sections 6–10 (Work Rail, Standard Band, Artists, Process, Pricing)**
  - Selected Work: Pinned horizontal rail with 8 pieces (3 piercings), caption with style and hours, lightbox intact.
  - The Standard: Full-bleed photo with 50% dark overlay, 4 flash SVG icon columns, engraved flourish.
  - Artists: 3 black-and-white portraits (Caleb Vance, Maren Croft, Elena Thorne - Piercing), parallax reveals.
  - Process: 4 horizontal steps along drawing hairline with red dots, Anton titles, ≤18-word descriptions.
  - Pricing: 2 columns with Allura script accent; Tattoo rates on left, Piercing 2-subcolumn list on right, 2 policies.

- [ ] **Task 6: Build Sections 11–14 (Reviews, FAQ, Booking Re-skin, Footer)**
  - Reviews: 4.9 on Google, 3 quotes in a row on paper-2.
  - FAQ: 6 smooth accordion items.
  - Booking Wizard: Re-skin only using new CSS variables (white/paper-2/ink/line/red). Structure untouched.
  - Footer: 4 columns, huge BLACK HERON wordmark with clip wipe, bottom bar.

- [ ] **Task 7: Visual & Gap Audit Across 5 Breakpoints**
  - Measure all section pair visible gaps at 1440×900 (≤96px) and 390×844 (≤64px).
  - Verify 0 console errors, 0 broken images, 0 horizontal overflow.
  - Confirm booking wizard functions flawlessly.
