# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **Traze US Session Newsletter** project - a professional HTML email newsletter template and deployment system for Traze's daily market snapshots. The project contains HTML templates, market charts, branding assets, and deployment configurations for GitHub Pages.

## Project Structure

```
US Session Newsletter/
├── _archive/                      # Published newsletters (GitHub Pages)
│   ├── YYYY-MM-DD/               # Each day's published newsletter
│   │   ├── index.html
│   │   └── charts/
│   └── index.html                # Archive navigation
│
├── _working/                      # Daily production workspace
│   └── YYYY-MM-DD/               # Today's working folder
│       ├── sources/              # Input PDFs and text files
│       ├── charts/               # Chart screenshots + commentary
│       ├── newsletter-draft.md   # Generated draft
│       └── newsletter-final.html # Final HTML output
│
├── _templates/                    # Template files
│   ├── newsletter-template-traze.html  # CURRENT PRODUCTION TEMPLATE
│   └── legacy/                   # Old templates (reference only)
│
├── _assets/                       # Brand assets
│   └── traze/                    # Traze logos and branding
│
├── _reference/                    # Reference materials
│   ├── design-examples/          # Newsletter design inspiration
│   └── sample-inputs/            # Example source files
│
└── _docs/                         # Documentation
    ├── CLAUDE.md                 # This file
    ├── README.md                 # Project overview
    ├── DAILY_NEWSLETTER_PROCESS.md  # Daily workflow
    └── NEWSLETTER_TEMPLATE.md    # Content template
```

## Key Information

### Newsletter Purpose
The newsletter provides daily market analysis for traders using the **Traze platform**, including:
- S&P 500 futures analysis
- Forex pairs (EUR/USD, GBP/USD, USD/JPY)
- Commodities (Gold, Oil)
- Market indices
- Key support/resistance levels (expressed as zones/ranges)
- Options expiry alerts

### HTML Structure
- Uses XHTML 1.0 Transitional for email compatibility
- Microsoft Office conditional comments for Outlook support
- Inline CSS for email client compatibility
- Responsive design with mobile breakpoints at 600px
- Traze brand colors defined as CSS variables

### Brand Colors (Traze)
```css
--traze-dark: #090A1D
--traze-dark-secondary: #000B20
--traze-purple: #5B61E3
--traze-cyan: #06B6D4
--success: #10B981
--danger: #EF4444
--warning: #F59E0B
```

## Current Production Template

**File:** `_templates/newsletter-template-traze.html`

**Status:** Active as of October 2025

**Design:** Light body with dark Traze gradient header/footer, email-safe

**Legacy templates** (reference only):
- `_templates/legacy/sample.html` - Original concept
- `_templates/legacy/sample-refined.html` - Iteration

## Newsletter Content Framework

### Content Structure

The newsletter follows a structured format optimized for traders using the Traze platform (indices, forex, commodities, crypto - **no individual stock trading**).

#### 1. Header & Branding
- Traze logo and tagline
- Date/Time with session identifier (e.g., "US session · Wednesday, September 25, 2025")
- Brief market sentiment indicator (Risk On/Risk Off/Neutral)

#### 2. Market Snapshot Dashboard ("At a glance")
**Key Indices** (relevant to Traze platform)
- S&P 500, Nasdaq, Dow futures with % changes
- VIX level
- DXY (Dollar Index)

**Alert Banner** (when relevant)
- Options expiry notifications
- Major events

#### 3. Market Overview
**Opening Commentary**
- 2-3 paragraph narrative on key theme
- Focus on how individual stock news affects indices
- Example: "Tech giants rallying → Nasdaq strength"

#### 4. The Big Money (S&P Futures Focus)
**Technical Levels & Positioning**
- S&P: Resistance zones, Support clusters, Pivot areas
- **IMPORTANT:** Express as ranges/zones only (e.g., "6,640-6,700 zone")
- Never use exact proprietary strikes
- Options flow commentary (when available from sources)

**Chart:** S&P 500 futures with commentary

#### 5. Instruments to Watch
**Grid of 6 instruments:**
- EUR/USD
- GBP/USD
- Gold
- Oil
- DXY
- VIX

Each with:
- Current price/level
- Change (pips or %)
- Chart image
- Brief commentary (VERBATIM from chart-comments.txt)

