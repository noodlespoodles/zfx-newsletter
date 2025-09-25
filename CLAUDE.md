# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the ZFX US Session Newsletter project - a professional HTML email newsletter template and deployment system for ZFX's daily market snapshots. The project contains HTML templates, market charts, branding assets, and deployment configurations for GitHub Pages.

## Project Structure

- **Main Newsletter Files:**
  - `Sample.html` - Original template file
  - `Sample_Refined.html` - Refined version of the template
  - `newsletter_upload/index.html` - Production-ready newsletter for GitHub Pages deployment

- **Assets:**
  - `Branding/` - Brand assets including favicon
  - `Inputs/Charts/` - Market chart images (ES, EUR/USD, GBP/USD, Gold, Oil, etc.)
  - `ZFX_logo.png` - Company logo

- **Deployment:**
  - `newsletter_upload/` - GitHub Pages deployment directory with self-contained assets

## Key Information

### Newsletter Purpose
The newsletter provides daily market analysis for traders including:
- S&P 500 futures analysis
- Forex pairs (EUR/USD, GBP/USD, USD/JPY)
- Commodities (Gold, Oil)
- Market indices
- Key support/resistance levels
- Options expiry alerts

### HTML Structure
- Uses XHTML 1.0 Transitional for email compatibility
- Microsoft Office conditional comments for Outlook support
- Inline CSS for email client compatibility
- Responsive design with mobile breakpoints at 600px
- ZFX brand colors defined as CSS variables

### Brand Colors
```css
--zfx-primary: #2d78bd
--zfx-primary-light: #57a0f7
--zfx-dark-bg: #0a264e
--zfx-success: #1fb587
--zfx-danger: #da372d
```

## Common Tasks

### Updating Newsletter Content
Edit the HTML files directly - no build process required. Key sections to update:
- Market analysis text
- Chart images in `Charts/` directory
- Timing information and key levels
- Date/timestamp information

### Deploying to GitHub Pages
The `newsletter_upload/` directory is configured for GitHub Pages:
1. Push changes to GitHub repository
2. Enable GitHub Pages from repository settings
3. Newsletter will be available at `https://[username].github.io/[repo-name]/`

### Working with Charts
Charts are PNG images stored in:
- `Inputs/Charts/` - Source charts
- `newsletter_upload/Charts/` - Production charts

Standard chart files: ES.png, eurusd.png, gbpusd.png, gold.png, oil.png, dxy.png, vix.png, 10yr.png

## Newsletter Content Framework

### Content Structure

The newsletter follows a structured format optimized for traders using the ZFX platform (indices, forex, commodities, crypto - no individual stock trading).

#### 1. Header & Branding
- ZFX logo and tagline
- Date/Time with session identifier (e.g., "US Session - September 19, 2025")
- Brief market sentiment indicator (Risk On/Risk Off/Neutral)

#### 2. Market Snapshot Dashboard
**Key Indices** (relevant to ZFX platform)
- S&P 500, Nasdaq, Dow futures with % changes
- European indices (DAX, FTSE, CAC)
- Asian indices (Nikkei, Hang Seng, Shanghai)

**Forex Majors Grid**
- EUR/USD, GBP/USD, USD/JPY with pip movements
- DXY (Dollar Index) as reference point

**Commodities**
- Gold, Silver, Oil with % changes
- Key levels for each

**Crypto Corner**
- BTC, ETH prices and 24h changes
- Market cap dominance metrics

**Volatility Metrics**
- VIX level with context (high/low/normal)
- Term structure if relevant

#### 3. Technical Levels & Positioning
**Key Support/Resistance**
- S&P: Pivot, Support, Resistance levels
- Major forex pairs: Daily pivots
- Gold/Oil: Key technical levels

**Options Flow Context** (when relevant)
- OPEX dates and implications for indices
- Major gamma levels affecting market
- Simple explanation of positioning impact

#### 4. Market Narrative
**Opening Commentary**
- 2-3 paragraph narrative on key theme
- Focus on how individual stock news affects indices
- Example: "Tech giants rallying → Nasdaq strength"

**Market Drivers** (3-4 bullets)
- Fed policy implications
- Economic data impacts
- Geopolitical factors
- Sector rotation effects on indices

#### 5. Trading Focus
**Index Impact Analysis**
- How major stock moves affect index weightings
- Sector performance driving index direction
- Example: "NVDA +4% adding 15 points to Nasdaq"

**Cross-Asset Correlations**
- Dollar strength impact on commodities
- Risk sentiment flow (stocks → crypto)
- Bond yields affecting forex

**Key Events & Timing**
- Economic releases with expected impact
- Central bank speakers
- Options expiry effects

#### 6. Trader Tips Section
Daily rotating educational content inspired by professional trading education:

**Weekly Schedule:**
- Monday: "Why the Easy Trade is Usually Wrong"
- Tuesday: "Reading Options Flow for Index Direction"
- Wednesday: "When Correlations Break Down"
- Thursday: "Managing Risk Around Economic Data"
- Friday: "OPEX Effects on Index Trading"

**Format:**
- One key trading concept per day
- Real-world application to current market
- Common pitfalls to avoid
- Actionable insight for the session

#### 7. Session Outlook
**What to Watch**
- Key levels for breakout/breakdown
- Time-specific events (e.g., "10:00 AM Consumer Confidence")
- Correlation trades to monitor

**Risk Factors**
- Potential volatility triggers
- Overnight gaps to be aware of
- News flow that could shift sentiment

