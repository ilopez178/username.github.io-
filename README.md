# Irving Lopez — Personal Website

Personal portfolio and consulting site for **Irving Lopez** — Product Manager at Ramsey Solutions and certified monday.com consultant.

**Live site:** [irvinglopez.com](https://irvinglopez.com)

---

## About

Irving is a product manager based in Tennessee with 5+ years shipping real estate tech at Ramsey Solutions — 100+ features, $8M+ in attributed revenue, 120k+ users served yearly. He also helps small businesses build custom workflows, automations, and integrations on monday.com.

---

## Tech Stack

- **Markup / Styling / Scripting:** Vanilla HTML5, CSS3, JavaScript — no libraries, no frameworks
- **Fonts:** Google Fonts (Inter)
- **Hosting:** GitHub Pages
- **CI/CD:** GitHub Actions — auto-deploys on push to `main`
- **Domain:** `irvinglopez.com` via `CNAME`

The entire site lives in a single `index.html` file. There is no build step.

---

## Key Files

| File | Purpose |
|---|---|
| `index.html` | The entire site — HTML, CSS, and JS |
| `CNAME` | Custom domain mapping — do not delete |
| `robots.txt` | Crawler permissions |
| `sitemap.xml` | SEO sitemap |
| `irving.jpg` | Profile photo used in the hero section |
| `CLAUDE.md` | Full project documentation for contributors and AI agents |

---

## Git Workflow

### Pull latest version (do this first before editing)

**Terminal** (open with `` Ctrl+` `` / `` Cmd+` `` in VS Code):

```bash
git pull origin main --rebase
```

---

### Push to production (publishes to irvinglopez.com)

**Option A — Ask Claude Code (easiest)**

Make your edits, then just say: *"Commit and push my changes"*
Claude will stage the files, write the commit message, and push — no terminal needed.

**Option B — Source Control panel (GUI)**

1. Make your edits to `index.html`
2. Open **Source Control** (`Ctrl+Shift+G` / `Cmd+Shift+G`)
3. Hover over **Changes** → click **+** to stage files
4. Type a commit message in the box at the top
5. Click **✓ Commit**
6. Click **Sync Changes** (or the **↑ Push** button)

**Option C — Terminal**

```bash
git add index.html
git commit -m "Updated Personal Website"
git push origin main
```

GitHub Actions deploys automatically after push — live in ~1 minute.

---

## Contributing

See [`CLAUDE.md`](CLAUDE.md) for the full design system, coding conventions, copy guidelines, and everything else you need before making changes.
