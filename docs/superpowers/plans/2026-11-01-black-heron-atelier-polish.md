# Black Heron Tattoo Atelier - Polish & Premium Lift Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Execute a comprehensive surgical polish pass on `index.html`: fix hero meta strip, resolve image loading by bundling local assets into `/assets/images`, prune non-working gallery cards and recalculate horizontal rail pinning, tighten section spacing, ensure all small text is ≥15px (eyebrows 16px brass), lift scroll choreography of sections 5-13 to the premium level of the first four sections, add a 2px brass scroll progress bar, add keyboard focus and reduced motion support, while strictly keeping sections 1-4 and the booking wizard untouched.

**Architecture:** 
Single-file architecture with clean modular sections in `index.html`. Local image assets stored under `assets/images/` and verified. Animations orchestrated via GSAP 3.12.5 and ScrollTrigger using existing easing (`power3.out`, `expo.out`) and duration patterns.

**Tech Stack:** HTML5, CSS3 (Vanilla), JavaScript (ES6+), GSAP 3.12.5 + ScrollTrigger 3.12.5, Lenis 1.1.x.

**Spec:** User Polish Pass Prompt (Parts A, B, C, D).

## Global Constraints
- Do not touch scroll effects of the first four sections (hero, marquee, intro, horizontal rail).
- Do not edit, restyle or audit the booking / appointment enquiry wizard; ensure it functions.
- Dark luxury palette: ink (`#0F0E0D`), charcoal (`#171513`), bone (`#EFE8DC`), brass (`#C5A880`), oxblood (`#5C2424`).
- Headings: Cormorant Garamond (weight 500 for ≥32px). Body/UI: Hanken Grotesk (weight 400, 500, 600).
- No custom cursor, no big section numerals, before/after section stays deleted.
- All typography ≥15px (eyebrow 16px brass, legal line 14px allowed).
- All images must load (local `/assets/images` preferred, eager load in pinned containers, hide card on error).
- Gap between any two sections ≤ 120px on desktop.

---

### Task 1: Image Asset Pipeline & Local Image Curation
**Files:**
- Create: `assets/images/*`
- Modify: `index.html` (image tags, onerror handling, loading attributes)

- [ ] Download verified warm, dark, high-resolution tattoo and studio images into `assets/images/`.
- [ ] Verify every local image file opens and has valid binary dimensions.
- [ ] Update `index.html` `img` tags to point to local assets with `width`, `height`, `aspect-ratio`, and `loading="eager"` for hero and pinned rail.
- [ ] Update `handleImageFallback` and remove `.img-failed::after` "ATELIER WORK ARCHIVE" placeholder text; hide card if image fails.

### Task 2: Fix Hero Meta Strip, Work Rail Pruning & Rail Pin Recalculation
**Files:**
- Modify: `index.html` (Hero CSS, Gallery HTML, Gallery JS)

- [ ] Set hero meta strip to 18px (`1.125rem`), weight 500, letter-spacing 0.12em, bone color at full opacity.
- [ ] Prune empty/non-working gallery cards in `#workRail`, keeping working curated cards.
- [ ] Update work rail width calculation and ScrollTrigger `end: () => "+=" + (workRail.scrollWidth - window.innerWidth)` so pinning matches the exact width without dead space.

### Task 3: Spacing Rhythm & Typography Minimums (≥15px & Eyebrow 16px)
**Files:**
- Modify: `index.html` (CSS Variables, Typography, Section padding)

- [ ] Audit and set section padding-block to `clamp(4rem, 8vw, 7.5rem)` applied once; eliminate double padding between adjacent sections.
- [ ] Ensure gap between any two sections never exceeds 120px on desktop.
- [ ] Set eyebrow labels to 16px (`1rem`), weight 600, letter-spacing 0.14em, brass.
- [ ] Set all other small uppercase text (tags, card meta, captions, footer small text) to minimum 15px (`0.9375rem`). Legal disclaimer in footer set to 14px (`0.875rem`).
- [ ] Verify zero text elements below 15px (except legal 14px).

### Task 4: Lift Scroll Choreography for Later Sections (Sections 5 to 13)
**Files:**
- Modify: `index.html` (HTML structure enhancements where needed, CSS transitions, JS ScrollTrigger choreography)

- [ ] **Artists**: Large portraits with clip-path reveal and gentle parallax; hover image swap to signature work; brass booking-status badge.
- [ ] **Piercing**: Sticky left heading with scrolling right menu; middle-of-screen row brass highlights; hairline draws.
- [ ] **Process**: Pinned sequence with line draw and smooth step transitions (title line mask reveal, description fade up, no numerals).
- [ ] **Pricing & Policies**: Row-by-row reveal, left-to-right hairline draw, soft figure settling.
- [ ] **Clinical Precision / Hygiene**: Full-bleed dark photo with parallax and staggered standard points.
- [ ] **Aftercare**: Scroll-linked background ease from ink to bone; hairline draw; tab changes with cross-fade and smooth height transition.
- [ ] **Reviews**: Pinned scroll sequence showing one large serif quote at a time with cross-fading.
- [ ] **FAQ**: Smooth height-animated accordion with rotating icon and hairline reveal.
- [ ] **Visit**: Grayscale interactive/rich map visual with staggered studio details.
- [ ] **Footer**: Curtain-style reveal as main content lifts away, newsletter input, social links.

### Task 5: Global Polish, Scroll Progress Bar, Accessibility & Audit
**Files:**
- Modify: `index.html` (Progress bar, focus styles, prefers-reduced-motion)

- [ ] Add 2px brass scroll-progress line at top of page (`#scrollProgressBar`).
- [ ] Add consistent hover effects and `:focus-visible` styles for keyboard navigation.
- [ ] Add smooth anchor scrolling and verify all nav links match sections.
- [ ] Add `prefers-reduced-motion` media queries.
- [ ] Call `ScrollTrigger.refresh()` after fonts and images load.
- [ ] Audit at 360px, 390px, 768px, 1280px, 1920px: zero console errors, zero 404s, zero overflow, perfect contrast.
