# Browser Access via GitHub Codespaces

This repo is configured for browser access via GitHub Codespaces.

## Quick Start

```bash
# Start codespace
gh codespace create -R vanarpsedoc/san -b main -m standardLinux32gb --display-name "openclaw-browser"

# SSH into codespace
gh codespace ssh

# Run browser (headless)
cd /workspaces/san
node -e "
const { chromium } = require('playwright');
(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  console.log(await page.title());
  await browser.close();
})();
"

# Stop codespace (to save free hours!)
gh codespace stop
```

## Codespace Details

- **Machine:** standardLinux32gb (4-core, 32GB RAM)
- **Browser:** Playwright Chromium (headless)
- **Free Tier:** 120 core-hours/month

## Useful Commands

```bash
# List codespaces
gh codespace list

# Check status
gh codespace status

# View logs
gh codespace logs

# Delete codespace
gh codespace delete
```

## Cost Management

⚠️ **Important:** Always stop your codespace when not in use!

```bash
# Stop to save hours
gh codespace stop -c <codespace-name>
```

Free tier: 120 core-hours/month
- standardLinux32gb = 4 cores/hour
- ~30 hours/month on this machine type

---

*Setup: February 13, 2026*
