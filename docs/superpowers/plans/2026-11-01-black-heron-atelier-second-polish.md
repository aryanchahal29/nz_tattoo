# Black Heron Tattoo Atelier - Second Polish Pass Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Execute second surgical polish pass on `index.html`: replace studio intro photo with authentic tattoo/piercing studio interior and fit section into 1 screen (100svh); eliminate blank spacing bands between sections with measured gaps ≤96px; rebuild piercing menu as a full-width grid layout with sliding tab indicator and jewellery standard panel; rebuild process section as a 5/7 two-column layout with interactive mini-index; elevate pricing into a sleek rate sheet and rough estimate guide; restructure footer into a 4-column layout with bulletin form validation; audit responsive layouts.

**Architecture:** Single-file application in `index.html` referencing verified local assets in `assets/images/`. Animations powered by GSAP 3.12.5 and ScrollTrigger with Lenis smooth scroll.

**Tech Stack:** HTML5, CSS3, JavaScript (ES6+), GSAP 3.12.5 + ScrollTrigger, Lenis 1.1.18.

**Spec:** User Second Polish Pass Prompt (Fixes 1-6, Global Rules, Image Rules, Final Audit).

## Global Constraints
- Do not touch scroll effects of first four sections (hero, marquee, intro, horizontal rail) - motion style must remain identical.
- Do not edit, restyle, or audit the booking wizard; ensure it functions.
- Dark luxury palette: ink (`#0F0E0D`), charcoal (`#171513`), bone (`#EFE8DC`), brass (`#B8975A`), oxblood (`#6B1E24`).
- Headings: Cormorant Garamond 500 (≥32px). Body/UI: Hanken Grotesk 400/500/600.
- All body text 19px desktop / 17px mobile, labels 16px brass, nothing under 15px except legal footer line (14px).
- Every photo must clearly depict tattoo/piercing elements (no generic interiors, no blue/purple cast).
- Gap between content of any two sections ≤ 96px at 1440x900 (≤ 64px on mobile).

---

### Task 1: Fix 1 - Studio Intro Authentic Image & Single-Screen Desktop Layout
**Files:**
- Create: `assets/images/studio_intro.jpg` (verified tattoo studio photo)
- Modify: `index.html` (CSS around `.intro-section`, HTML around `#intro`)

- [ ] **Step 1:** Download and verify a dark, moody photo of a real tattoo atelier bench/chair/machine setup with warm desaturated tones into `assets/images/studio_intro.jpg`.
- [ ] **Step 2:** Refactor `.intro-section` CSS so that on desktop (≥1024px) it fits within `100svh` minus header:
  - Container padding: `clamp(1rem, 2vh, 2.5rem) 0`.
  - Grid: `align-items: stretch` so image height equals text column height.
  - Heading: `clamp(2.2rem, 3.5vw, 3.8rem)`.
  - Trim paragraph to ~45 words.
  - Quote: max 2 lines.
  - Stats: single horizontal row.
- [ ] **Step 3:** Verify in browser at 1440x900, 1366x768, and 1920x1080 that the entire section fits on one screen without scrolling, and stacks on mobile.

### Task 2: Fix 2 - Section Spacing & Root-Cause Gap Remediation
**Files:**
- Modify: `index.html` (CSS section paddings, ScrollTrigger rail end calculation, `.reviews-section` min-height)

- [ ] **Step 1:** Fix work rail ScrollTrigger: set `end: () => "+=" + (grid.scrollWidth - window.innerWidth)` with NO extra offset; vertically center cards in the horizontal rail.
- [ ] **Step 2:** Remove `min-height: 80vh / 100vh` on non-pinned sections (e.g. `.reviews-section`).
- [ ] **Step 3:** Standardize section padding: apply `padding-block: clamp(3rem, 5vw, 4.5rem)` once per section, removing stacked margin-bottoms and divider padding.
- [ ] **Step 4:** Write automated measurement script to calculate content-to-content distance between every section pair at 1440x900 and verify all gaps are ≤ 96px (≤ 64px on mobile).

### Task 3: Fix 3 - Rebuild Piercing Menu as Full-Width Layout
**Files:**
- Modify: `index.html` (Piercing CSS, HTML, and JS)

