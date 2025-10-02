# Daily Newsletter Production Process

This checklist ensures consistent, high-quality newsletter production every day.

**Estimated Total Time:** 30-35 minutes
**Target Completion:** Before market open (7:30 AM ET)

---

## Stage 1: Input Collection (Manual - 10 min)

### Folder Setup

Navigate to: `_working/` folder

Create today's dated folder:
```bash
_working/YYYY-MM-DD/
├── sources/
└── charts/
```

Example: `_working/2025-09-25/`

### Collect Source Documents

Place in `sources/` subfolder:
- [ ] **bloomberg.pdf** - "Stock Market Today" PDF
- [ ] **spotgamma.pdf** - "Founder's Notes" or "Key SG Levels"
- [ ] **tipranks.txt** - Market summary (text or PDF)
- [ ] **benzinga.pdf** - Morning dashboard (optional)
- [ ] **squeezemetrics.pdf** - Options flow (optional)

**Missing Sources:** Note which sources are unavailable (affects confidence)

### Collect Charts

Place in `charts/` subfolder:
- [ ] Screenshot S&P 500 futures (ES) - any filename OK
- [ ] Screenshot EUR/USD (6E) - any filename OK
- [ ] Screenshot GBP/USD - any filename OK (optional)
- [ ] Screenshot Gold (GC) - any filename OK
- [ ] Screenshot Oil (CL) - any filename OK
- [ ] Screenshot DXY - any filename OK
- [ ] Screenshot VIX - any filename OK

**Chart file naming:** Any naming convention is acceptable (e.g., "Screenshot 2025-09-25 144309.png" or "ES_2025-09-25.png")

### Create Chart Commentary

Create file: `charts/chart-comments.txt`

**Format:** One line per instrument, plain text, your trading commentary

**Example:**
```
DXY is on a rip up overnight. Bias is long but wait for a decent pullback. Watch the indexes to correlate.
NQ recovered somewhat in the overnight but expect more aggressive selling. Lots of options flow (aka resistance) between 24760 and 24822.
ES, like NQ, same same
CL is in a range. Sell the top, buy the bottom, don't diddle in the middle
GC had two clear legs down overnight. Wait for price action to develop and potentially play the range with a short intraday bias.
6E is the flip side of DXY - wait for a pullback first though.
VIX is climbing
```

**IMPORTANT:** This commentary will be used VERBATIM in the newsletter. Write exactly what you want to appear.

---

## Stage 2: Initialize (Claude Code - 2 min)

### Command
Open Claude Code and run:
```
Start newsletter process for YYYY-MM-DD
```

Example: `Start newsletter process for 2025-09-25`

### What Claude Does
- Analyzes files in `_working/YYYY-MM-DD/sources/`
- Analyzes files in `_working/YYYY-MM-DD/charts/`
- Creates inventory of available sources
- Notes any missing data sources
- Reports extraction confidence level

### Review Inventory
- [ ] Claude found all expected source files
- [ ] Claude found chart-comments.txt
- [ ] Claude noted any missing sources
- [ ] Confidence level is acceptable (High/Medium)

**If Low Confidence:** Verify source files are in correct folder

---

## Stage 3: Generate Draft (Claude Code - 5 min)

### Command
```
Create newsletter draft from inputs
```

### What Claude Does
- Extracts market data from source PDFs
- Extracts technical levels from SpotGamma
- Extracts market narrative from Bloomberg
- Copies chart commentary VERBATIM from chart-comments.txt
- Applies all data integrity rules
- Applies formatting standards (UK English, sentence case, no emojis)
- Generates `newsletter-draft.md` in `_working/YYYY-MM-DD/`

### Initial Verification
Claude should automatically verify:
- [ ] All 9 sections populated (Header, Snapshot, Overview, Big Money, Instruments, Calendar, Tip, Outlook, CTA/Footer)
- [ ] No fabricated data present
- [ ] Chart commentary is verbatim from chart-comments.txt
- [ ] Sentence case throughout (no ALL CAPS)
- [ ] No emojis present
- [ ] UK spelling used
- [ ] Technical levels shown as zones/ranges (not exact strikes)

---

## Stage 4: Review & Edit (Manual - 10-15 min)

### Open Draft
Open file: `_working/YYYY-MM-DD/newsletter-draft.md`

### Data Integrity Verification

**CRITICAL CHECKS:**
- [ ] **No fabricated FX levels** - EUR/USD, GBP/USD levels only if from sources
- [ ] **No invented commodity prices** - Gold, Oil prices match sources
- [ ] **No made-up index values** - S&P, Nasdaq, DXY match sources
- [ ] **Chart commentary is EXACT** - Compare against chart-comments.txt word-for-word
- [ ] **All numbers trace to sources** - Can you find each number in the source PDFs?

**If ANY data looks fabricated:**
1. STOP - do not proceed
2. Delete the fabricated section
3. Regenerate with explicit source reference
4. Verify against source document

