# Black Heron Tattoo Atelier - Website Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a luxury bespoke demo website for "Black Heron Tattoo Atelier" (Christchurch, NZ) in a single, impeccably structured `index.html` file with dark editorial luxury aesthetics, GSAP + ScrollTrigger, Lenis smooth scroll, responsive mobile-first architecture, and 17 dedicated sections.

**Architecture:** Single self-contained `index.html` containing:
- Semantic HTML with SEO, OpenGraph, JSON-LD schema (type: TattooParlor)
- Config object at the top of `<script>` for instant 2-minute white-label re-branding
- Pure CSS with strict custom property palette, fluid typography via `clamp()`, 12-column grid, zero-radius fill-wipe buttons, fixed SVG turbulence film-grain overlay, and bone/dark alternating section rhythm
- Modular vanilla JavaScript powering Lenis + ScrollTrigger synchronization, clip-path reveals, custom magnetic/canvas cursor, horizontal gallery pin on desktop, interactive before/after comparison sliders with keyboard support, tabbed piercing & aftercare engines, step-by-step booking consultation form with client-side image preview, and accessible accordions

**Tech Stack:** Vanilla HTML5, Vanilla CSS3 (custom properties, clamp, container/grid layouts), Vanilla Modern JS (ES2022+), Google Fonts (Cormorant Garamond + Jost), GSAP 3.12.5, ScrollTrigger 3.12.5, Lenis 1.1.18.

**Spec:** Direct user prompt detailing 17 ordered sections, strict design constraints, copy rules (NZ English, banned words list, cultural sensitivity regarding Māori motifs/tā moko), motion/scroll requirements, and zero-defect accessibility criteria.

## Global Constraints

- Single file delivery: all markup, styles (`<style>`), and scripts (`<script>`) in `index.html`.
- Strict palette: only `--ink: #0F0E0D;`, `--charcoal: #171513;`, `--bone: #EFE8DC;`, `--stone: #8E877B;`, `--brass: #B8975A;`, `--oxblood: #6B1E24;` (no blue, purple, teal, neon, or extraneous gradients).
- Typography: Cormorant Garamond (300/400, italic) for display, leading 0.95–1.05. Jost (300/400/500) for body/UI. Labels: Jost uppercase, 11-12px, letter-spacing 0.18em in brass.
- Fixed SVG film grain overlay (`feTurbulence`) at 4% opacity, `pointer-events: none`.
- Motion: Lenis smooth scroll synced with ScrollTrigger. Easing: `power3.out` or `expo.out` only, durations 0.9–1.4s. Transform and opacity only for 60fps. Full `prefers-reduced-motion` compliance.
- Copy rules: New Zealand English ("colour", "specialise", "programme"). Currency in NZD ("from $250"). Phone in `+64` format. No exclamation marks, no emoji, no banned words ("Elevate", "Unleash", "Welcome to", "Passionate", "State-of-the-art", "journey", "where art meets").
- Respect Māori cultural considerations: zero Māori decorative motifs, tā moko omitted.
- Use `<!-- [CONFIRM] -->` tags for all studio-specific policies, hygiene records, and licensing items.
- Images: Curated high-res Unsplash photos with `alt`, `data-swap`, aspect ratios, and fallback to charcoal grain blocks on error.

## Review Focus

1. **Horizontal Rail on Desktop vs. Vertical Grid on Mobile (Section 5):** Desktop uses pinned GSAP horizontal scroll; mobile (<768px) must seamlessly fall back to an elegant vertical stack without breaking document flow or scroll position.
2. **Before/After Comparison Sliders (Section 6):** Must support touch swipe, mouse drag, and accessible keyboard arrow inputs (`Left`/`Right`/`Home`/`End` with ARIA `aria-valuenow`). Auto-wipe triggers once via ScrollTrigger.
3. **Multi-Step Consultation Form (Section 13):** Clean 4-step wizard with file upload preview, reactive validation, clear progress indicator, accessible field error announcements, and mock submission state with reset.
4. **Header Scroll Direction & Mobile Bottom Bar:** Header disappears on scroll down past 80px and reappears on scroll up with solid ink background. Mobile sticky bottom bar appears after hero and hides near the booking form to prevent overlap.
5. **Accessibility & Keyboard Navigation:** Lightbox (Esc, arrow keys, focus trap), FAQ accordion (`aria-expanded`, keyboard enter/space), tabbed piercing/aftercare components (`role="tablist"`), and custom cursor disabled on touch devices.

---

### Task 1: HTML Document Foundation, Metadata, Design Tokens & Global CSS

**Files:**
- Create: `index.html`

