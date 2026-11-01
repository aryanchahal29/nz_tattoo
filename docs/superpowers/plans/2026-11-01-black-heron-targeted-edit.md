# Black Heron Tattoo & Piercing Targeted Edit Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Execute a surgical, targeted edit of the existing Black Heron site addressing 5 specific areas (Hero cleanup, Selected Work full-color Instagram-feed strip, The Standard editorial redesign on bone, Resident Artists 3-in-a-row grid, and Footer overhaul with credit removal) while keeping all existing Lenis and GSAP ScrollTrigger choreography, easings, fonts, palette, booking wizard, and section order intact.

**Architecture:** Edit `index.html` (single-file architecture with inline `<style>` and `<script>` blocks). Generate 12 full-color portfolio images (7 tattoo, 5 piercing) and 1 sterile setup photo into `assets/images/work/` and `assets/images/`, inspect all images to verify zero ambiguity, remove all mentions of "Aryan Kumar", rebuild the targeted HTML/CSS/JS sections, and run an automated Playwright audit across 5 viewports (390, 768, 1366, 1440, 1920) to ensure zero console errors, zero broken images, zero horizontal scroll, and flawless responsiveness.

**Tech Stack:** Vanilla HTML5, Vanilla CSS, Vanilla JavaScript (ES6+), GSAP 3.12.5 + ScrollTrigger, Lenis 1.1.x, Playwright for automated multi-viewport testing.

**Spec:** User prompt requirements for Tasks 1 through 7.

## Global Constraints
- Preserve Anton + Barlow + Allura fonts and typography scale.
- Palette remains `--ivory #F7F2EA`, `--bone #EDE4D6`, `--ink #0E0C0B`, `--oxblood #5A0F1B`, `--crimson #B5121B`, `--brass #B8975A`, `--ash #4A4238`.
- Section order preserved: Hero -> Marquee -> Studio Intro -> Two Disciplines -> Selected Work -> The Standard -> Artists -> Process -> Pricing -> Reviews -> FAQ -> Booking -> Footer.
- Section gaps strictly <= 96px on desktop (<= 64px on mobile).
- No custom cursor, no magnetic effects, no big numerals, zero blue or purple.
- Do NOT touch hero scroll behavior, marquee, studio intro, two disciplines, process, pricing, reviews, FAQ, or the 4-step booking form wizard.
- Remove author credit "Aryan Kumar" completely from HTML comments, meta tags, JSON-LD, body text, and scripts.

## Review Focus
1. Hero buttons have >= 48px space below them at 1366x768, 1440x900, 1920x1080 without pill and bottom strip.
2. Selected Work section background is `--ink #0E0C0B` with 12 full-color photos (7 tattoo, 5 piercing) in 3:4 portrait tiles, zero beige bars, and clean hover overlay with style/placement/hours and Instagram icon.
3. The Standard is on `--bone` with sterile setup photo on left (5/12) and 2x2 grid with SVG self-drawing circle icons on right (7/12).
4. Resident Artists section displays all 3 artists side by side in a 3-column grid on desktop (>= 1024px) with no sticky stacking and portrait height <= 52svh so heading and cards fit at 1440x900.
5. Footer is an `--ink` band with live NZ opening hours, brass script "ready", 4-column layout, large "BLACK HERON" wordmark, and 0 occurrences of "Aryan Kumar".

---

### Task 1: Generate & Verify 13 Full-Color High-Resolution Images
**Files:**
- Create: `assets/images/work/` directory
- Create: `assets/images/work/work_tattoo_1.jpg` through `work_tattoo_7.jpg` (7 styles: fine line florals, blackwork, Japanese, neo-traditional, realism, lettering, color botanical)
- Create: `assets/images/work/work_piercing_1.jpg` through `work_piercing_5.jpg` (5 styles: ear stack, helix/conch, septum, nostril, navel)
- Create: `assets/images/standard_sterile_setup.jpg` (sterile single-use needles and titanium tray)

- [ ] Generate 7 full-color tattoo photos showing clear tattoos on skin.
- [ ] Generate 5 full-color piercing photos with clearly visible jewellery.
- [ ] Generate 1 sterile setup photo for The Standard.
- [ ] Inspect every generated image with `view_file` to confirm: stranger instantly identifies tattoo or piercing, no anime/castles/drawings, no blue/purple cast, no Māori/Polynesian patterns.

### Task 2: Item 1 - Hero Cleanup & Spacing Adjustment
**Files:**
- Modify: `index.html` (Hero HTML, CSS, JS)

- [ ] Delete "NOW BOOKING: NOV / DEC" pill markup, CSS, pulsing animation, and JS.
- [ ] Delete 4-item bottom trust strip markup, CSS, and JS.
- [ ] Adjust hero CTA group margins/padding so buttons have at least 48px clearance to the bottom of the viewport at 1366x768, 1440x900, and 1920x1080.
- [ ] Maintain hero headline, Allura "atelier" script, intro line, rotating circular badge, slow zoom, pin, and scale.