### Content Quality Check
- [ ] Market narrative makes sense
- [ ] Technical levels align with current market context
- [ ] No contradictions between sections
- [ ] Trader tip is educational and relevant
- [ ] Economic calendar events are accurate and in ET timezone
- [ ] Session outlook is actionable

### Style Compliance
- [ ] Sentence case throughout (e.g., "Market overview" not "Market Overview")
- [ ] No ALL CAPS anywhere
- [ ] No emojis present anywhere
- [ ] UK English spelling (realised, whilst, colour, behaviour)
- [ ] Numbers have commas (6,650 not 6650)
- [ ] Percentages have two decimals (0.44% not 0.4%)
- [ ] Times include "ET" (10:00 AM ET)
- [ ] Currency pairs in standard format (EUR/USD not EURUSD)

### Add Personal Commentary
- [ ] Add any additional market insights
- [ ] Adjust tone if needed
- [ ] Enhance trader tip if desired
- [ ] Add any risk warnings

### Save Edits
Save `newsletter-draft.md` with your changes

---

## Stage 5: Generate HTML (Claude Code - 2 min)

### Command
```
Generate HTML from approved draft
```

### What Claude Does
- Loads `_templates/newsletter-template-traze.html` as base
- Inserts content from edited `newsletter-draft.md`
- Applies Traze branding and styling
- Sets up relative paths for charts
- Generates `newsletter-final.html` in `_working/YYYY-MM-DD/`
- Opens in browser for preview

### HTML Preview Check
- [ ] Browser opens with newsletter preview
- [ ] Traze logo displays correctly
- [ ] Dark gradient header displays
- [ ] All chart images display
- [ ] Pill-shaped buttons render correctly
- [ ] Gradient section dividers visible
- [ ] Footer dark styling correct
- [ ] Date and session time correct

### Mobile Responsive Check
- [ ] Resize browser to mobile width (~400px)
- [ ] Content stacks to single column
- [ ] Images resize appropriately
- [ ] Text remains readable
- [ ] Buttons remain clickable

**If any issues:** Note them and fix before publishing

---

## Stage 6: Publish to GitHub Pages (Manual - 5 min)

### Prepare Archive Folder

Create archive folder structure:
```bash
_archive/YYYY-MM-DD/
├── charts/
└── (index.html will go here)
```

### Copy Files

```bash
# Copy from working to archive
cp _working/YYYY-MM-DD/newsletter-final.html _archive/YYYY-MM-DD/index.html
cp -r _working/YYYY-MM-DD/charts/* _archive/YYYY-MM-DD/charts/
```

### Update Archive Index

Edit `_archive/index.html` to add new entry:
```html
<li class="newsletter-item">
  <a href="YYYY-MM-DD/index.html">Daily Market Snapshot - [Month DD, YYYY]</a>
  <div class="date">US session - [Brief description]</div>
</li>
```

### Git Commit & Push

```bash
cd "US Session Newsletter"
git add _archive/YYYY-MM-DD/
git add _archive/index.html
git commit -m "Add YYYY-MM-DD newsletter"
git push origin main
```

### Verify Published

Wait 1-2 minutes, then visit:
```
https://noodlespoodles.github.io/zfx-newsletter/YYYY-MM-DD/
```

**Final Checks:**
- [ ] Newsletter displays correctly
- [ ] All charts load
- [ ] Logo displays
- [ ] Mobile responsive works
- [ ] Archive index updated

---

## Data Integrity Standards

### Absolute Requirements

**These rules must NEVER be violated:**

1. **Only use data directly from source documents**
   - If you can't find the number in a source PDF, don't include it
   - Never estimate, calculate, or approximate
   - Never use yesterday's data as a placeholder

2. **Chart commentary must be VERBATIM**
   - Copy EXACTLY from chart-comments.txt
   - No additions, no clarifications, no enhancements
   - If commentary says "GC had two legs down" - use ONLY that text

3. **Technical levels as zones/ranges only**
   - "6,640-6,700 resistance zone" ✓
   - "6,675 resistance" ✗ (exact proprietary level)
   - "Upper 6,600s" ✓
   - "6,650" ✗ (exact proprietary strike)

4. **No FX levels unless from sources**
   - If Bloomberg doesn't mention EUR/USD support/resistance, don't include it
   - Don't fabricate Fibonacci levels
   - Don't add "common sense" round numbers

5. **UK English spelling**
   - realised (not realized)
   - colour (not color)
   - centre (not center)
   - whilst (not while)
   - behaviour (not behavior)

### Common Fabrication Mistakes to Avoid

❌ **DON'T DO THIS:**
- "EUR/USD support at 1.1700, resistance at 1.1800" (if not in sources)
- "Gold holding well despite DXY surge" (if "despite DXY surge" not in chart-comments.txt)
- "S&P resistance at 6,675" (exact strike instead of zone)
- "Markets are BULLISH" (all caps for emphasis)
- "📊 Market Overview" (emoji in heading)

