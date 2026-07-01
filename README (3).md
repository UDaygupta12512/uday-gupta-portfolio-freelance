# Uday Gupta — Developer Portfolio

> Full-Stack Developer & AI Builder · B.Tech CSE 2026 · MIET Meerut · AI Minor, IIT Ropar

[![Live Demo](https://img.shields.io/badge/Live-Portfolio-7b5cff?style=for-the-badge&logo=vercel)](https://uday-gupta-portfolio.vercel.app)
[![GitHub](https://img.shields.io/badge/GitHub-UDaygupta12512-181717?style=for-the-badge&logo=github)](https://github.com/UDaygupta12512)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Uday%20Gupta-0077B5?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/uday-gupta-7b0887295)

---

## What This Is

A single-file portfolio and freelance website — no framework, no bundler, no build step. Every feature runs in ~400KB of vanilla HTML/CSS/JS. The constraint is intentional: if you understand the stack deeply enough, you don't need a framework to build something polished.

**Try pressing `Ctrl+K` anywhere on the site.**

---

## Features

### Navigation & UX
- **Command Palette** (Ctrl/⌘+K) — 25+ actions across Navigate, Projects, Actions, Links
- **Context-aware cursor** — emoji changes per section (🔍 projects, ⚡ skills, ✉️ contact…)
- Mobile hamburger overlay with all nav links
- Dark / light theme with flash-of-wrong-theme prevention
- Keyboard accessibility — `:focus-visible` rings on all interactive elements
- Skip-to-content link for screen readers

### Projects
- 8 project cards with animated SVG previews
- 3 full case studies (Mindsphere AI, AI Podcast, Cook Assistant)
- All project buttons properly clickable (fixed overlay intercept bug)

### Skills
- Animated progress bars (IntersectionObserver, width-based, 3-layer fallback)
- Physics-based skill cloud (Matter.js — 30 badges with real gravity + mouse interaction)
- Falls back to static 54-badge grid if Matter.js CDN unavailable

### Freelance Features
- Hire form — Formspree → EmailJS → mailto 3-layer fallback chain
- Honeypot spam protection (`_gotcha` field, client + server double-check)
- Response pledge badge ("Replies within 4 hours")
- Sticky "Available for projects" bar (appears at 60% scroll or after 45s)
- **Industry pitch generator** — 10 industries, custom project ideas per sector
- Job fit analyzer for recruiters

### Live Data
- GitHub commit ticker above footer (lazy API fetch, hardcoded fallback)
- Live GitHub stats (lazy IntersectionObserver)
- `status.json` — manually updated "now" status card (what I'm building/learning)

### Easter Eggs
- `Ctrl+K` → "whoami" → terminal modal with fake `git log`
- `Ctrl+K` → "how this site was built" → architecture deep-dive modal
- `Ctrl+K` → "print" → clean print/PDF output via `@media print`

### Content
- 10 curated tech blog articles with full modal reader
- Public build log / changelog (8 entries, tagged SHIP/FEAT/LEARN/FIX)
- "What I'd Build For Your Industry" widget (10 sectors, 3 custom ideas each)

---

## Tech Stack

```
HTML / CSS / Vanilla JS      — no framework, no bundler
GSAP 3.12 + ScrollTrigger   — scroll animations
Matter.js 0.19.0             — physics skill cloud
EmailJS                      — email fallback for contact form
Formspree                    — primary contact form + lead dashboard
GitHub REST API              — live stats + commit ticker (lazy loaded)
```

---

## File Structure

```
portfolio/
├── index.html      — entire site (HTML + CSS + JS, ~400KB)
├── favicon.svg     — UG monogram in brand gradient
├── status.json     — live "now" status (edit this to update the site)
├── robots.txt      — search engine crawl rules
└── sitemap.xml     — sitemap for Google indexing
```

### Updating Your Status

Edit `status.json` and redeploy. No code changes needed:

```json
{
  "updated": "Jul 2026",
  "status": "open",
  "building": { "value": "Your current project" },
  "learning": { "value": "What you're studying" },
  "shipped":  { "value": "What you just launched" },
  "availability": "Open to full-time SDE roles + freelance projects"
}
```

---

## Deployment

Deployed on **Vercel** (free tier). No build step required — pure static site.

To deploy your own copy:
1. Fork this repo
2. Go to [vercel.com](https://vercel.com) → New Project → Import from GitHub
3. Select this repo, click Deploy
4. Done — live in ~30 seconds

---

## Architecture Notes

### Why a single file?
Keeping everything in `index.html` means zero dependency management, zero build failures, and instant local development (`open index.html` in any browser). The trade-off is file size (~400KB) — acceptable for a portfolio that's loaded once and cached.

### GSAP Safety Shim
If GSAP CDN fails to load (ad-blocker, CDN outage, network issues), a no-op shim absorbs all `gsap.from/to/set` calls silently. All elements have `opacity: 1 !important` CSS fallbacks, so the page remains fully usable without animations.

### Theme System
`[data-theme="light"]` attribute on `<html>`, set by a tiny inline `<head>` script before paint (prevents flash-of-wrong-theme). Every color is a CSS custom property redefined under that selector — no duplicate stylesheets.

### Form Fallback Chain
```
Formspree (lead dashboard) 
  → EmailJS (email backup)
    → mailto: (guaranteed last resort)
```
Honeypot field `name="_gotcha"` (Formspree's documented convention) gives double protection — client-side JS check + Formspree's own server-side filter.

---

## Contact

- **Email** — udayapril22@gmail.com
- **WhatsApp** — +91 7668161626
- **LinkedIn** — [uday-gupta-7b0887295](https://www.linkedin.com/in/uday-gupta-7b0887295)
- **GitHub** — [UDaygupta12512](https://github.com/UDaygupta12512)

---

*Built by Uday Gupta · Jun 2026 · Single file, zero frameworks, zero excuses.*