**Interfaces:**
- Produces: Base HTML5 structure, SEO meta tags, OpenGraph tags, JSON-LD `TattooParlor` schema, CSS custom properties, typography imports, SVG filter for film grain, utility classes, and reset.

- [ ] **Step 1: Scaffolding HTML5 structure with SEO & JSON-LD**
  Define `<head>` with character set, viewport, title "Black Heron Tattoo Atelier | Fine Art Tattoo & Body Piercing Christchurch NZ", description, Open Graph metadata, canonical link, and JSON-LD schema with address, coordinates, opening hours, and price range.
- [ ] **Step 2: External CDNs & Font Links**
  Add preconnect and font links for Cormorant Garamond and Jost. Add CDN script tags for Lenis (1.1.18), GSAP (3.12.5), and ScrollTrigger (3.12.5).
- [ ] **Step 3: Global CSS Custom Properties & Base Styling**
  Write CSS variables (`--ink`, `--charcoal`, `--bone`, `--stone`, `--brass`, `--oxblood`, `--font-display`, `--font-body`). Configure SVG feTurbulence grain overlay, box-sizing, smooth font rendering, focus-visible styles, custom cursor styling, and button fill-wipe states.
- [ ] **Step 4: Image Error Handling & Fallback Helper**
  Add global CSS for `.image-container` and fallback script to replace failed images with charcoal grain blocks.
- [ ] **Step 5: Verify Base Layout in Browser**
  Verify document parses without console errors and fonts load correctly.

---

### Task 2: Studio CONFIG Object & Core Navigation Components

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: Base structure from Task 1.
- Produces: `CONFIG` object at top of `<script>` tag, dynamic DOM hydration functions for brand strings, responsive header (Section 1), mobile sticky bottom CTA, and hero curtain reveal element.

- [ ] **Step 1: Write Studio CONFIG Object**
  Include `studioName`, `tagline`, `city`, `suburb`, `address`, `phone`, `email`, `instagram`, `hours`, `depositAmount`, `minimumCharge`, `artists`, and `piercingPrices`.
- [ ] **Step 2: Section 1 - Header Navigation Markup & Styles**
  Build `<header>` with SVG wordmark logo left, semantic `<nav>` (Work, Artists, Piercing, Process, Aftercare, FAQ), and "Book a consult" primary CTA right. Include mobile hamburger drawer.
- [ ] **Step 3: Header Scroll Behavior & Mobile Bottom CTA**
  Implement header scroll logic (transparent at top, solid ink after 80px, hide on scroll down, reveal on scroll up). Implement mobile sticky bottom "Book a consult" bar that triggers after hero and hides near booking form.
- [ ] **Step 4: Verify navigation links, mobile menu toggle, and scroll header triggers.**

---

### Task 3: Hero Section & Marquee Strip (Sections 2 & 3)

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: CSS tokens and Lenis/GSAP setup.
- Produces: Section 2 (Hero 100svh with mask reveal, parallax scale, scroll hairline cue) and Section 3 (Marquee ticker with velocity boost).

- [ ] **Step 1: Section 2 - Hero Markup & Styles**
  100svh dark container with full-bleed atmospheric tattoo atelier background image, huge Cormorant Garamond display headline split in 2-3 lines with overflow masks, brief italicized copy line, magnetic primary button, "Est. 2012", "Christchurch", "By appointment", and vertical hairline "Scroll" cue.
- [ ] **Step 2: Hero Intro Timeline & Pinning Animation**
  GSAP timeline lifting the ink curtain (<1.2s), fading in wordmark, staggering line reveals (0.08s). ScrollTrigger pin for ~100vh of scroll that scales background (1.12 to 1), deepens dark overlay, and gently drifts headline lines apart.
- [ ] **Step 3: Section 3 - Marquee Strip**
  Build marquee strip with text: `Fine line · Blackwork · Japanese · Colour · Cover-ups · Piercing`. Add seamless infinite CSS animation and ScrollTrigger velocity detection to accelerate smoothly on fast scroll.
- [ ] **Step 4: Verify hero entry, pinning, and marquee fluidity.**

---

### Task 4: Studio Intro & Selected Work Gallery with Lightbox (Sections 4 & 5)

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: Config data, GSAP ScrollTrigger.
- Produces: Section 4 (Intro split layout with counter animations) and Section 5 (Filterable 12-piece gallery with desktop horizontal pin rail and interactive accessible lightbox).

- [ ] **Step 1: Section 4 - Studio Intro**
  Build asymmetric split layout: left column editorial atelier interior photo with clip-path reveal and gentle parallax; right column section numeral `01`, label `ATELIER PHILOSOPHY`, serif heading, calm narrative copy in NZ English, large italic pull quote, and 3 counters (Years Operating: 14, Resident Artists: 3, Sessions Annually: 850+).