#### 6. Today's Calendar
**Economic Events & Timing**
- High impact events (red flag)
- Medium impact events (yellow flag)
- Times in ET
- Central bank speakers
- Data releases

#### 7. Trader Tip
**Daily rotating educational content**

Weekly themes (optional - can be ad-hoc):
- Monday: "Why the Easy Trade is Usually Wrong"
- Tuesday: "Reading Options Flow for Index Direction"
- Wednesday: "When Correlations Break Down"
- Thursday: "Managing Risk Around Economic Data"
- Friday: "OPEX Effects on Index Trading"

**Format:**
- One key trading concept
- Real-world application to current market
- Common pitfalls to avoid
- Key takeaway box

#### 8. Session Outlook
**What to Watch**
- Key levels for breakout/breakdown
- Time-specific events
- Correlation trades to monitor

**Risk Factors**
- Potential volatility triggers
- Overnight gaps
- News flow that could shift sentiment

#### 9. Call to Action & Footer
- "Ready to trade?" CTA with Traze link
- Risk warning
- Unsubscribe/Privacy/Contact links

### Content Guidelines

**Voice & Tone:**
- Professional but accessible
- Educational without being patronizing
- Action-oriented for traders
- Balance between Bloomberg formality and conversational style

**Focus Areas:**
- How news impacts tradeable instruments on Traze platform
- Practical levels and setups
- Risk management emphasis
- **No individual stock recommendations** - only impact analysis

**Length & Format:**
- Concise sections for quick scanning
- Bullet points for key information
- Bold highlighting for important levels/numbers
- Each section should be digestible in 30-60 seconds

**Platform-Specific Notes:**
- Traze offers indices, forex, commodities, and crypto trading
- **No individual stocks are tradeable on the platform**
- Commentary on individual stocks should focus on their impact on indices
- Emphasize instruments available for trading on Traze

### Data Sources for Content

The newsletter synthesizes information from multiple professional sources:
- **SpotGamma**: Options positioning and gamma levels
- **Bloomberg**: Market wrap and corporate news impact
- **TipRanks**: Concise market summaries
- **SqueezeMetrics**: Options flow and dealer positioning
- **WSJ Markets**: Thematic analysis and context (optional)
- **Benzinga**: Futures and pre-market data (optional)

## Daily Newsletter Production

### Quick Start Commands

Use these commands to initiate each stage of newsletter production:

1. **Initialize:** `Start newsletter process for [YYYY-MM-DD]`
   - Analyzes available inputs in `_working/YYYY-MM-DD/`
   - Creates inventory of sources
   - Notes any missing data

2. **Generate:** `Create newsletter draft from inputs`
   - Extracts data from all sources
   - Applies consistency rules
   - Generates `newsletter-draft.md` with all sections

3. **Finalize:** `Generate HTML from approved draft`
   - Converts edited draft to HTML using `_templates/newsletter-template-traze.html`
   - Applies email-safe styling
   - Creates `newsletter-final.html`

### Daily Workflow

#### 1. Input Collection (Manual - 10 min)

Create folder structure:
```bash
_working/YYYY-MM-DD/
├── sources/
│   ├── bloomberg.pdf
│   ├── spotgamma.pdf
│   ├── tipranks.txt
│   ├── benzinga.pdf (optional)
│   └── squeezemetrics.pdf (optional)
└── charts/
    ├── [chart screenshots - any naming OK]
    └── chart-comments.txt (USER-CREATED)
```

**Chart Comments Format:**
```
DXY is on a rip up overnight. Bias is long but wait for a decent pullback.
ES, like NQ, same same
CL is in a range. Sell the top, buy the bottom, don't diddle in the middle
GC had two clear legs down overnight.
6E is the flip side of DXY - wait for a pullback first though.
VIX is climbing
```

#### 2. Processing (Claude Code - 2 min)
- Run: `Start newsletter process for [YYYY-MM-DD]`
- Review inventory of available sources

#### 3. Generate Draft (Claude Code - 5 min)
- Run: `Create newsletter draft from inputs`
- Claude extracts and generates markdown draft
- Saved to `_working/YYYY-MM-DD/newsletter-draft.md`

