# Handoff: portfolio work in progress

Notes for picking this up in a new Claude Code session (e.g. on Windows).
Start the session in this repo folder and say: **"Read HANDOFF.md and continue."**

## What this repo is

A static HTML portfolio (no build step). It's served by GitHub Pages from `main`
(see `CNAME`), so **pushing to `main` updates the live site**.

To preview locally, in this folder run one of these, then open http://localhost:8000:

- `python -m http.server 8000` (Windows)
- `python3 -m http.server 8000` (Mac)

## Changes made (all in `index.html`)

**Header / nav**
- Removed the thin line under the header strip. Its bottom edge now feathers out over about 26px instead of a hard cut.
- The green strip (over the About/Contact band) and the beige strip are separate layers that cross-fade at 0.35s, the same speed as the logo colour change.
- The logo switches colour at the middle of the band's painted brush edge, so it stays in sync both ways.
- Scrolling down hides the whole header, logo included. Scrolling up, hovering the top, or keyboard focus brings it back.
- `scroll-padding-top` (96px desktop, 80px phone) so nav links land below the header.

**Hero**
- Barsik's hover note is in **Fraunces italic** (the old "Shadows Into Light" handwriting font was dropped; the file `fonts/shadows-into-light.woff2` is unused now).
- The note sits **beside the painting** in the paper margin, with a curved arrow toward the keyboard.
  - A small script measures the free margin and adds `.tag-side` when the note fits.
  - Without room (phones) it shows as a paper label along the top of the painting.
- No space is reserved under the painting any more. The headline sits 26px below it, and "Open to work" clears the fold.
- Hero line now reads "I do **UI/UX** and interaction design." The homepage meta descriptions changed too. The degree name in About stays "UX/UI Design" (official title).

**Contact**
- Clicking "Open to work" or the header "Contact" immediately:
  - turns the email coral, and
  - switches Barsik's note to "Over here! Email her".
- Barsik hops when the section arrives. The state holds while Contact is on screen and resets once you scroll away.
- The contact note is also Fraunces italic.

**Other**
- Removed the MindScoop / CBS KPIX block from About. Its `.feature` CSS is still in the file, unused.
- The Reboot blurb no longer leaves "Reboot." alone on the last line, and project blurbs use `text-wrap: pretty`.

## Still to do

**From the portfolio review**, most impactful first:

1. **Docket:**
   - Say who the 6 testers were (e.g. "2 have hired, 4 have interviewed").
   - Test with real hiring managers or interviewers.
   - Add a timed "submit feedback" task.
   - Trim it from 28 sections to about 15 (collapse Personas, Task Flow, Sources).
2. **New featured project.** Either:
   - "Docket Assist": AI drafts interview feedback from rough notes, with sources shown and bias flags, tested against a blank form. Or:
   - A small real shipped project with one real metric.
3. **Quick win (cuts only):**
   - Move Reboot off the homepage list. It's unfinished: "Round 02: waiting for players".
   - Remove every "6 months later", "Thank you" and placeholder section across the case studies.
4. **Flosser:**
   - Run a 1-week diary study with new people.
   - Collapse the mascot/branding sections to about 3 screens.
   - Fix "23 people" vs "22 responses".
   - The 3 focus-group people are the same as Reboot's; disclose that or replace them.
5. **Nuance:**
   - Narrow it to shade matching.
   - Add a "How reviews stay honest" section and the business trade-off, or keep it demoted.
   - The homepage blurb ("Most beauty apps get shade matching wrong") contradicts the page's own competitor table.

**Open questions:**

- **Case study pages** (docket, flosser, nuance, reboot) still say "UX/UI" in about a dozen places. Switch them to "UI/UX" to match the homepage?
- **Unused leftovers:** delete `fonts/shadows-into-light.woff2` and the `.feature` CSS?
- **Phone layout:** not yet checked on a real phone, especially the hero note label and the nav.