- [ ] **Step 2: Counter Animation Logic**
  ScrollTrigger triggers numerical counter rollup with easing on first entry.
- [ ] **Step 3: Section 5 - Selected Work Gallery**
  Build category filter bar (All / Fine line / Blackwork / Japanese / Colour / Cover-ups) with 12 curated pieces. Each card features image, style, artist name, and hover view badge.
- [ ] **Step 4: Horizontal Scroll Rail on Desktop & Vertical on Mobile**
  Implement GSAP ScrollTrigger horizontal scroll pinning on desktop (`window.innerWidth >= 1024px`) with graceful fallback to responsive grid on tablet and mobile.
- [ ] **Step 5: Accessible Lightbox Modal**
  Implement modal with high-res preview, artist name, style, placement, session length, close button, Esc key listener, left/right keyboard navigation, and focus trapping.
- [ ] **Step 6: Verify gallery filtering, horizontal track, and lightbox accessibility.**

---

### Task 5: Before & After Drag Sliders and Artists Showcase (Sections 6 & 7)

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: Artist data from `CONFIG`.
- Produces: Section 6 (3 Before/After comparison sliders) and Section 7 (Artist profiles with hover portrait swap).

- [ ] **Step 1: Section 6 - Before & After Comparison Component**
  Build 3 comparison cases: 1) Cover-up transformation, 2) Fresh day-1 vs Healed 8-week fine line, 3) Japanese sleeve rework. Each case has two overlapping images with clip-path divider, interactive drag handle, and keyboard accessibility (arrow keys adjusting percentage, `aria-valuenow`). Include metadata captions (style, session count, total hours).
- [ ] **Step 2: Auto-Wipe ScrollTrigger Animation**
  When Section 6 scrolls into viewport, execute a subtle 0% -> 60% -> 50% auto-wipe animation once to guide user discovery.
- [ ] **Step 3: Section 7 - Artists Showcase**
  Section numeral `03`, headline, and 3 artist cards dynamically/statically populated from `CONFIG.artists`. Large portrait (4:5 ratio), artist name, specialty, experience years, current booking status ("Books open: March"), and portfolio trigger. On mouse hover, smoothly cross-fade to a signature tattoo piece by that artist.
- [ ] **Step 4: Verify drag sliders on mobile touch & desktop mouse, and artist card hover states.**

---

### Task 6: Piercing Menu, 5-Step Process & Pricing/Hygiene Sections (Sections 8, 9, 10, 11)

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: Piercing data from `CONFIG`, ScrollTrigger scrub engine.
- Produces: Section 8 (Piercing tabbed menu), Section 9 (Process vertical scroll line), Section 10 (Transparent pricing), and Section 11 (Hygiene and safety).

- [ ] **Step 1: Section 8 - Piercing Tabbed Menu**
  Tabs for Ear, Face, Body (`role="tablist"`). Placements with starting price in NZD ("from $90"), healing times, and quality note regarding implant-grade ASTM F-136 titanium and 14k/18k solid gold jewellery.
- [ ] **Step 2: Section 9 - Process with Vertical Drawing Hairline**
  5 steps: 1) Enquire, 2) Consult and design, 3) Deposit and date, 4) Session, 5) Aftercare and touch-up. Left vertical hairline indicator that draws downward on scroll scrub (`scaleY: 0` to `1`), turning each completed step marker from stone to brass as scroll passes.
- [ ] **Step 3: Section 10 - Pricing and Policy**
  Minimalist luxury table/grid: Minimum Charge ($180 NZD), Hourly Range ($200–$250/hr), Deposit Amount ($100–$300 non-refundable), Cancellation Window (72 hours notice required), and Complimentary Touch-up Policy (within 6 months).
- [ ] **Step 4: Section 11 - Hygiene & Studio Standards**
  Autoclave sterilization, hospital-grade disinfectants, 100% single-use needles and cartridges, Ministry of Health / Council compliance notices with `<!-- [CONFIRM] -->` studio placeholder marks.
- [ ] **Step 5: Verify tab accessibility, scrub line animation, and layout clarity.**

---

### Task 7: Aftercare Guide, 4-Step Consultation Booking Form & Reviews (Sections 12, 13, 14)

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: Config data, booking state engine.
- Produces: Section 12 (Aftercare in bone background), Section 13 (4-step booking wizard with image upload preview), and Section 14 (Reviews).

