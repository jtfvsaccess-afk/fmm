# Fort Myers Labor Only Movers — AI-Optimized Lead Gen Site

## Project Overview

**Business:** Labor-only moving lead generation for Fort Myers, FL
**Model:** $75/lead sold to FlexHelp, Inc. (Thumbtack Top Pro, 247+ reviews, 4.9★)
**Tech:** Static HTML/CSS/JS (no build system) — AI-crawler visible from day 1
**Deploy:** GitHub Pages (auto-deploys from `main`) · also works on Netlify
**GitHub:** `https://github.com/overnightmvp/FMM.git`
**Live site:** `https://fortmyerslaboronlymovers.com/`

---

## Recent Updates (Latest Commits)

| Commit | Description |
|--------|-------------|
| `1bdaadd` | **fix:** correct relative asset paths in all blog pages — fixed `/blog/` subdirectory CSS/JS references |
| `d2879ca` | **perf:** optimize analytics loading and fix font 404 errors — removed redundant GA4, added defer to GTM, updated font paths |
| `b9677a0` | **feat(analytics):** install GA4 and GTM tracking across all 20 HTML pages |
| `c836512` | **perf(pagespeed):** fix contrast, add main landmark, fix headings, defer JS — achieve 100 score |

---

## Current Project Status

### ✅ Completed

- **Font Loading Fixed** — Corrected all 5 font paths in `assets/fonts.css` (Inter-Regular, Inter-Medium, Inter-SemiBold, Inter-Bold, Inter-ExtraBold)
- **Blog Paths Fixed** — Corrected relative asset paths in all 9 blog pages (`/blog/` subdirectory)
- **Analytics Installed** — GA4 (Measurement ID: `G-9HT66TRLBB`) + GTM (Container: `GTM-NP2GZLLJ`) across all 20 HTML pages
- **Performance Optimized** — Removed redundant GA4 gtag.js (~150 KiB saved), added `defer` attribute to GTM script
- **Deployed to Netlify** — Live at https://deft-beignet-56707a.netlify.app/

### ⚠️ Pending (User Action Required)

1. **Add GA4 Configuration Tag in GTM UI** ← CRITICAL BLOCKER
   - Go to https://tagmanager.google.com/ → Select `GTM-NP2GZLLJ`
   - **Tags** → **New** → Select **Google Analytics: GA4 Configuration**
   - **Measurement ID:** `G-9HT66TRLBB`
   - **Trigger:** All Pages
   - **Save & Publish**

2. **Verify Performance Improvements**
   - Run PageSpeed Insights on https://deft-beignet-56707a.netlify.app/
   - Verify: Font 404s resolved, unused JS reduced, performance score improved
   - DevTools Network tab: All font files should return 200 status

3. **Verify Analytics Tracking**
   - GA4 Real-Time: Pageviews appearing after GTM publish
   - Form submission: `generate_lead` event fires with $75 value

### 📊 Expected Performance Gains

| Metric | Before | After | Status |
|--------|--------|-------|--------|
| Font 404 Errors | 4 | ✅ 0 | Fixed |
| Unused JavaScript | 225 KiB | ~75 KiB | Optimized |
| Render Blocking | GTM + GA4 | ✅ GTM deferred | Optimized |
| Analytics System | Redundant dual load | ✅ Unified (GTM only) | Optimized |

---

## Quick Start

```bash
# Preview locally (main landing page)
open index.html

# Preview other pages
open blog/index.html                        # Blog hub
open labor-only-moving-fort-myers.html     # Service pillar
open omvp-fmm-dashboard.html               # Project dashboard

# Push to GitHub (auto-deploys)
git add .
git commit -m "feat: description"
git push origin main
# GitHub Pages: https://overnightmvp.github.io/FMM/
# jtfvsaccess-afk: https://github.com/jtfvsaccess-afk/fmm

# Deploy to Netlify (drag & drop)
# → netlify.com/drop → drag fort-myers-movers/ folder
```

See `CLAUDE.md` for Claude Code session guidance.

---

## Before Going Live: Configuration Status

| Item | Status | Details |
|------|--------|---------|
| **Formspree Form ID** | ✅ Configured | `assets/movers.js` line 9 → See `systems/launch-checklist.md` |
| **Google Tag Manager** | ✅ Installed | Container ID: `GTM-NP2GZLLJ` (all 20 HTML files) |
| **GA4 Measurement ID** | ✅ Installed | ID: `G-9HT66TRLBB` (assets/movers.js line 12) |
| **GA4 GTM Configuration** | ⚠️ PENDING | **User must add GA4 Configuration tag in GTM UI** (see above) |
| **Phone Number** | ✅ Configured | Fort Myers area code (239) in assets/movers.js line 10 |

**Live Deployment Checklist:**
- ✅ All assets linked correctly (fonts, CSS, JS)
- ✅ All 20 HTML pages have GA4 + GTM installed
- ✅ Blog relative paths fixed
- ⚠️ Awaiting GA4 Configuration tag in GTM (required for tracking)
- ⚠️ Run PageSpeed Insights to verify performance improvements

See `systems/launch-checklist.md` for full pre-launch verification.

---

## File Structure

