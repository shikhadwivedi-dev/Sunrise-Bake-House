# Accessibility Audit - Sunrise Bake House

**Site:** Sunrise Bake House (Fictional Bakery)
**Pages Tested:** Home, Services, About, Gallery, Contact (5 pages)
**Tools Used:** Google Chrome Lighthouse, Keyboard Test (Tab / Shift+Tab / Enter), Manual Check
**Date:** November 2026

## Final Scores
- Home: Accessibility 100
- Services: Accessibility 100
- About: Accessibility 100
- Gallery: Accessibility 100
- Contact: Accessibility 100
- axe DevTools: 0 issues
- Keyboard Test: Passed - no focus trap, all controls reachable

## Issue 1: Form inputs had placeholder but no label
**Page:** Contact
**WCAG:** 1.3.1, 3.3.2
**Problem Found:** Initially form inputs only had placeholder text. Placeholder disappears when typing, so screen reader users cannot know the field purpose.
**Fix:** Added visible `<label>` elements linked with `for` / `id` for Name, Phone, Service, Message. Kept placeholders only as examples.
**Result:** Labels now read correctly by screen readers.

## Issue 2: Error messages shown in red colour only
**Page:** Contact
**WCAG:** 1.4.1
**Problem Found:** Error messages were only in red colour. Colour-blind users cannot tell it is an error.
**Fix:** Added the word "Error:" at start of every error message and linked it with `aria-describedby`. Example: "Error: Please enter your name."
**Result:** Error is clear even without colour.

## Issue 3: Focus outline removed on links
**Page:** All pages
**WCAG:** 2.4.7
**Problem Found:** Default browser outline was not visible enough.
**Fix:** Restored a 3px solid outline in brand colour (#7a2e00) with 3px offset for all links, buttons, inputs, textarea and select on `:focus`.
**Result:** Keyboard users can clearly see where they are on the page.

## Issue 4: No way to skip navigation
**Page:** All pages
**WCAG:** 2.4.1
**Problem Found:** Keyboard users had to Tab through all nav links on every page before reaching content.
**Fix:** Added "Skip to main content" link as first element on every page, linking to `<main id="main">`. It appears on focus.
**Result:** Keyboard test passes, user can jump directly to content.

## Issue 5: Images missing alt text
**Page:** Home, About, Gallery
**WCAG:** 1.1.1
**Problem Found:** Some images had no description.
**Fix:** Added meaningful alt text for all informative images. Example: "Chocolate layer cake with chocolate frosting on a plate".
**Result:** Screen reader users get full information.

## Other Checks Passed
- One h1 per page, logical heading order (h1 > h2 > h3)
- Base font size 17px, line-height 1.6, high contrast (dark brown #7a2e00 on white)
- Tables use scope="col" for headers
- Form has success message with role="status" and aria-live="polite"
- No focus trap, Tab order is logical

## Remaining Work
- Add captions if a video is added later.
- Add alt text for any new images added in future.

## Conclusion
All 5 pages now meet basic WCAG 2.2 standards. Lighthouse accessibility score is 100 on all pages. Site is keyboard-friendly and screen-reader friendly.