- [ ] **Step 1: Section 12 - Aftercare Guide (Bone Background)**
  Alternate background to `--bone` with contrasting `--charcoal` text for visual rhythm. Tabs for Tattoo, Piercing, Cover-up. Chronological stages: Day 1–3, Week 1–2, Week 3–4, Long-term care. "When to contact us" cautionary callout box and "Download aftercare card" button placeholder.
- [ ] **Step 2: Section 13 - 4-Step Booking Enquiry Form**
  Return to dark background. Progress bar with 4 steps:
  - Step 1: Service selection (Tattoo, Piercing, Cover-up, Not sure)
  - Step 2: Tattoo/Piercing Details (Idea summary, preferred style, placement, dimensions, budget, file drag-and-drop reference upload with client-side image thumbnail preview)
  - Step 3: Artist preference, availability, and client contact details (+64 phone format, email, name)
  - Step 4: Deposit explainer ($150 NZD applied to final session), consultation agreement checkbox, review summary, and submission button
  Include inline client-side validation, error messages, and elegant animated success message with reset option (annotated: `// Demo only: nothing is sent`).
- [ ] **Step 3: Section 14 - Client Reviews**
  3 understated luxury editorial quotes with client name and artist attribution, plus "4.9 on Google (180+ verified studio reviews)" marked with comments.
- [ ] **Step 4: Verify form step transitions, file preview, validation, and success screen.**

---

### Task 5: FAQ Accordion, Visit/Studio Location, Luxury Footer & Cursor Motion (Sections 15, 16, 17)

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: Contact info from `CONFIG`, GSAP cursor controller.
- Produces: Section 15 (FAQ Accordion), Section 16 (Visit & Map), Section 17 (Footer), Desktop custom cursor, and Lenis/ScrollTrigger final synchronization.

- [ ] **Step 1: Section 15 - FAQ Accordion**
  Accessible accordion (`aria-expanded`, `aria-controls`) answering: Minimum age (18+ for tattoos, ID required), Pain management, Cost estimates, Deposit policy, Cancellations/Rescheduling, Complimentary touch-ups, Cover-up viability, Bringing a guest, Numbing cream policy, Walk-ins vs appointments, Studio accessibility.
- [ ] **Step 2: Section 16 - Visit & Contact Studio**
  Studio address in Christchurch (Victoria Street / Arts Centre quadrant), opening hours, parking & transit advice, stylized dark-mode map embed/mockup, phone link (+64 3 ...), Instagram handle, and direct directions link.
- [ ] **Step 3: Section 17 - Editorial Luxury Footer**
  Oversized serif wordmark "BLACK HERON", newsletter subscription input with fill-wipe submit button, social links (Instagram, Facebook) with clean inline SVGs, copyright, and subtle attribution "Website by Aryan Kumar".
- [ ] **Step 4: Custom Desktop Cursor & Magnetic CTA Effect**
  Desktop-only (`pointer: fine`) custom cursor: small brass hairline ring that follows mouse smoothly, expanding and displaying "VIEW" over gallery/slider items. Magnetic pull effect on primary hero and header CTA buttons.
- [ ] **Step 5: Verify FAQ accordion keyboard controls, map styling, footer layout, and cursor performance.**

---

### Task 9: Comprehensive Creative Director Audit, Cross-Device Polish & Verification

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: Complete page implementation.
- Produces: Fully verified, zero-defect production-ready demo website.

- [ ] **Step 1: Lenis & ScrollTrigger Integration Audit**
  Verify smooth scrolling is fluid at 60fps, anchor links smoothly glide to targets, and no scroll jump or layout shift occurs.
- [ ] **Step 2: Responsive Breakpoint Verification (360px to 1920px)**
  Test on 360px mobile, 390px iPhone, 768px tablet, 1024px iPad Pro/laptop, and 1920px widescreen using browser inspection. Ensure no horizontal overflow, tap targets >= 44px, and mobile sticky CTA functions seamlessly.
- [ ] **Step 3: Copy, Culture, and Tone Review**
  Audit text against banned words ("Elevate", "Unleash", "Welcome to", "Passionate", "State-of-the-art", "journey", "where art meets"), ensure New Zealand spelling ("colour", "specialise"), verify no exclamation marks or emojis, verify tā moko is excluded, and verify `[CONFIRM]` comments exist on studio specifics.
- [ ] **Step 4: Accessibility & Reduced Motion Audit**
  Test keyboard navigation (Tab, Enter, Space, Escape, Arrows) through lightbox, before/after slider, tabs, and accordions. Verify `@media (prefers-reduced-motion: reduce)` disables Lenis, pinning, and parallax while maintaining elegant opacity transitions.
- [ ] **Step 5: Browser Subagent Verification & Video Capture**
  Run browser test to inspect console errors, render quality, interactions, and confirm flawless presentation.
