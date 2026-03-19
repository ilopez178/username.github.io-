# CLAUDE.md — irvinglopez.com

This file is the source of truth for any Claude agent or contributor working on this site. **Read it before making any changes. Update it when your changes affect anything documented here.**

---

## Project Overview

Personal portfolio and consulting site for **Irving Lopez** — Product Manager at Ramsey Solutions and monday.com consultant.

- **Live site:** [irvinglopez.com](https://irvinglopez.com)
- **Repo:** GitHub Pages, auto-deployed via GitHub Actions on push to `main`
- **Architecture:** Single-file static site — all HTML, CSS, and JS live in `index.html`
- **No build step.** No frameworks. No package manager.

---

## Tech Stack

| Layer | Choice |
|---|---|
| Markup | Vanilla HTML5 |
| Styling | Vanilla CSS3 (embedded in `index.html`) |
| Scripting | Vanilla JavaScript (embedded in `index.html`) |
| Fonts | Google Fonts — Inter only |
| Hosting | GitHub Pages |
| CI/CD | GitHub Actions (`.github/workflows/static.yml`) |
| Domain | `irvinglopez.com` via `CNAME` file |

---

## File Structure

```
/
├── index.html                    # The entire site (HTML + CSS + JS)
├── CLAUDE.md                     # This file
├── CNAME                         # Custom domain — do not delete
├── robots.txt                    # SEO crawler permissions
├── sitemap.xml                   # SEO sitemap
├── irving.jpg                    # Profile photo (used in hero)
├── Irving Lopez 2000x2000.jpg   # Full-res backup (not used in site)
├── images/                       # Empty — safe to use for future assets
├── README.md                     # Brief public description
└── .github/workflows/static.yml # GitHub Pages deployment
```

---

## Design System

### Colors (CSS Custom Properties)

Always use these variables — never hardcode hex values.

```css
--bg:       #080808   /* Page background */
--surface:  #0f0f0f   /* Slightly lighter background */
--card:     #141414   /* Card backgrounds */
--border:   #1c1c1c   /* Borders */
--text:     #c8c8c8   /* Body text */
--muted:    #5a5a5a   /* Secondary / label text */
--white:    #f2f2f2   /* Headings / high-contrast text */
--accent:   #0ea5e9   /* Primary cyan/sky blue */
--accent2:  #38bdf8   /* Lighter cyan — hover states, highlights */
```

Do not change the color palette without Irving's explicit approval.

### Typography

- **Font:** Inter (loaded from Google Fonts)
- **Headings:** `color: var(--white)`
- **Body copy:** `color: var(--text)`
- **Labels / secondary:** `color: var(--muted)`
- Type hierarchy: section title → card title → body copy → label

### Spacing

All spacing uses multiples of 8px: `8, 16, 24, 32, 48, 64, 96`.

### Cards

```css
background: var(--card);
border: 1px solid var(--border);
border-radius: 12px;
```

Hover state: `border-color: var(--accent)` + `glowPulse` animation.

### Buttons / CTAs

Primary: `background: var(--accent)`, dark text.
Ghost: transparent with `border: 1px solid var(--border)`.

### Animations

Keep these existing animations — do not remove or rename them:

| Name | Purpose |
|---|---|
| `pulse` | Pulsing status dot |
| `blink` | Typing cursor |
| `spinOnce` | Profile photo ring (fires once on load) |
| `ticker` | Horizontal tools scroll |
| `glowPulse` | Card hover glow |
| `shimmer` | Skeleton loading |

---

## Page Sections

In order, top to bottom:

1. **Nav** — sticky header, underline hover, hamburger on mobile
2. **Hero** — typing animation cycling through 6 phrases, profile photo, two CTA buttons
3. **Stats bar** — animated counters (years, revenue, features shipped, users served)
4. **About** — bio, 6 highlight cards, animated tools ticker
5. **Testimonials** — 3 cards from Ramsey Solutions leaders
6. **Services** — 6 service cards + 3 Upwork client reviews (all 5-star)
7. **Experience** — certifications, education, languages
8. **Contact** — email, phone, social links (LinkedIn, Upwork, FastExpert, Instagram, Facebook)
9. **Footer** — copyright line

---

## Coding Conventions

### General
- **All code stays in `index.html`.** Do not split into separate `.css` or `.js` files.
- Use CSS variables for all colors — never hardcode hex.
- Responsive breakpoints: `1024px`, `900px`, `768px`.
- Prefer CSS animations over JS animations.

### CSS
- Embedded in a single `<style>` block in `<head>`.
- Follow existing naming conventions (BEM-ish, descriptive class names).

### JavaScript
- Lives in a single `<script>` block at the bottom of `<body>`.
- Use `const` and `let` — never `var`.
- Separate logical sections with `// --- Section Name ---` comments.

---

## Copy & Tone Guidelines

- **Voice:** Professional but approachable — not corporate, not casual.
- **Person:** First-person ("I help teams…", "I've shipped…").
- **Quantify results** whenever possible: `$8M+`, `120k+ users`, `100+ features`.
- **Keep copy tight** — no filler words, no buzzword overload.
- **Language:** English only, unless Irving explicitly asks for Spanish content.
- **Do not alter testimonials** without Irving's approval — they are real quotes from named individuals.

---

## Personal Details (Do Not Change Without Confirmation)

| Field | Value |
|---|---|
| Name | Irving Lopez |
| Title | Product Manager |
| Employer | Ramsey Solutions |
| Location | Tennessee |
| Email | contact@irvinglopez.com |
| Phone | (505) 360-9429 |
| Stats | 5+ years, $8M+ revenue, 100+ features, 120k+ users |
| Upwork | Top Rated |

---

## SEO Files

| File | Purpose |
|---|---|
| `robots.txt` | Tells crawlers they can index everything; points to sitemap |
| `sitemap.xml` | Tells Google/Bing the canonical URL and update frequency |
| JSON-LD in `<head>` | Structured data (Schema.org `@graph`) for rich search results |

### JSON-LD Schema Summary

The structured data uses `@graph` with a `Person` node targeting two audiences:

1. **As a Product Manager** — job title, employer (Ramsey Solutions), PM experience
2. **As a monday.com Consultant** — this is the primary SEO target for consulting leads

Key fields used to signal monday.com expertise to Google:

| Field | Purpose |
|---|---|
| `jobTitle` | Array: "Product Manager", "monday.com Consultant", "monday.com Implementation Specialist" |
| `knowsAbout` | 20+ specific monday.com and automation topics Google can index |
| `hasCredential` | Both Partner Verified monday.com certifications |
| `hasOccupation` | `Occupation` type with skills targeting monday.com consulting searches |
| `makesOffer` | All 6 services listed as `Service` objects with names and descriptions |

**When to update the JSON-LD:**
- Add a new service → add an entry to `makesOffer`
- Earn a new certification → add an entry to `hasCredential`
- Expand into a new tool/area → add it to `knowsAbout`

Update `sitemap.xml`'s `<lastmod>` date whenever significant content changes are made.

---

## Images

- `irving.jpg` — profile photo displayed in the hero section
- `Irving Lopez 2000x2000.jpg` — full-resolution backup, not referenced in the site
- `images/` — empty directory, safe to use for future assets
- **Optimize before adding:** target under 500KB for web images

---

## Deployment

1. Push to `main`
2. GitHub Actions runs `.github/workflows/static.yml` automatically
3. Site deploys to GitHub Pages (~1 minute)
4. Verify at [irvinglopez.com](https://irvinglopez.com)

**Never delete `CNAME`** — it maps `irvinglopez.com` to GitHub Pages. Deleting it breaks the custom domain.

### Git Workflow

```bash
git pull origin main --rebase   # sync before making changes
# edit index.html (and update CLAUDE.md if needed)
git add index.html CLAUDE.md    # stage relevant files
git commit -m "Short description of change"
git push origin main
```

---

## What NOT to Do

- Do not add external JS libraries (jQuery, React, Vue, etc.)
- Do not split `index.html` into separate CSS/JS files
- Do not hardcode colors — always use CSS variables
- Do not add new fonts — Inter only
- Do not change the color palette without explicit approval
- Do not edit testimonials or personal details without confirmation
- Do not delete `CNAME`, `robots.txt`, or `sitemap.xml`
- Do not push to a branch other than `main` for production deploys

---

## Keeping This File Updated

**Update `CLAUDE.md` when you:**
- Add or remove a page section
- Change the design system (colors, fonts, spacing, animations)
- Add new JS behavior
- Update personal details, stats, certifications, or contact info
- Add new images or assets
- Change the deployment workflow or add new config files

**You do not need to update it for:**
- Minor copy tweaks (fixing a typo, rewording a sentence)
- Small style adjustments that don't change the design system

When in doubt, update the file.
