# Fda Food And Drug Enforcement Monitor MCP Server & Python API

[![Apify Store](https://img.shields.io/badge/Apify_Store-Run_on_Apify-blue?style=for-the-badge&logo=apify)](https://apify.com/deepaksheoran172/fda-food-and-drug-enforcement-monitor)
[![MCP Server](https://img.shields.io/badge/MCP-Model_Context_Protocol-purple?style=for-the-badge)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Hub](https://img.shields.io/badge/Live_Catalog-B2B_Scrapers_Hub-emerald?style=for-the-badge)](https://deepakshe.github.io/b2b-mcp-apify-scrapers-hub/)

> **FDA enforcement actions, warning letters, food recalls & drug safety intelligence monitor. MCP Server & Python SDK.**

---

## ⚡ The Problem vs. The Solution

Manual monitoring and constant polling of external APIs or portals consumes developer hours and results in delayed alerts. This serverless Actor provides sub-second structured data with built-in stateful delta monitoring and instant webhooks.

- **Zero-Proxy Fast Engine:** Asynchronous Python runtime designed for speed (<50MB RAM).
- **Multi-Interface Support:** Run via pure Python SDK, cURL, Node.js fetch, n8n / Make.com workflow, or Claude / Cursor MCP Agent.
- **Production Reliable:** Pinned to Apify serverless cloud with 99.9% uptime SLA.

---

## 🚀 Quickstart: 1-Line cURL

```bash
curl -X POST "https://api.apify.com/v2/acts/deepaksheoran172~fda-food-and-drug-enforcement-monitor/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"enableDeltaMode": false}'
```

---

## 🚀 Quickstart: Pure Python (Zero-Dependency)

```python
import json
import os
import urllib.request

APIFY_TOKEN = os.getenv("APIFY_TOKEN", "YOUR_APIFY_TOKEN")
ACTOR_URL = "https://api.apify.com/v2/acts/deepaksheoran172~fda-food-and-drug-enforcement-monitor/run-sync-get-dataset-items?token=" + APIFY_TOKEN

payload = {"enableDeltaMode": False}

req = urllib.request.Request(
    ACTOR_URL,
    data=json.dumps(payload).encode("utf-8"),
    headers={"Content-Type": "application/json"},
    method="POST"
)

with urllib.request.urlopen(req, timeout=120) as resp:
    results = json.loads(resp.read().decode("utf-8"))
    print(f"Retrieved {len(results)} items:")
    print(json.dumps(results[:2], indent=2))
```

---

## 🤖 Claude Desktop & Cursor MCP Server Setup

Add this actor to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "fda-food-and-drug-enforcement-monitor": {
      "command": "npx",
      "args": ["-y", "@apify/actors-mcp-server"],
      "env": {
        "APIFY_TOKEN": "YOUR_APIFY_TOKEN",
        "ACTOR_NAME": "deepaksheoran172/fda-food-and-drug-enforcement-monitor"
      }
    }
  }
}
```

---

## 🔄 n8n & Make.com Automation

A production n8n workflow template is bundled in this repository as [`workflow.json`](./workflow.json).

---

## 🏷️ Pricing & 60% Launch Discount

- **Apify Store:** Available under pay-per-result pricing with a **60% Launch Discount**.
- **Run Online:** Test it instantly on the [Apify Store Console](https://apify.com/deepaksheoran172/fda-food-and-drug-enforcement-monitor).
- **Fleet Hub:** Explore all enterprise tools and MCP servers at [b2b-mcp-apify-scrapers-hub](https://deepakshe.github.io/b2b-mcp-apify-scrapers-hub/).

---

## 📄 License

MIT License. Free for personal, commercial, and enterprise integration.