#### 8. Charts Section
6 clean charts with annotations:
- S&P 500 futures (ES)
- EUR/USD
- Gold
- Oil
- DXY
- VIX or key sector ETF

### Content Guidelines

**Voice & Tone:**
- Professional but accessible
- Educational without being patronizing
- Action-oriented for traders
- Balance between Bloomberg formality and conversational style

**Focus Areas:**
- How news impacts tradeable instruments on ZFX platform
- Practical levels and setups
- Risk management emphasis
- No individual stock recommendations, only impact analysis

**Length & Format:**
- Concise sections for quick scanning
- Bullet points for key information
- Bold highlighting for important levels/numbers
- Each section should be digestible in 30-60 seconds

**Platform-Specific Notes:**
- ZFX offers indices, forex, commodities, and crypto trading
- No individual stocks are tradeable on the platform
- Commentary on individual stocks should focus on their impact on indices
- Emphasize instruments available for trading on ZFX

### Data Sources for Content

The newsletter synthesizes information from multiple professional sources:
- **SpotGamma**: Options positioning and gamma levels
- **Bloomberg**: Market wrap and corporate news impact
- **TipRanks**: Concise market summaries
- **SqueezeMetrics**: Options flow and dealer positioning
- **WSJ Markets**: Thematic analysis and context
- **Benzinga**: Futures and pre-market data

## Daily Newsletter Production

### Quick Start Commands
Use these commands to initiate each stage of newsletter production:

1. **Initialize:** "Start newsletter process for [date]"
   - Analyzes available inputs
   - Creates inventory of sources
   - Notes any missing data

2. **Generate:** "Create newsletter draft from inputs"
   - Extracts data from all sources
   - Applies consistency rules
   - Generates draft document with all sections

3. **Finalize:** "Generate HTML from approved draft"
   - Converts edited draft to HTML
   - Applies email-safe styling
   - Embeds charts appropriately

### Daily Workflow

1. **Input Collection** (Manual)
   - Place all available sources in dated folder
   - Include: PDFs, text files, chart images, manual notes
   - Expected sources: Bloomberg, SpotGamma, TipRanks, WSJ, SqueezeMetrics

2. **Processing** (Claude Code)
   - Run: "Start newsletter process for [date]"
   - Review inventory of available sources
   - Run: "Create newsletter draft from inputs"

3. **Review & Edit** (Manual)
   - Check all sections populated correctly
   - Add personal market commentary
   - Adjust any incorrect extractions
   - Verify data accuracy

4. **Finalization** (Claude Code)
   - Run: "Generate HTML from approved draft"
   - Review HTML preview
   - Copy to email platform (Mailchimp, etc.)

5. **Distribution** (Manual)
   - Final quality check
   - Send via email platform

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
   - Combine perspectives from WSJ and Bloomberg
   - Extract main theme from opening paragraphs
   - Identify 3-4 key market drivers
   - Focus on index impact, not individual stocks

4. **Trading Focus**
   - Economic calendar events with times (ET)
   - Central bank speakers
   - Key correlations to monitor
   - Risk factors for the session

#### Data Integrity Rules
1. **Never fabricate or invent data**
   - Only use numbers directly extracted from source documents
   - If data is missing, mark as "Data not available" or omit section entirely
   - Never calculate or estimate missing values
   - Never add support/resistance levels without explicit source
   - No FX levels unless directly from inputs

2. **Source verification**
   - Every data point must trace to a specific source document
   - If uncertain about a number, don't include it
   - When sources conflict, show both with clear attribution
   - Never fill gaps with "reasonable" estimates or round numbers

3. **Technical levels protection**
   - Always express as ranges/zones, never exact proprietary strikes
   - Use general areas: "upper 6,600s" not "6,675"
   - Describe regions: "resistance zone" not specific levels

4. **NEVER expand or embellish content**
   - Use text EXACTLY as provided - no additions, no "clarifications"
   - Chart commentary: Use EXACT wording from Chart comments.txt
   - Do not add context, explanations, or interpretive statements
   - Do not "improve" or "enhance" descriptions with professional flourishes
   - If commentary says "GC had two legs down" - write ONLY that, nothing more
   - Do not add market relationships not explicitly stated (e.g., "despite DXY surge")

5. **Verbatim content rules**
   - Chart notes: Copy EXACTLY from Chart comments.txt
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
- **Emojis:** Never use emojis in any content
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

Before approving draft:
- [ ] All 8 sections present and populated
- [ ] Data sources identified for each element
- [ ] All data traced to source documents (no fabrication)
- [ ] No made-up FX levels or commodity prices
- [ ] No conflicting information between sections
- [ ] Times displayed in ET format
- [ ] Numbers formatted consistently with commas
- [ ] Sentence case used throughout (no ALL CAPS)
- [ ] No emojis present anywhere
- [ ] UK English spelling verified
- [ ] Technical levels expressed as zones/ranges only
- [ ] Professional tone maintained
- [ ] Charts referenced match available files
- [ ] Trader tip matches day of week
- [ ] No individual stock recommendations

Before sending:
- [ ] HTML renders correctly in browser
- [ ] Mobile responsive design working
- [ ] All charts displaying properly
- [ ] Links functional (if any)
- [ ] Date and session correct
- [ ] Final proofread complete

### Handling Missing Sources

If sources are missing:
1. Note at start of draft which sources unavailable
2. Use available sources to fill sections
3. Mark low-confidence extractions clearly
4. Provide fallback content where possible
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