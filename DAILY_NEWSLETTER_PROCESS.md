# Daily Newsletter Production Checklist

This checklist ensures consistent, high-quality newsletter production every day.

## Pre-Processing Checklist
*Check off each item before starting extraction*

### Input Verification
- [ ] All inputs placed in today's dated folder
- [ ] Bloomberg PDF present
- [ ] SpotGamma PDF present  
- [ ] TipRanks text/PDF present
- [ ] WSJ Markets PDF present
- [ ] SqueezeMetrics PDF present (if available)
- [ ] Chart images present:
  - [ ] ES.png (S&P 500 futures)
  - [ ] eurusd.png
  - [ ] gbpusd.png
  - [ ] gold.png
  - [ ] oil.png
  - [ ] dxy.png (Dollar Index)
  - [ ] vix.png (Volatility)
  - [ ] 10yr.png (10-year yield) - optional
- [ ] Any manual notes or corrections added

### Missing Source Notes
*List any missing sources here:*
```
Missing: 
```

## Data Integrity Verification
*Critical rules - never violate these*

### Absolute Requirements
- [ ] Only use data directly from source documents
- [ ] Never invent FX levels, commodity prices, or index values
- [ ] If data missing, mark as "Not available" - never estimate
- [ ] Every number must trace to a specific source file
- [ ] When unsure, exclude rather than guess
- [ ] NO EMBELLISHMENT - use exact wording from sources
- [ ] Chart commentary must be VERBATIM from Chart comments.txt
- [ ] No adding "colour" or "context" not in original text

### Style Requirements
- [ ] Sentence case only (no ALL CAPS anywhere)
- [ ] No emojis in any section
- [ ] UK English spelling throughout (realised, colour, whilst, behaviour)
- [ ] Technical levels as ranges/zones only (e.g., "upper 6,600s" not "6,675")
- [ ] No specific proprietary strike prices

## Processing Steps
*Execute in order*

### Stage 1: Initialize
- [ ] Run: "Start newsletter process for [TODAY'S DATE]"
- [ ] Review inventory of available sources
- [ ] Note any extraction warnings

### Stage 2: Extract & Generate
- [ ] Run: "Create newsletter draft from inputs"
- [ ] Verify all sections populated:
  - [ ] Market Snapshot complete
  - [ ] Technical Levels extracted
  - [ ] Market Narrative present
  - [ ] Market Drivers identified (3-4 bullets)
  - [ ] Trading Focus events listed
  - [ ] Trader Tip matches day of week
  - [ ] Session Outlook populated
  - [ ] Chart references correct
- [ ] Verify data integrity:
  - [ ] No fabricated data present
  - [ ] All numbers trace to sources
  - [ ] No made-up FX levels
  - [ ] Missing data marked as unavailable
  - [ ] Chart commentary is EXACT from Chart comments.txt
  - [ ] No embellishments or additions to source text
- [ ] Verify style compliance:
  - [ ] Sentence case throughout
  - [ ] No emojis present
  - [ ] UK spelling used
  - [ ] Levels shown as zones/ranges

### Stage 3: Quality Review
- [ ] Data accuracy check:
  - [ ] Index levels reasonable (no 50% moves)
  - [ ] Forex rates within normal ranges
  - [ ] Times shown in ET format
  - [ ] Percentages to 2 decimal places
- [ ] Consistency check:
  - [ ] Numbers formatted with commas
  - [ ] Currency pairs in standard format
  - [ ] Professional language throughout
- [ ] Source attribution:
  - [ ] Conflicts noted and resolved
  - [ ] Low-confidence data flagged
  - [ ] Sources cited where needed

## Manual Review & Edit
*Your review before finalizing*

### Content Review
- [ ] Market narrative makes sense
- [ ] Technical levels align with current market
- [ ] No contradictions between sections
- [ ] Trader tip is educational and relevant
- [ ] Personal commentary added where appropriate

### Final Edits
- [ ] Spelling and grammar checked
- [ ] Tone appropriate for professional traders
- [ ] ZFX platform limitations respected (no individual stocks)
- [ ] Risk disclaimers appropriate

## Finalization Steps

### HTML Generation
- [ ] Run: "Generate HTML from approved draft"
- [ ] Preview HTML in browser
- [ ] Check mobile responsiveness
- [ ] Verify all charts display correctly
- [ ] Test any links (if present)

### Pre-Send Checklist
- [ ] Date and session time correct
- [ ] Subject line prepared
- [ ] Distribution list verified
- [ ] Send time scheduled appropriately

## Post-Send Review
*For continuous improvement*

- [ ] Note any issues encountered today
- [ ] Update process documentation if needed
- [ ] Save successful draft as template reference

## Daily Commands Reference

### Standard Commands
1. **Start:** `Start newsletter process for [date]`
2. **Draft:** `Create newsletter draft from inputs`
3. **HTML:** `Generate HTML from approved draft`

### Troubleshooting Commands
- `Show extraction conflicts` - Display any data discrepancies
- `Regenerate section [SECTION_NAME]` - Redo specific section
- `Apply manual override for [DATA_POINT]` - Force specific value

## Notes for Today
*Space for process notes, issues, or improvements:*
```
Date: 
Issues: 
Improvements for tomorrow:
```