#### 4. Review & Edit (Manual - 10-15 min)
- Open `newsletter-draft.md`
- Check all sections populated correctly
- **Verify no fabricated data** (check against sources)
- **Verify chart commentary is verbatim from chart-comments.txt**
- Add personal market commentary
- Adjust any incorrect extractions
- Verify data accuracy
- Save edits

#### 5. Finalization (Claude Code - 2 min)
- Run: `Generate HTML from approved draft`
- Claude creates `newsletter-final.html`
- Opens in browser for preview

#### 6. Distribution (Manual - 5 min)
**Primary Method: GitHub Pages**

1. Copy `_working/YYYY-MM-DD/` to `_archive/YYYY-MM-DD/`
2. Rename `newsletter-final.html` → `index.html`
3. Update `_archive/index.html` with new entry
4. Git commit and push
5. Available at: `https://noodlespoodles.github.io/zfx-newsletter/YYYY-MM-DD/`

**Total Time:** ~30-35 minutes

### Processing Standards

#### Data Extraction Rules

1. **Market Snapshot Data**
   - Priority: Bloomberg → Benzinga → TipRanks
   - Look for patterns: "S&P 500 rose/fell X%", "closed at X"
   - Cross-validate between sources when available
   - Use most recent timestamp if conflicts

2. **Technical Levels**
   - Primary source: SpotGamma "Key SG levels"
   - Extract: Support, Resistance, Pivot, Call Wall, Put Wall
   - Include gamma levels and volatility trigger
   - Note OPEX dates and implications

3. **Market Narrative**
   - Combine perspectives from Bloomberg and other sources
   - Extract main theme from opening paragraphs
   - Identify 3-4 key market drivers
   - Focus on index impact, not individual stocks

4. **Trading Focus / Calendar Events**
   - Economic calendar events with times (ET)
   - Central bank speakers
   - Key correlations to monitor
   - Risk factors for the session

#### Data Integrity Rules

**CRITICAL: These rules are absolute and must NEVER be violated**

1. **Never fabricate or invent data**
   - Only use numbers directly extracted from source documents
   - If data is missing, mark as "Data not available" or omit section entirely
   - Never calculate or estimate missing values
   - Never add support/resistance levels without explicit source
   - **No FX levels unless directly from inputs**

2. **Source verification**
   - Every data point must trace to a specific source document
   - If uncertain about a number, don't include it
   - When sources conflict, show both with clear attribution
   - Never fill gaps with "reasonable" estimates or round numbers

3. **Technical levels protection**
   - Always express as ranges/zones, never exact proprietary strikes
   - Use general areas: "upper 6,600s" or "6,640-6,700 zone"
   - Describe regions: "resistance zone" not "6,675 resistance"
   - This protects proprietary SpotGamma data

4. **NEVER expand or embellish content**
   - Use text EXACTLY as provided - no additions, no "clarifications"
   - Chart commentary: Use EXACT wording from `chart-comments.txt`
   - Do not add context, explanations, or interpretive statements
   - Do not "improve" or "enhance" descriptions with professional flourishes
   - If commentary says "GC had two legs down" - write ONLY that, nothing more
   - Do not add market relationships not explicitly stated (e.g., "despite DXY surge")

5. **Verbatim content rules**
   - Chart notes: Copy EXACTLY from `chart-comments.txt`
   - Market narrative: Use ONLY extracted text from sources
   - Technical analysis: Use ONLY descriptions from inputs
   - If something seems incomplete, mark as "[Data not available]" rather than filling gaps
   - No connecting phrases or colour commentary unless in source

6. **Prohibited additions**
   - No interpretive statements beyond source material
   - No assumptions about market behaviour
   - No explanatory text not in original
   - No "professional" writing improvements
   - No creative additions whatsoever

#### Formatting & Style Standards

- **Case:** Sentence case throughout (no ALL CAPS anywhere)
- **Headers:** Capitalise only first word (e.g., "Market snapshot" not "Market Snapshot")
- **Emphasis:** Bold for key terms, never use all caps for emphasis
- **Emojis:** Never use emojis in any content (HTML or text)
- **UK English:** Always use UK spelling (realised, colour, centre, whilst, behaviour)
- **Numbers:** Use commas (6,650 not 6650)
- **Percentages:** Two decimal places (0.44% not 0.4%)
- **Times:** Always include "ET" (10:00 AM ET)
- **Currency pairs:** Standard format (EUR/USD not EURUSD)
- **Index names:** Full names in narrative, symbols in tables