✓ **DO THIS:**
- Only include FX levels if explicitly mentioned in Bloomberg or other sources
- Use EXACT text from chart-comments.txt: "GC had two legs down overnight"
- "S&P resistance zone: 6,640-6,700 area"
- "Markets are bullish" (sentence case)
- "Market overview" (no emoji, sentence case)

---

## Troubleshooting

### Issue: Claude Fabricated Data

**Symptoms:**
- FX levels appear that weren't in sources
- Chart commentary includes context not in chart-comments.txt
- Numbers that don't match any source document

**Solution:**
1. STOP - do not proceed to HTML generation
2. Identify fabricated sections
3. Delete fabricated content
4. Ask Claude: "Regenerate [section name] using ONLY data from [specific source file]"
5. Manually verify every number against source

### Issue: Missing Critical Source

**Bloomberg or SpotGamma unavailable:**
1. Note in newsletter header: "LIMITED DATA - [Source] unavailable"
2. Skip sections that require missing source:
   - No Bloomberg = Skip market narrative
   - No SpotGamma = Skip technical levels
3. Proceed with available data only
4. Reduce confidence/scope of newsletter

**Optional sources missing (Benzinga, SqueezeMetrics):**
- Proceed normally, work with available data

### Issue: Low Extraction Confidence

**Causes:**
- Source files corrupted or unreadable
- Unusual PDF format
- Source file in wrong location

**Solutions:**
- Verify source files open correctly in PDF reader
- Check file is in `_working/YYYY-MM-DD/sources/` folder
- Try re-downloading source file
- Use alternative source if available

### Issue: Chart Images Not Displaying

**Causes:**
- Charts folder missing
- File paths incorrect
- Files not copied to archive

**Solutions:**
- Verify charts exist in `_working/YYYY-MM-DD/charts/`
- Check HTML uses relative paths: `charts/filename.png`
- Ensure charts copied to `_archive/YYYY-MM-DD/charts/`

### Issue: HTML Generation Failed

**Solutions:**
1. Verify template exists: `_templates/newsletter-template-traze.html`
2. Check draft file is valid markdown
3. Verify all chart files referenced in draft exist
4. Try regenerating: "Generate HTML from approved draft"
5. If still failing, use previous day's HTML as base and manually edit

---

## Quick Reference: Commands

### Daily Production Commands
1. `Start newsletter process for YYYY-MM-DD`
2. `Create newsletter draft from inputs`
3. `Generate HTML from approved draft`

### Troubleshooting Commands
- `Show extraction confidence for [date]` - Check data quality
- `Regenerate [section name] from [source file]` - Fix specific section
- `List available sources for [date]` - Verify input inventory

---

## Time Estimates

| Stage | Time | Can Skip? |
|-------|------|-----------|
| Input Collection | 10 min | No |
| Initialize | 2 min | No |
| Generate Draft | 5 min | No |
| Review & Edit | 10-15 min | No |
| Generate HTML | 2 min | No |
| Publish to GitHub | 5 min | No |
| **TOTAL** | **30-35 min** | - |

**Target Completion:** 7:30 AM ET (before market open)

**Latest Start Time:** 7:00 AM ET (assumes no issues)

---

## Daily Production Checklist (Print This)

**Date: _________**

### Pre-Production
- [ ] Created `_working/YYYY-MM-DD/sources/` folder
- [ ] Created `_working/YYYY-MM-DD/charts/` folder
- [ ] Downloaded Bloomberg PDF → sources/
- [ ] Downloaded SpotGamma PDF → sources/
- [ ] Downloaded TipRanks → sources/
- [ ] Created chart screenshots → charts/
- [ ] Created chart-comments.txt → charts/

### Processing
- [ ] Ran: "Start newsletter process for YYYY-MM-DD"
- [ ] Reviewed inventory (all sources found)
- [ ] Ran: "Create newsletter draft from inputs"
- [ ] Opened newsletter-draft.md

### Review
- [ ] Verified no fabricated FX levels
- [ ] Verified chart commentary is verbatim
- [ ] Verified all numbers trace to sources
- [ ] Checked sentence case (no ALL CAPS)
- [ ] Checked no emojis present
- [ ] Checked UK English spelling
- [ ] Added personal commentary
- [ ] Saved edits

### HTML & Publish
- [ ] Ran: "Generate HTML from approved draft"
- [ ] Previewed in browser (desktop view)
- [ ] Previewed in browser (mobile view)
- [ ] Created `_archive/YYYY-MM-DD/` folder
- [ ] Copied newsletter-final.html → index.html
- [ ] Copied charts/ folder
- [ ] Updated _archive/index.html
- [ ] Git commit and push
- [ ] Verified published URL

**Issues Encountered:**
```
(note any problems for process improvement)
```

**Time Taken:** _____ minutes

---

*Last updated: October 2025*
*For detailed guidance, see: _docs/CLAUDE.md*
