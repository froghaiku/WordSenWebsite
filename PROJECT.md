# WordSen Website — Project Status

**Living Document** — Updated via `/end` after website work sessions.
**Last Updated:** May 9, 2026

---

## Tech Stack

- **Framework:** Jekyll (~4.4) static site generator
- **Hosting:** **Vercel** (auto-deploys from `main` on push). Repo is `froghaiku/WordSenWebsite`. Local preview via `bundle exec jekyll serve`. (Site was migrated off GitHub Pages in April 2026 — see commit `ace56a6`.)
- **CSS:** Single stylesheet (`assets/css/main.css`) with CSS custom properties
- **Fonts:** Inter (body), Great Vibes/Zapfino (brand)
- **JavaScript:** Vanilla JS — mobile nav toggle, smooth scrolling
- **No build step** beyond Jekyll
- **Permalink convention:** every subpage's frontmatter must declare `permalink: /pagename/` so Jekyll outputs `_site/pagename/index.html`. Without it, Vercel returns 404 on the clean URL. Caught the hard way on the May 9 beta-page rewrite.

## Color Palette

```
--bg: #FFF5F0          warm peach background
--accent: #dd6245      coral/terracotta (primary)
--accent-hover: #c54d30
--text: #2d3748        dark gray
--text-secondary: #4a5568
--highlight: #10b981   emerald — used to highlight key phrases in body copy
--border: #f0e8e4      light beige
--radius: 12px
```

## Text Highlight Pattern

Ben uses emerald-green highlights (`--highlight: #10b981`) to emphasize the **core phrase or sentence** in a paragraph. This is part of his writing style across the site — every meaningful paragraph should have one highlighted phrase that captures the central idea.

**How to apply:**
- Wrap the phrase in `<span class="highlight">...</span>`
- The CSS class lives in `assets/css/main.css` (sets color + font-weight 500)
- Pick the ONE phrase per paragraph that someone could read on its own and still get the point. Not the whole thing — just the load-bearing phrase
- One highlight per paragraph is the rule. Multiple highlights in a single paragraph dilute the technique
- Examples in the wild: homepage feature cards (the three "How WordSen is different" boxes), the roadmap "feature - benefit" tagline (uses the same green via `.entry-benefit`)

When writing new content for the site, ask: "If a reader scans this page in 3 seconds, what one phrase per paragraph do I want their eye to catch?" That's the highlight.

## Current Pages

| Page | File | Status |
|------|------|--------|
| Homepage | `_layouts/home.html` | Live — phone frame placeholders need GIF recordings |
| Beta signup | `beta.html` | Live |
| Contact | `contact.html` | Live |
| Roadmap | `roadmap.html` | Live |
| Privacy | `privacy.html` | Live |
| Blog | `_posts/` | Live — needs more content |
| Dev Blog listing | `blog/` | Live |
| Feature pages | `features/` | De-linked from nav, may remove |

## Phone Frame Component (April 7, 2026)

CSS phone frame mockup in `assets/css/main.css` (search "PHONE FRAME COMPONENT").

**5 placeholder spots on homepage:**

| Spot | Expected file | What to record |
|------|--------------|----------------|
| Hero left phone | `screenshots/hero-study.gif` | Flipping through flashcards |
| Hero right phone | `screenshots/hero-wordlist.gif` | Scrolling word list |
| Flashcard spotlight | `screenshots/flashcard.gif` | Single card in detail |
| Kitsune spotlight | `screenshots/kitsune.gif` | Fox in its room |
| Card creation spotlight | `screenshots/card-creation.gif` | Voice recording to card flow |

All paths relative to `assets/images/`. To activate: delete `<div class="phone-screen-placeholder">` and uncomment the `<img>` tag above it in `_layouts/home.html`.

**Recording workflow:** QuickTime Player via USB cable from real iPhone (app has Unity, so Simulator won't work) → convert with `ffmpeg -i recording.mov -vf "fps=15,scale=375:-1:flags=lanczos" -loop 0 output.gif`

## Design Decisions (March 25, 2026)

- Positioning: "Learn 1,000 Japanese words without losing motivation"
- Hormozi/Dunford frameworks applied
- Warm, cozy aesthetic matching the app's personality
- First-person voice ("I built this because...") — see `Docs/WRITING_STYLE.md`

## Known Issues / TODO

- [ ] Record GIFs from real iPhone and drop into phone frames (5 placeholder spots still empty)
- [ ] Old feature pages in `features/` — de-linked but still exist, decide whether to remove
- [ ] Blog needs more content
- [ ] `WRITING_STYLE copy.md` in Docs/ — stale copy, should delete
- [ ] Blog post `_posts/2025-08-29-why-I-am-building-wordsen.markdown` references the removed stone-fox feature on lines 134 and 142 — Ben to decide whether to update or leave as historical
- [ ] Lots of new uncommitted assets sitting in `assets/images/` (mockup PNGs, kiki.gif, torii images, kit logos) and two unpublished draft posts in `_posts/` — Ben to triage and commit selectively

---

## Recent Work

### May 9, 2026 — Pre-Beta Marketing Push
- **Beta page** (`/beta/`): full rewrite in Ben's voice. Three cards above the signup ("Who you are" / "What I need from you" / "What you get"), tight perk line under the form ("First 100 signups get 1,000 koins on launch day"). Removed AI-tell intro box and fabricated daily-usage claim that snuck through. Added missing `permalink: /beta/` frontmatter to fix initial 404.
- **Homepage** (`_layouts/home.html`): added three feature-card illustrations (`stairs.png`, `fox.png`, `combine.png`) all locked to 200px height for cross-card alignment. Added `cycle.png` inside the "You know this cycle" white card. Bumped `.section-title` to 3rem (after iterating from 2rem → 4rem → 3rem) and `.spotlight-text h3` to 2.25rem. Rewrote Kitsune spotlight to drop the removed stone-fox punishment line and lean into "feels good to take care of your fox." Reframed Hub card around multi-app SRS fragmentation with "Nothing is in sync" as the punch.
- **Roadmap** (`/roadmap/`): every shipped-feature entry trimmed to a single sentence; added a `Feature - Benefit` green-highlighted tagline to each H3; restyled so each MONTH is one centered 800px white card containing its entries (was per-entry cards); added 6 emojis spread across months. Coming-next timeline updated to "late May 2026" honest-slip framing.
- **Highlight pattern documented** in this PROJECT.md: emerald `--highlight: #10b981` CSS variable + `.highlight` utility class for emphasizing the load-bearing phrase in any paragraph. One per paragraph, never multiple.
- **WRITING_STYLE.md broadened**: the "not just X, it's Y" rule expanded to forbid ALL "not X, it's Y" reframes regardless of the word "just." Caught after I shipped "This isn't a polished launch. It's me handing you..." in the first beta-page draft.

### April 7, 2026 — Phone Frame Component
- Built CSS phone frame component (iPhone mockup with Dynamic Island)
- Replaced all 4 homepage placeholder divs with phone frames
- Created `assets/images/screenshots/` directory for GIF assets
