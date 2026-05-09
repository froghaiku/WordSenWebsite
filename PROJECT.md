# WordSen Website — Project Status

**Living Document** — Updated via `/end` after website work sessions.
**Last Updated:** April 7, 2026

---

## Tech Stack

- **Framework:** Jekyll (~4.4) static site generator
- **Hosting:** GitHub Pages (or local `bundle exec jekyll serve`)
- **CSS:** Single stylesheet (`assets/css/main.css`) with CSS custom properties
- **Fonts:** Inter (body), Great Vibes/Zapfino (brand)
- **JavaScript:** Vanilla JS — mobile nav toggle, smooth scrolling
- **No build step** beyond Jekyll

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

- [ ] Record GIFs from real iPhone and drop into phone frames
- [ ] Old feature pages in `features/` — de-linked but still exist, decide whether to remove
- [ ] Blog needs more content
- [ ] `WRITING_STYLE copy.md` in Docs/ — stale copy, should delete

---

## Recent Work

### April 7, 2026 — Phone Frame Component
- Built CSS phone frame component (iPhone mockup with Dynamic Island)
- Replaced all 4 homepage placeholder divs with phone frames
- Created `assets/images/screenshots/` directory for GIF assets
