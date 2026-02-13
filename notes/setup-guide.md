# Setup Guide

Complete guide on how this workspace was configured.

---

## 📅 Timeline

- **Date:** February 13, 2026
- **Platform:** Termux on Android
- **AI Model:** GLM-5 via Modal Research Program

---

## 🤖 Model Configuration

### Modal GLM-5 Setup

We switched from GitHub Copilot to Modal's free GLM-5 endpoint.

**Config added to `openclaw.json`:**

```json
{
  "auth": {
    "profiles": {
      "modal:llm": {
        "provider": "modal",
        "mode": "api_key"
      }
    }
  },
  "models": {
    "mode": "merge",
    "providers": {
      "modal": {
        "baseUrl": "https://api.us-west-2.modal.direct/v1",
        "api": "openai-completions",
        "models": [
          {
            "id": "zai-org/GLM-5-FP8",
            "name": "GLM-5",
            "reasoning": true,
            "input": ["text"],
            "cost": {
              "input": 0,
              "output": 0
            },
            "contextWindow": 192000,
            "maxTokens": 8192
          }
        ]
      }
    }
  },
  "agents": {
    "defaults": {
      "model": {
        "primary": "modal/zai-org/GLM-5-FP8"
      }
    }
  }
}
```

### GLM-5 Specs

| Property | Value |
|----------|-------|
| Parameters | 744B (40B active MoE) |
| Context Window | 192K tokens |
| Max Output | 8K tokens |
| License | MIT (Open Source) |
| Free Tier | Until end of April 2026 |
| Rate Limit | 1 concurrent request |

---

## 🔍 Search Configuration

Since Brave Search API wasn't available, we set up Serper (Google Search API).

**Custom search script:**

```bash
#!/bin/bash
QUERY="$1"
curl -s -X POST "https://google.serper.dev/search" \
  -H "X-API-KEY: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d "{\"q\": \"$QUERY\"}"
```

---

## 🌐 Browser Access via Codespaces

Since Termux doesn't support browsers, we set up GitHub Codespaces.

### Quick Commands

```bash
# Start codespace
gh codespace create -R vanarpsedoc/san -b main -m standardLinux32gb

# SSH into codespace
gh codespace ssh

# Stop when done
gh codespace stop
```

---

## 📱 Platform Limitations

### Termux on Android

- ❌ No native browser (Chromium not supported)
- ❌ No Playwright/Puppeteer
- ✅ Full Linux command line
- ✅ Node.js, Python, Git
- ✅ SSH client

---

## 📚 Resources

- [Modal GLM-5 Endpoint](https://modal.com/glm-5-endpoint)
- [GLM-5 GitHub](https://github.com/zai-org/GLM-5)
- [OpenClaw Docs](https://docs.openclaw.ai)
- [Serper API](https://serper.dev)

---

*Last updated: February 13, 2026*
