# Header Refinement Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Refine the atelier header to be fully transparent at top of page over the hero with a 140px soft gradient scrim, transition to solid ivory with height shrinking from 96px to 76px after 80px of scroll, maintain hide/show scroll behavior, support mobile drawer open state (ink background, ivory text), prevent mid-page flash on reload/hash navigation, and respect prefers-reduced-motion.

**Architecture:** Update CSS custom properties, header styles, and pseudo-element scrim in `index.html`. Add an early inline script to `index.html` within `<header>` for zero-flash initial state detection, and enhance `initHeaderScroll()` with passive scroll handling and `requestAnimationFrame`. Update `initMobileMenu()` to manage `.menu-open` class.

**Tech Stack:** Vanilla HTML5, CSS Custom Properties, Vanilla JavaScript (ES6+), GSAP / Lenis integration.

**Spec:** Direct user task requirements for header behavior and styling.

## Global Constraints
- Change the header only. Do not change any other sections on the site.
- Header height: 96px at top (scrollY < 80px), 76px after 80px of scroll.
- Scrim: 140px tall linear-gradient from rgba(14,12,11,0.55) to transparent.
- No blur and no backdrop-filter on header.
- Scrolled state after 80px: solid --ivory, 1px bottom hairline rgba(14,12,11,0.12), ink text, ink button with ivory text.
- Transitions: 0.35s ease on background-color, color, border-color, and height.
- Hide on scroll down (> 150px), show on scroll up.
- Mobile menu open: ink background and ivory text regardless of scroll position.
- Logo: single text or SVG element colored through CSS variables (no duplicate images).
- Loader sequence unchanged: header still fades down at the end of it.
- Respect prefers-reduced-motion (no transitions).
- Zero jump in hero content across viewports (390, 768, 1366, 1920).

## Review Focus
1. Hero content jumping: ensure hero content does not shift when header changes height from 96px to 76px.
2. Refresh / Hash navigation flash: ensure mid-page reload or #work link loads with solid header immediately without transparent flicker.
3. Contrast on hero photo: ensure ivory text over the 140px scrim remains legible against bright photo areas.
4. Mobile menu state: verify hamburger icon, wordmark, and tagline turn ivory and header turns ink when menu is opened at scroll = 0 or scrolled.
5. Reduced motion: verify all transitions are disabled under `prefers-reduced-motion: reduce`.

---

### Task 1: Update Header CSS in index.html

**Files:**
- Modify: `index.html:525-650`

- [ ] **Step 1: Replace header CSS styles with new transparent top, 140px scrim, solid scrolled state, mobile menu open state, and reduced-motion media query.**
- [ ] **Step 2: Verify CSS syntax and classes.**

---

### Task 2: Update Header HTML Markup in index.html

**Files:**
- Modify: `index.html:3420-3455`

- [ ] **Step 1: Add inline zero-flash detection script inside `<header class="site-header" id="siteHeader">`.**
- [ ] **Step 2: Add `header-consult-btn` class to the "Book a consult" button and clean inline style overrides.**

---

### Task 3: Update Header & Mobile Menu JavaScript in index.html

**Files:**
- Modify: `index.html:5350-5375` (Header Scroll Controller)
- Modify: `index.html:6355-6375` (Mobile Menu Controller)

- [ ] **Step 1: Update `initHeaderScroll()` to manage `is-scrolled` (scrollY >= 80px) and `is-hidden` (scroll direction) with rAF.**
- [ ] **Step 2: Update `initMobileMenu()` to toggle `.menu-open` on `#siteHeader`.**

---

### Task 4: Automated Verification Across Viewports & States

**Files:**
- Create: `scratch/verify_header.py`
- Test: Viewports 390x844, 768x1024, 1366x768, 1920x1080; scroll >= 80px; hash navigation; mobile menu open; reduced motion.

- [ ] **Step 1: Write Selenium verification script checking header dimensions, colors, scrim, hero stability, and mobile menu states.**
- [ ] **Step 2: Execute script and confirm all checks pass.**
- [ ] **Step 3: Capture and inspect screenshots.**

---

### Task 5: Git Commit & Push to GitHub

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Commit changes with clear message.**
- [ ] **Step 2: Push to `origin/main` on GitHub.**
- [ ] **Step 3: Verify GitHub Pages deployment.**