#### Language Standards

- Use "advanced/declined" not "went up/down"
- Use "resistance/support" not "ceiling/floor"
- Maintain professional tone throughout
- Avoid speculation, stick to verifiable facts only

### Quality Checklist

**Before approving draft:**
- [ ] All sections present and populated
- [ ] Data sources identified for each element
- [ ] **All data traced to source documents (no fabrication)**
- [ ] **No made-up FX levels or commodity prices**
- [ ] No conflicting information between sections
- [ ] Times displayed in ET format
- [ ] Numbers formatted consistently with commas
- [ ] Sentence case used throughout (no ALL CAPS)
- [ ] **No emojis present anywhere**
- [ ] UK English spelling verified
- [ ] **Technical levels expressed as zones/ranges only**
- [ ] Professional tone maintained
- [ ] Charts referenced match available files in `charts/` folder
- [ ] **Chart commentary is VERBATIM from chart-comments.txt**
- [ ] Trader tip is relevant and educational
- [ ] **No individual stock recommendations**

**Before publishing:**
- [ ] HTML renders correctly in browser
- [ ] Mobile responsive design working
- [ ] All charts displaying properly
- [ ] All image paths correct (relative paths)
- [ ] Links functional (if any)
- [ ] Date and session correct
- [ ] Final proofread complete
- [ ] Archive folder created with YYYY-MM-DD format

### Handling Missing Sources

If sources are missing:
1. Note at start of draft which sources unavailable
2. Use available sources to fill sections
3. Mark low-confidence extractions clearly
4. **Omit sections that require missing source** (don't guess)
5. Never guess or fabricate data

### Conflict Resolution

When sources disagree:
1. Show both values with source attribution
2. Use most recent/reliable source as primary
3. Note conflict in draft for manual review
4. Apply these priorities:
   - Prices: Most recent source
   - Levels: SpotGamma > others
   - News: Bloomberg > others
   - Sentiment: Consensus across sources

### HTML Asset Path Rules

**For Archive (GitHub Pages):**
- Charts: `charts/[filename].png` (relative path)
- Logo: `../_assets/traze/_logo_traze_light.png` (relative path from archive folder)

**Path Testing:**
- [ ] Open HTML file directly in browser (file:// path)
- [ ] All images should load
- [ ] If any broken, fix paths before publishing

## Common Issues & Solutions

### Issue: Chart Commentary Was Embellished
**Symptom:** Chart descriptions contain context not in chart-comments.txt
**Cause:** AI attempted to "improve" or "enhance" descriptions
**Solution:** Regenerate section with explicit instruction: "Use EXACT text from chart-comments.txt with NO additions"

### Issue: FX Levels Were Fabricated
**Symptom:** EUR/USD, GBP/USD levels appear but weren't in sources
**Cause:** AI filled gaps with invented data
**Solution:** Remove entire section. Only include if explicitly in sources.

### Issue: Broken Image Paths
**Symptom:** Charts don't display in published HTML
**Cause:** Absolute paths used instead of relative
**Solution:** Ensure paths are relative: `charts/filename.png` not `/full/path/`

### Issue: Date Folder Format Confusion
**Symptom:** Mixed DDMMYYYY and YYYY-MM-DD folders
**Cause:** Inconsistent naming convention
**Solution:** Use YYYY-MM-DD format for all archive folders

## Emergency Procedures

### If Newsletter Contains Fabricated Data
1. **STOP** - do not publish
2. Regenerate section from scratch with explicit source reference
3. Manually verify every number against source documents
4. If unsure, omit data entirely

### If Critical Source Missing (Bloomberg or SpotGamma)
- Mark newsletter as "LIMITED DATA" in header
- Skip sections that require missing source
- Note missing source in newsletter
- Proceed with available data only

### If HTML Generation Fails
- Check template path: `_templates/newsletter-template-traze.html`
- Verify all chart image files exist
- Use previous day's HTML as fallback base
- Manually update key sections only

---

*Last updated: October 2025*
*Current template: newsletter-template-traze.html*
*Distribution: GitHub Pages (https://noodlespoodles.github.io/zfx-newsletter/)*
