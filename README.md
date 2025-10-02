# Traze US Session Newsletter

Professional daily market analysis newsletter for traders using the Traze platform.

**Live Archive:** [https://noodlespoodles.github.io/zfx-newsletter/](https://noodlespoodles.github.io/zfx-newsletter/)

---

## Quick Links

- **Documentation:** See `_docs/` folder for complete guidance
- **Production Process:** `_docs/DAILY_NEWSLETTER_PROCESS.md`
- **Content Template:** `_docs/NEWSLETTER_TEMPLATE.md`
- **Claude Code Guide:** `_docs/CLAUDE.md`

---

## Project Overview

This repository contains the complete production system for the Traze daily market snapshot newsletter, featuring:

- **HTML Newsletter Template** (Traze-branded, email-safe, responsive)
- **Daily Production Workflow** (Claude Code powered, ~30 minutes/day)
- **GitHub Pages Deployment** (automated archive hosting)
- **Brand Assets** (Traze logos, colors, styling)

---

## Folder Structure

```
├── _archive/            # Published newsletters (GitHub Pages)
│   ├── YYYY-MM-DD/      # Each day's newsletter
│   └── index.html       # Archive navigation
│
├── _working/            # Daily production workspace
│   └── YYYY-MM-DD/      # Today's working folder
│       ├── sources/     # Input PDFs
│       ├── charts/      # Screenshots + commentary
│       ├── newsletter-draft.md
│       └── newsletter-final.html
│
├── _templates/          # Newsletter templates
│   ├── newsletter-template-traze.html  # CURRENT
│   └── legacy/          # Old templates
│
├── _assets/             # Traze branding
│   └── traze/           # Logos, favicon
│
├── _reference/          # Reference materials
│   ├── design-examples/ # Inspiration
│   └── sample-inputs/   # Example sources
│
└── _docs/               # Documentation
    ├── CLAUDE.md
    ├── README.md
    ├── DAILY_NEWSLETTER_PROCESS.md
    └── NEWSLETTER_TEMPLATE.md
```

---

## Daily Workflow (30 minutes)

### 1. Collect Inputs (10 min)
Create folder: `_working/YYYY-MM-DD/`
- Download Bloomberg, SpotGamma, TipRanks PDFs → `sources/`
- Screenshot charts → `charts/`
- Write chart commentary → `charts/chart-comments.txt`

### 2. Generate Draft (7 min)
```
Claude Code: "Start newsletter process for YYYY-MM-DD"
Claude Code: "Create newsletter draft from inputs"
```

### 3. Review & Edit (10 min)
- Open `newsletter-draft.md`
- Verify no fabricated data
- Add personal insights
- Save

### 4. Generate HTML (2 min)
```
Claude Code: "Generate HTML from approved draft"
```

### 5. Publish (5 min)
- Copy to `_archive/YYYY-MM-DD/`
- Git commit and push
- Live at: `https://noodlespoodles.github.io/zfx-newsletter/YYYY-MM-DD/`

**See `_docs/DAILY_NEWSLETTER_PROCESS.md` for detailed checklist**

---

## Newsletter Content

### Sections
1. **Header** - Traze branding, date, session
2. **At a glance** - Market dashboard (S&P, VIX, DXY)
3. **Market overview** - Daily narrative and drivers
4. **The big money** - S&P futures technical analysis
5. **Instruments to watch** - EUR/USD, Gold, Oil, DXY, VIX (with charts)
6. **Today's calendar** - Economic events (ET timezone)
7. **Trader tip** - Daily educational content
8. **Session outlook** - What to watch, risk factors
9. **CTA & Footer** - Traze link, risk warning

### Data Sources
- **Bloomberg** - Market wrap, prices
- **SpotGamma** - Technical levels, options positioning
- **TipRanks** - Market summaries
- **SqueezeMetrics** - Options flow (optional)
- **Benzinga** - Futures data (optional)

---

## Key Features

### Traze Branding
- Dark gradient header (#090A1D → #5B61E3)
- Light body for email compatibility
- Pill-shaped buttons (border-radius: 9999px)
- Gradient section dividers (cyan-purple)

### Data Integrity
- **No fabricated FX levels** - Only from sources
- **Verbatim chart commentary** - Exact text from chart-comments.txt
- **Technical levels as zones** - No exact proprietary strikes
- **UK English spelling** - Throughout

### Responsive Design
- Desktop: Two-column layouts
- Mobile: Single-column stack
- Breakpoint: 600px
- Email-safe: XHTML 1.0 Transitional, inline CSS

---

## GitHub Pages Deployment

### Setup (One-Time)
1. Repository settings → Pages
2. Source: Deploy from branch `main` / (root)
3. Wait 2-3 minutes for deployment

### Daily Publishing
```bash
# Copy newsletter to archive
cp _working/YYYY-MM-DD/newsletter-final.html _archive/YYYY-MM-DD/index.html
cp -r _working/YYYY-MM-DD/charts/* _archive/YYYY-MM-DD/charts/

# Update archive index
# Edit _archive/index.html to add new entry

# Commit and push
git add _archive/
git commit -m "Add YYYY-MM-DD newsletter"
git push origin main
```

Newsletter available at:
```
https://noodlespoodles.github.io/zfx-newsletter/YYYY-MM-DD/
```

---

## Production Standards

### Absolute Rules (NEVER Violate)

1. **Only use data from sources** - No fabrication, no estimation
2. **Chart commentary verbatim** - Exact text from chart-comments.txt
3. **Technical levels as zones** - "6,640-6,700" not "6,675"
4. **No FX levels unless from sources** - Don't invent support/resistance
5. **No emojis** - Anywhere in content
6. **Sentence case** - "Market overview" not "Market Overview"
7. **UK English** - realised, whilst, colour, behaviour

### Common Mistakes to Avoid
❌ "EUR/USD support at 1.1700" (if not in Bloomberg)
❌ "Gold holding well despite DXY surge" (if not in chart-comments.txt)
❌ "Markets are BULLISH" (all caps)
❌ "📊 Market Overview" (emoji)

✅ Only include FX levels from sources
✅ Use exact chart commentary
✅ "Markets are bullish" (sentence case)
✅ "Market overview" (no emoji)

---

## Development

### Current Template
**File:** `_templates/newsletter-template-traze.html`

**Status:** Active (October 2025)

**Tech Stack:**
- XHTML 1.0 Transitional
- Inline CSS (email compatibility)
- Microsoft Office conditional comments (Outlook)
- Responsive media queries (@600px)

### Brand Colors (Traze)
```css
--traze-dark: #090A1D
--traze-dark-secondary: #000B20
--traze-purple: #5B61E3
--traze-cyan: #06B6D4
--success: #10B981
--danger: #EF4444
```

---

## Support

### Documentation
- **Daily Process:** `_docs/DAILY_NEWSLETTER_PROCESS.md` (step-by-step checklist)
- **Content Template:** `_docs/NEWSLETTER_TEMPLATE.md` (markdown structure)
- **Claude Code Guide:** `_docs/CLAUDE.md` (complete reference)

### Troubleshooting
- **Fabricated data detected:** See `_docs/CLAUDE.md` → "Common Issues"
- **HTML generation failed:** Check template path, verify chart files exist
- **Charts not displaying:** Verify relative paths, check file copy to archive

### Questions?
See `_docs/CLAUDE.md` for comprehensive guidance including:
- Complete workflow explanation
- Data extraction rules
- Quality checklists
- Emergency procedures
- Common issues and solutions

---

## License

Proprietary - Traze internal use only

---

**Last Updated:** October 2025
**Current Version:** Traze branding (light body, dark header/footer)
**Production Template:** `newsletter-template-traze.html`