### Task 3: Item 2 - Selected Work Instagram-Feed Strip & Lightbox Integration
**Files:**
- Modify: `index.html` (Work Section HTML, CSS, JS, artworkData array)

- [ ] Update section background to `--ink #0E0C0B` (full-bleed).
- [ ] Update header to ivory text: Eyebrow "Portfolio", Heading "SELECTED WORK", and outlined ivory button "Follow @blackheronatelier" with inline SVG Instagram glyph.
- [ ] Replace 8 old cards with 12 3:4 portrait tiles (`height: min(58svh, 560px)`, 14px gap, 1px ivory border at 70% opacity, 0 radius, no text box under image, `loading="eager"`).
- [ ] Apply full-color styling: remove grayscale/sepia filters for `.work-gallery-card img`, set `filter: contrast(1.05) saturate(1.05)`.
- [ ] Implement hover overlay: image scale 1.05, bottom dark gradient with style, placement, hours, and center ivory Instagram glyph. Piercing tiles highlight "Piercing" in crimson.
- [ ] Update `artworkData` array with 12 color items, and connect to existing lightbox modal.

### Task 4: Item 3 - The Standard Redesign (Light Editorial Split on Bone)
**Files:**
- Modify: `index.html` (The Standard HTML, CSS, JS)

- [ ] Remove muddy oxblood photo background, oxblood multiply tint, and small ornament.
- [ ] Set section background to `--bone #EDE4D6` with dark ink text.
- [ ] Build left column (5/12): full-color `standard_sterile_setup.jpg` with clip-path reveal, gentle parallax, 1px brass offset frame (16px offset), and caption "Opened in front of you".
- [ ] Build right column (7/12): Eyebrow "The standard", Anton heading "WHAT YOU CAN COUNT ON", 20px intro line "Clinical safety, implant-grade materials and honest craft."
- [ ] Build 2x2 grid separated by 1px hairlines: each cell has 56px circle line icon with 1.5px ink stroke and brass dot (stroke-dashoffset on enter), Anton 26px title, and <= 20 words copy for all 4 items.
- [ ] Add bottom credentials row: "Autoclave sterilised · Single-use needles · Implant-grade metals" separated by brass dots.

### Task 5: Item 4 - Resident Artists (3 Columns in One Row on Desktop)
**Files:**
- Modify: `index.html` (Artists HTML, CSS, JS)

- [ ] Remove sticky stacking scroll behavior and pinning JS.
- [ ] Style desktop (>= 1024px) as a 3-column grid in one row with 32px gap.
- [ ] Card layout: 4:5 portrait, Anton name, discipline, years, booking status, and "View portfolio →" link.
- [ ] Constrain portrait height to `max-height: min(52svh, 480px)` so heading and all 3 cards fit in 1440x900 viewport.
- [ ] Style tablet & mobile (< 1024px) as a horizontal swipe row with scroll-snap, cards 82% wide.
- [ ] Preserve current artist photos, hover reveal to signature work, clip-path reveal, and 0.12s column stagger. Ensure no pin spacer or extra scroll distance remains.

### Task 6: Item 5 - Footer Overhaul & Credit Removal
**Files:**
- Modify: `index.html` (Footer HTML, CSS, JS, `<head>` tags)

- [ ] Search and purge all occurrences of "Aryan Kumar" from author meta tags, HTML comments, and body copy.
- [ ] Style footer as an `--ink` band with ivory text.
- [ ] Top row: Anton "READY WHEN YOU ARE." with brass Allura "ready" (>= 4rem), "Book a consult" button with ivory fill/ink text/brass wipe, and clickable phone `+64 3 379 8421`.
- [ ] Middle row: 4 columns separated by 1px hairlines at 15% opacity:
  - Studio: Address & "Get directions →"
  - Hours: Tue–Sat 11:00 am – 7:00 pm, Sun–Mon closed, and dynamic Pacific/Auckland live status ("Open today until 7:00 pm" or "Closed today")
  - Follow: Instagram and Facebook with inline SVGs and text labels
  - Consultation: "Appointment only. Replies within 48 hours." & "Send an enquiry" link
- [ ] Bottom: Huge "BLACK HERON" wordmark ivory 10-12% opacity cropped 20% by bottom edge with clip-path wipe.
- [ ] Bottom bar: © line and "Back to top ↑" only.

### Task 7: Multi-Viewport Audit & Verification
**Files:**
- Create: `scratch/audit_targeted_edit.js`
- Test viewports: 390x844, 768x1024, 1366x768, 1440x900, 1920x1080

- [ ] Verify 0 occurrences of "Aryan Kumar".
- [ ] Verify Hero has no pill and no bottom strip; buttons have >= 48px space below them.
- [ ] Verify all 12 Selected Work images load in full color with zero broken images.
- [ ] Verify The Standard has light bone background and 2x2 grid.
- [ ] Verify Resident Artists are 3 in one row on desktop without sticky stacking.
- [ ] Verify live NZ studio hours in footer.
- [ ] Verify 0 console errors, 0 broken images, 0 horizontal overflow.
- [ ] Verify section gaps <= 96px desktop / <= 64px mobile.