```
fort-myers-movers/
├── 📄 ROOT LANDING PAGES (8 files)
│   ├── index.html                         ← Main landing page (9 sections, quote form)
│   ├── labor-only-moving-fort-myers.html  ← Primary service pillar
│   ├── cape-coral-movers.html
│   ├── bonita-springs-movers.html
│   ├── naples-moving-help.html
│   ├── loading-unloading-help.html
│   ├── packing-unpacking-fort-myers.html
│   ├── privacy-policy.html
│   └── omvp-fmm-dashboard.html            ← Project management dashboard
│
├── 🎨 ASSETS (Design System)
│   ├── assets/fonts.css                   ← Self-hosted Inter fonts (FIXED ✅)
│   ├── assets/movers.css                  ← Full design system (6-variable theming)
│   ├── assets/movers.js                   ← Quote calculator + form logic + GA4 tracking
│   ├── assets/movers.min.css              ← Minified CSS
│   └── assets/movers.min.js               ← Minified JS
│
├── 🔤 FONTS
│   ├── fonts/inter.css                    ← Font loader
│   └── fonts/Inter-*.woff2                ← 5 self-hosted font files (Regular, Medium, SemiBold, Bold, ExtraBold)
│
├── 📝 BLOG (9 articles + index)
│   ├── blog/index.html
│   ├── blog/average-cost-labor-only-moving-florida.html
│   ├── blog/best-time-to-move-fort-myers.html
│   ├── blog/how-to-hire-moving-labor-fort-myers.html
│   ├── blog/labor-only-vs-full-service-movers.html
│   ├── blog/moving-cape-coral-fl.html
│   ├── blog/moving-checklist-fort-myers.html
│   ├── blog/pod-container-loading-service.html
│   ├── blog/tips-loading-moving-truck.html
│   └── blog/*.md                          ← Source markdown versions
│
├── 📚 DOCUMENTATION
│   ├── docs/design-system.md              ← CSS token reference — all variables + components
│   ├── docs/brand-system.html             ← Visual brand guide — open in browser
│   ├── docs/AI-VISIBILITY-STRATEGY.md     ← AI crawler optimization (llm.txt, robots.txt, Schema.org)
│   ├── docs/SEO-CONTENT-STRATEGY.md       ← Keyword targets + content calendar
│   ├── docs/market-intel.md               ← Competitor analysis + market data
│   ├── docs/FMM-90-minute-execution.md    ← Quick start guide
│   ├── docs/BOILERPLATE-NEW-CITY-ONBOARDING.md
│   ├── docs/email-templates.md
│   ├── docs/contractor-research.md
│   └── docs/next-steps-roadmap.md         ← Week 1 → Month 3 action plan
│
├── 🔧 SYSTEMS & OPERATIONS
│   ├── systems/lead-routing-setup.md      ← Formspree → Zapier → Sheets → Contractor
│   ├── systems/launch-checklist.md        ← Pre-launch verification steps
│   ├── systems/pricing-guide.md           ← Rate card + contractor pricing
│   └── systems/success-metrics.md         ← KPIs and analytics tracking
│
├── 📋 PROJECT FILES
│   ├── README.md                          ← This file
│   ├── CLAUDE.md                          ← Project guidance for Claude Code
│   ├── PERFORMANCE.md                     ← Performance optimization metrics
│   └── .planning/                         ← GSD workflow files
│       ├── STATE.md                       ← Project state tracking
│       ├── phases/                        ← Phase plans (01, 02, 03)
│       └── todos/                         ← Task tracking (pending/ and done/)
│
└── 📁 OTHER
    ├── ads/                               ← (future: facebook-strategy.md, google-ads-strategy.md)
    └── .git/                              ← Git repository (GitHub sync)
```

---

## Project Statistics

| Category | Count | Status |
|----------|-------|--------|
| **HTML Pages** | 20 | ✅ GA4 + GTM installed |
| **Blog Articles** | 9 | ✅ Paths fixed |
| **Service Pages** | 6 | ✅ All optimized |
| **Font Files** | 5 | ✅ Self-hosted (fixed paths) |
| **CSS Files** | 2 | ✅ Main + minified |
| **JS Files** | 2 | ✅ Main + minified |
| **Documentation Files** | 10+ | ✅ Current |
| **System Guides** | 4 | ✅ Complete |

---

## AI Visibility Layer (Competitive Moat)

The current live site (React/Hostinger) is invisible to GPTBot, ClaudeBot, and PerplexityBot. Our static HTML rebuild wins on day 1.

| Asset | Purpose | Status |
|---|---|---|
| `llm.txt` | First-party brand facts for LLMs | ✅ Done |
| `robots.txt` | Explicit AI crawler Allow directives | ✅ Done |
| Schema.org MovingCompany | Rich results + AI citations | ✅ Done |
| Schema.org FAQPage | FAQ rich results | ✅ Done |
| Static HTML | Full content in initial response | ✅ Done |

---

## Theming for New Markets

To replicate for a new city, update 6 CSS variables in `assets/movers.css` + find/replace city names:

```css
/* assets/movers.css — change these 6 lines to rebrand for new city */
--color-primary:      #1e3a8a;   /* Main brand color (navy) */
--color-primary-dark: #1a3070;   /* Hover state */
--color-accent:       #f97316;   /* CTA button color (orange) */
--color-accent-hover: #ea6c0a;   /* Button hover */
--color-trust:        #16a34a;   /* Trust bar background (green) */
--font-family: 'Inter', sans-serif;
```

**Replication Checklist:**
1. Update 6 CSS variables in `assets/movers.css`
2. Find/replace: `Fort Myers` → `[New City]`
3. Find/replace: `(239) phone number` → `[New Area Code]`
4. Update Schema.org `areaServed` arrays in all HTML files
5. Create new Formspree form ID (assets/movers.js line 9)
6. Create new GTM container (if needed) or reuse existing
7. Update `docs/` files with new market data
8. Push to new GitHub repo/subdirectory

**Estimated effort:** 2–3 hours per new city (template-driven deployment)

---

## Revenue Model

- **Lead price:** $75/qualified lead (exclusive)
- **Target volume:** 300+ leads/month by Month 3
- **Contractor payment:** Net 15 via Wave invoice
- **Month 3 target:** $22,500+ revenue

See `docs/market-intel.md` for full financial projections.
