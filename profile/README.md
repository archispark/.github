<div align="center">
  <img src="./logo.svg" width="96" height="96" alt="ArchiSpark" />
  <h1>ArchiSpark</h1>
  <p><strong>ArchiMate 3.1 modeling platform — web UI, REST API and MCP server.</strong><br/>
  Model enterprise architecture. Query it with AI.</p>

  <p>
    <a href="https://archispark.ai"><img src="https://img.shields.io/badge/archispark.ai-website-892FE8?style=flat-square" alt="Website"/></a>
    <a href="https://docs.archispark.ai"><img src="https://img.shields.io/badge/docs-getting%20started-1A87FF?style=flat-square" alt="Docs"/></a>
    <a href="https://img.shields.io/github/license/archispark/.github"><img src="https://img.shields.io/github/license/archispark/.github" alt="AGPL v3 License"/></a>
    <a href="https://github.com/archispark/archispark"><img src="https://img.shields.io/badge/ArchiMate-3.1-FF1D5D?style=flat-square" alt="ArchiMate 3.1"/></a>
  </p>
</div>

---

## What is ArchiSpark?

ArchiSpark is a full-stack ArchiMate 3.1 platform designed for enterprise architects who want to model, explore and manage their architecture — and let AI do the heavy lifting.

It ships three layers out of the box:

| Layer | Description |
|---|---|
| **Web UI** | Interactive canvas with ArchiMate notation, views library, relationship validator, analytical landscapes |
| **REST API** | Full CRUD over elements, relationships, views and workspaces. Swagger UI included |
| **MCP Server** | 25 tools exposed via Streamable HTTP — connect Claude or any LLM to create and query models in natural language |

## Features

- **AI-Native via MCP** — connect Claude or any MCP-compatible agent; describe your systems and let AI build the model
- **ArchiMate 3.1 compliant** — shapes, colors and relationship rules per the specification
- **AOEF interoperability** — full roundtrip import/export with Archi, BiZZdesign and Sparx EA
- **Relationship validator** — conformance checks in real-time, conflicts flagged with suggested alternatives
- **Interactive canvas** — drag, connect and resize nodes directly in the browser
- **Analytical landscapes** — App-by-Capability and Strategy-by-Capability views generated automatically
- **Multi-workspace RBAC** — fine-grained roles per ArchiMate layer; SQLite or PostgreSQL backend
- **SVG & PNG export** — every view, plus a ZIP bundle with the full model
- **Multilingual UI** — English, French, Spanish, German and Italian

## Quick Start

> Requires Node.js ≥ 22 and pnpm.

```bash
# 1 — Clone and install
git clone https://github.com/archispark/archispark
cd archispark && pnpm install

# 2 — Start all services
#   API   → http://localhost:3000  (Swagger at /docs)
#   MCP   → http://localhost:3001
#   Web   → http://localhost:8000
pnpm dev

# 3 — Open the web UI (default credentials: admin / admin)
open http://localhost:8000
```

## MCP Server

ArchiSpark exposes a Streamable HTTP MCP server on `:3001`. Add it to Claude Desktop or Claude Code:

```json
{
  "mcpServers": {
    "archispark": {
      "url": "http://localhost:3001/mcp/"
    }
  }
}
```

Then describe your architecture in plain language:

```
"Create a BusinessActor 'Customer', an ApplicationComponent 'CRM',
 and a Serving relationship between them."
```

The 25 available tools cover element and relationship CRUD, view rendering, AOEF import/export, property definitions and workspace management. → [Full MCP tool reference](https://docs.archispark.io/mcp-tools/)

## Repositories

| Repo | Description |
|---|---|
| [archispark](https://github.com/archispark/archispark) | Core platform — API, MCP server and web UI |
| [archispark-docs](https://github.com/archispark/archispark-docs) | Documentation site |
| [archispark-landing](https://github.com/archispark/archispark-landing) | Landing page |

---

<div align="center">
  <sub>ArchiMate® is a registered trademark of The Open Group. ArchiSpark is not affiliated with The Open Group.</sub>
</div>
