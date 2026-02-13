# API Keys & Credentials

Quick reference for all configured services.

---

## 🔑 Active Keys

| Service | Type | Status | Notes |
|---------|------|--------|-------|
| Modal | `modalresearch_*` | ✅ Active | Free tier until April 2026 |
| Serper | Search API | ✅ Active | Google Search API |
| GitHub | PAT | ✅ Active | Full repo access |
| Telegram | Bot Token | ✅ Active | Bot configured |

---

## 🤖 Modal (GLM-5)

**Purpose:** Primary LLM API

- **Type:** Research API Key
- **Prefix:** `modalresearch_`
- **Free Tier:** Until April 2026
- **Rate Limit:** 1 concurrent request
- **Model:** GLM-5 (zai-org/GLM-5-FP8)

**Endpoint:**
```
https://api.us-west-2.modal.direct/v1
```

---

## 🔍 Serper

**Purpose:** Web Search API

- **Type:** API Key
- **Provider:** Google Search
- **Endpoint:** `https://google.serper.dev/search`

**Usage:**
```bash
curl -X POST "https://google.serper.dev/search" \
  -H "X-API-KEY: YOUR_KEY" \
  -H "Content-Type: application/json" \
  -d '{"q": "search query"}'
```

---

## 🐙 GitHub

**Purpose:** Repository access & Codespaces

- **Type:** Personal Access Token (PAT)
- **Prefix:** `ghp_`
- **Scopes:** `repo` (full control)

**Use Cases:**
- Push to repositories
- Create/manage Codespaces
- API access

---

## 📱 Telegram

**Purpose:** Bot communication

- **Type:** Bot Token
- **Format:** `123456789:ABC...`
- **Status:** Active

---

## ⚠️ Security Notes

> [!WARNING]
> Never commit API keys directly to public repositories!

**Best Practices:**
1. Use environment variables
2. Rotate keys regularly
3. Use minimal required scopes
4. Monitor usage in dashboards

---

## 🔄 Key Rotation Schedule

| Key | Last Rotated | Next Rotation |
|-----|--------------|---------------|
| Modal | Feb 2026 | As needed |
| GitHub PAT | Feb 2026 | Monthly |
| Serper | Feb 2026 | Quarterly |

---

*Last updated: February 13, 2026*