- [ ] **Step 1:** Rebuild header row: eyebrow "Piercing", heading "The piercing menu" on ONE line (`clamp(2.6rem, 5vw, 4.5rem)`), right-aligned intro "Every piercing uses a single-use sterile needle, in a private room." Remove left sticky column.
- [ ] **Step 2:** Rebuild tabs: horizontal row under header, non-wrapping, 18px, sliding brass underline, with cross-fade (0.5s) on tab switch.
- [ ] **Step 3:** Rebuild table: CSS grid columns `2fr 2.4fr 1.4fr 1.2fr`, 76-84px row height, placement in Cormorant 500 (26px), jewellery in Hanken 17px muted, healing window with hairline bar, price right-aligned ("from" small caps, Cormorant 500 30px), hover 2px brass bar.
- [ ] **Step 4:** Add mobile stacked layout (<768px), "Piercing aftercare" smooth link, and full-width Jewellery Standard panel (3 metal columns + brand names).

### Task 4: Fix 4 - Rebuild Process Section as 5/7 Two-Column Layout
**Files:**
- Modify: `index.html` (Process CSS, HTML, and JS)

- [ ] **Step 1:** Eliminate blank top spacing on `#process`.
- [ ] **Step 2:** Construct two-column layout:
  - Left column (sticky, 5 cols): eyebrow "Methodology", heading "The five-step process", intro, vertical mini-index of 5 step titles (active title bone + brass indicator, clicking scrolls to step).
  - Right column (7 cols): 5 steps along vertical hairline.
- [ ] **Step 3:** Update step items: Cormorant 500 34px title, 18px description (2-3 lines), brass small-caps meta tag.
- [ ] **Step 4:** ScrollTrigger choreography: active step 100% brightness, others 40% opacity, title line reveal, description fade up, dot fill. Verify heading + 3 steps visible together at 1440x900.

### Task 5: Fix 5 - Pricing & Studio Policy Premium Overhaul
**Files:**
- Modify: `index.html` (Pricing CSS, HTML, and JS)

- [ ] **Step 1:** Replace boxed cards with 3-column rate sheet separated by 1px vertical hairlines. Brass label, big Cormorant 500 figure (`clamp(3.2rem, 6vw, 5.5rem)`) with small "NZD", 17-18px description. Figures rise from mask, hairlines draw top to bottom.
- [ ] **Step 2:** Implement "A rough guide" 3-column estimate table with row-by-row reveals (Small piece, Palm-sized, Forearm/calf, Full-day, Half sleeve) + footnote.
- [ ] **Step 3:** Implement 2-column policy block (Cancellation, Touch-up) with 1px brass top hairline, Cormorant 500 28px title, 18px body copy.

### Task 6: Fix 6 - Atelier Bulletin & Structured 4-Column Footer
**Files:**
- Modify: `index.html` (Footer CSS, HTML, and JS)

- [ ] **Step 1:** Rebuild top row: left = eyebrow "Bulletin", heading "Be first when the books open", copy, 56px input + brass JOIN button with fill-wipe, "One email a quarter. Unsubscribe anytime.", JS email validation + "You're on the list." state. Right = "Book a consult" CTA + "Appointment only. Replies within 48 hours."
- [ ] **Step 2:** Rebuild middle 4 columns: Studio (address, hours), Explore (section links), Contact (phone, email, Instagram), Follow (Instagram & Facebook text links).
- [ ] **Step 3:** Implement full-width `BLACK HERON` wordmark at ~14% opacity with clip-path wipe from bottom on entrance.
- [ ] **Step 4:** Bottom bar: © line, "Back to top" smooth scroll link, "Website by Aryan Kumar".

### Task 7: Verification & Multi-Breakpoint Audit
**Files:**
- Run test scripts & browser subagent

- [ ] **Step 1:** Run gap measurement script: verify every section pair gap ≤ 96px at 1440x900.
- [ ] **Step 2:** Browser audit across 1440x900, 1366x768, 1920x1080, 768, and 390.
- [ ] **Step 3:** Verify 0 console errors, 0 broken images, booking wizard works, smooth scrolling throughout.
