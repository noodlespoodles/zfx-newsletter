# ZFX Daily Market Snapshot Newsletter

Professional trading newsletter for ZFX clients featuring market analysis, charts, and key timing information.

## Live Preview
Once deployed, your newsletter will be available at:
`https://[your-github-username].github.io/[repository-name]/`

## Quick Setup - GitHub Pages

### Step 1: Create GitHub Repository
1. Go to [GitHub.com](https://github.com) and sign in
2. Click the **+** icon (top right) → **New repository**
3. Name it something like `zfx-newsletter` (avoid spaces)
4. Set to **Public** (required for free GitHub Pages)
5. **DON'T** initialize with README (we already have files)
6. Click **Create repository**

### Step 2: Push to GitHub
Copy and run these commands in the `newsletter_upload` folder:

```bash
# Add your GitHub repository as remote (replace with your URL)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Scroll down to **Pages** (left sidebar)
4. Under **Source**, select:
   - **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
5. Click **Save**

### Step 4: Access Your Newsletter
- Wait 2-3 minutes for deployment
- Your newsletter will be live at:
  ```
  https://[your-username].github.io/[repository-name]/
  ```
- Example: `https://johnsmith.github.io/zfx-newsletter/`

## Files Included
- `index.html` - Main newsletter file
- `ZFX_logo.png` - Company logo
- `Charts/` - All market charts
  - ES.png (S&P 500 futures)
  - eurusd.png (EUR/USD)
  - gbpusd.png (GBP/USD)
  - gold.png (Gold)
  - oil.png (Oil)
  - 10yr.png (10-year yields)

## Sharing Options
Once live, you can:
1. **Direct link**: Share the GitHub Pages URL
2. **Email**: Send the link with preview text
3. **Embed**: Use an iframe on other websites

## Updating Content
1. Edit `index.html` locally
2. Commit and push changes:
   ```bash
   git add .
   git commit -m "Update newsletter content"
   git push
   ```
3. GitHub Pages auto-updates in ~1 minute

## Custom Domain (Optional)
To use your own domain (e.g., newsletter.zfx.com):
1. Add a `CNAME` file with your domain
2. Configure DNS settings with your provider
3. Enable in GitHub Pages settings

## Support
For GitHub Pages documentation: https://pages.github.com/