# Folder Reorganization Plan

## Current State (Messy)
```
US Session Newsletter/
├── 25092025/ (working folder - DDMMYYYY format)
├── 2025-09-25/ (archive folder - YYYY-MM-DD format)
├── Branding/ (brand assets - mixed ZFX and Traze)
├── Charts/ (orphaned charts - unclear purpose)
├── Inputs/ (example inputs - not dated)
├── Newsletter design examples/ (reference materials)
├── ZFX_.../ (web scrape files - not needed)
├── newsletter_upload/ (old deployment folder)
├── Sample.html, Sample_Refined.html (legacy templates)
├── index.html, index_archive.html (orphaned HTML)
├── newsletter_template_traze.html (CURRENT TEMPLATE)
├── ZFX_logo.png (orphaned logo)
└── Documentation (.md files)
```

## Proposed Clean Structure
```
US Session Newsletter/
│
├── _archive/                      # Published newsletters archive
│   ├── 2025-09-25/
│   │   ├── index.html
│   │   ├── Charts/
│   │   └── ZFX_logo.png
│   └── index.html                 # Archive index/navigation
│
├── _working/                      # Daily production workspace
│   └── YYYY-MM-DD/               # Today's date folder
│       ├── sources/
│       │   ├── bloomberg.pdf
│       │   ├── spotgamma.pdf
│       │   ├── tipranks.txt
│       │   ├── benzinga.pdf
│       │   └── squeezemetrics.pdf
│       ├── charts/
│       │   ├── [chart screenshots]
│       │   └── chart-comments.txt
│       ├── newsletter-draft.md
│       └── newsletter-final.html
│
├── _templates/                    # Templates and production files
│   ├── newsletter-template-traze.html  # CURRENT PRODUCTION TEMPLATE
│   └── legacy/
│       ├── sample.html
│       └── sample-refined.html
│
├── _assets/                       # Brand assets
│   └── traze/
│       ├── logo-light.png
│       ├── logo-dark.png
│       └── favicon/
│
├── _reference/                    # Reference materials
│   ├── design-examples/
│   │   └── [newsletter design PNGs]
│   └── sample-inputs/            # Example inputs for testing
│       ├── bloomberg-example.pdf
│       └── spotgamma-example.pdf
│
└── _docs/                         # Documentation
    ├── CLAUDE.md
    ├── README.md
    ├── DAILY_NEWSLETTER_PROCESS.md
    └── NEWSLETTER_TEMPLATE.md
```

## Migration Actions

### 1. Create New Folder Structure
- Create `_archive/`, `_working/`, `_templates/`, `_assets/`, `_reference/`, `_docs/`
- Underscore prefix keeps them at top of alphabetical listing

### 2. Move Documentation
- CLAUDE.md → `_docs/CLAUDE.md`
- README.md → `_docs/README.md`
- DAILY_NEWSLETTER_PROCESS.md → `_docs/DAILY_NEWSLETTER_PROCESS.md`
- NEWSLETTER_TEMPLATE.md → `_docs/NEWSLETTER_TEMPLATE.md`
- Keep README.md copy in root for GitHub

### 3. Move Templates
- newsletter_template_traze.html → `_templates/newsletter-template-traze.html`
- Sample.html → `_templates/legacy/sample.html`
- Sample_Refined.html → `_templates/legacy/sample-refined.html`

### 4. Move Assets
- Branding/Traze/ → `_assets/traze/`
- ZFX_logo.png → DELETE (outdated branding)

### 5. Move Archives
- 2025-09-25/ → `_archive/2025-09-25/`
- index_archive.html → `_archive/index.html`
- index.html → DELETE or move to archive if relevant

### 6. Move Reference Materials
- Newsletter design examples/ → `_reference/design-examples/`
- Inputs/ → `_reference/sample-inputs/` (rename files for clarity)

### 7. Consolidate Working Folders
- 25092025/ → `_working/2025-09-25/` (standardize to YYYY-MM-DD)
- Reorganize internal structure to sources/ and charts/ subfolders

### 8. Delete Obsolete
- ZFX_ Forex & CFDs... folder (web scrape, not needed)
- Charts/ (orphaned, unclear purpose)
- newsletter_upload/ (old deployment method)

## New Daily Workflow

### Setup (First Time)
```bash
cd "_working"
mkdir YYYY-MM-DD
cd YYYY-MM-DD
mkdir sources charts
```

### Collect Inputs
```
_working/YYYY-MM-DD/
├── sources/
│   ├── bloomberg.pdf
│   ├── spotgamma.pdf
│   ├── tipranks.txt
│   ├── benzinga.pdf (optional)
│   └── squeezemetrics.pdf (optional)
└── charts/
    ├── [screenshots - any naming OK]
    └── chart-comments.txt
```

### Process
1. Claude processes from `_working/YYYY-MM-DD/`
2. Generates `newsletter-draft.md`
3. After review, generates `newsletter-final.html`

### Publish
1. Copy `_working/YYYY-MM-DD/` to `_archive/YYYY-MM-DD/`
2. Rename `newsletter-final.html` → `index.html`
3. Git commit and push
4. Available at: https://noodlespoodles.github.io/zfx-newsletter/YYYY-MM-DD/

## Benefits of New Structure

1. **Clear Separation:** Working vs Archive vs Reference
2. **Consistent Naming:** All YYYY-MM-DD format
3. **Easy to Clean:** Delete old dates from `_working/`
4. **Organized Assets:** All branding in one place
5. **Clear Documentation:** All docs in `_docs/`
6. **No Confusion:** Legacy templates in `_templates/legacy/`
7. **Underscore Prefix:** Keeps system folders at top of listings
