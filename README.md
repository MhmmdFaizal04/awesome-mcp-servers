<div align="center">

# Awesome MCP Servers

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=15&pause=1000&color=6C63FF&center=true&vCenter=true&width=500&lines=Model+Context+Protocol+Servers;For+Claude+%C2%B7+Cursor+%C2%B7+Windsurf;Browser+%C2%B7+Database+%C2%B7+Dev+Tools;60%2B+curated+%26+categorized" alt="Typing SVG" />

<br/>

[![Stars](https://img.shields.io/github/stars/MhmmdFaizal04/awesome-mcp-servers?style=for-the-badge&color=6C63FF&labelColor=0a0a0f&logo=github)](https://github.com/MhmmdFaizal04/awesome-mcp-servers/stargazers)
[![Forks](https://img.shields.io/github/forks/MhmmdFaizal04/awesome-mcp-servers?style=for-the-badge&color=f472b6&labelColor=0a0a0f&logo=github)](https://github.com/MhmmdFaizal04/awesome-mcp-servers/network)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-4ade80?style=for-the-badge&labelColor=0a0a0f)](CONTRIBUTING.md)
[![License](https://img.shields.io/github/license/MhmmdFaizal04/awesome-mcp-servers?style=for-the-badge&color=22d3ee&labelColor=0a0a0f)](LICENSE)
[![Awesome](https://img.shields.io/badge/Awesome-List-6C63FF?style=for-the-badge&labelColor=0a0a0f)](https://github.com/sindresorhus/awesome)

<br/>

> A curated, categorized list of **MCP (Model Context Protocol) servers** for Claude, Cursor, Windsurf, and any MCP-compatible AI assistant.  
> Updated regularly. PRs welcome.

<br/>

[Browse Online](https://mhmmdfaizal04.github.io/awesome-mcp-servers/examples/) &nbsp;&middot;&nbsp;
[What is MCP?](docs/what-is-mcp.md) &nbsp;&middot;&nbsp;
[Setup Cursor](docs/setup-cursor.md) &nbsp;&middot;&nbsp;
[Setup Claude](docs/setup-claude.md)

</div>

---

## Contents

- [What is MCP?](#what-is-mcp)
- [Official Servers](#official-servers)
- [Browser & Web](#browser--web)
- [Database & Storage](#database--storage)
- [Dev Tools & Git](#dev-tools--git)
- [Productivity & Communication](#productivity--communication)
- [AI & Knowledge](#ai--knowledge)
- [API & External Services](#api--external-services)
- [File System & OS](#file-system--os)
- [Finance & Data](#finance--data)
- [Setup Guides](#setup-guides)
- [Contributing](#contributing)

---

## What is MCP?

**Model Context Protocol (MCP)** is an open standard by Anthropic that lets AI assistants (Claude, Cursor, Windsurf, etc.) connect to external tools, APIs, and data sources through a unified interface.

Think of MCP servers as **plugins for AI** — each server exposes a set of tools the AI can call to interact with the outside world.

```
Your AI Assistant
      │
      ▼
  MCP Client  ←──── reads ────→  mcp.json / .cursor/mcp.json
      │
      ├── MCP Server: filesystem  →  read/write local files
      ├── MCP Server: github      →  search repos, create PRs
      ├── MCP Server: postgres    →  query your database
      ├── MCP Server: slack       →  send messages
      └── MCP Server: browser     →  automate web browsing
```

**Supported by:** Claude Desktop · Cursor · Windsurf · Continue.dev · Zed · and more

---

## Official Servers

Maintained by Anthropic — battle-tested, production ready.

| Server | Description | Install |
|--------|-------------|---------|
| [filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | Read, write, and manage local files and directories | `npx @modelcontextprotocol/server-filesystem` |
| [fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) | Fetch web content — HTML, JSON, text from any URL | `npx @modelcontextprotocol/server-fetch` |
| [memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | Persistent knowledge graph memory across conversations | `npx @modelcontextprotocol/server-memory` |
| [git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) | Git operations — log, diff, status, blame | `uvx mcp-server-git` |
| [github](https://github.com/modelcontextprotocol/servers/tree/main/src/github) | GitHub API — repos, issues, PRs, code search | `npx @modelcontextprotocol/server-github` |
| [gitlab](https://github.com/modelcontextprotocol/servers/tree/main/src/gitlab) | GitLab API — repos, issues, merge requests | `npx @modelcontextprotocol/server-gitlab` |
| [postgres](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) | Query PostgreSQL databases | `npx @modelcontextprotocol/server-postgres` |
| [sqlite](https://github.com/modelcontextprotocol/servers/tree/main/src/sqlite) | SQLite database operations and queries | `uvx mcp-server-sqlite` |
| [slack](https://github.com/modelcontextprotocol/servers/tree/main/src/slack) | Slack — read channels, post messages | `npx @modelcontextprotocol/server-slack` |
| [puppeteer](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer) | Browser automation with Puppeteer | `npx @modelcontextprotocol/server-puppeteer` |
| [google-maps](https://github.com/modelcontextprotocol/servers/tree/main/src/google-maps) | Google Maps — places, directions, geocoding | `npx @modelcontextprotocol/server-google-maps` |
| [google-drive](https://github.com/modelcontextprotocol/servers/tree/main/src/google-drive) | Google Drive — search, read, list files | `npx @modelcontextprotocol/server-gdrive` |
| [brave-search](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search) | Brave Search API — web and local search | `npx @modelcontextprotocol/server-brave-search` |
| [aws-kb-retrieval](https://github.com/modelcontextprotocol/servers/tree/main/src/aws-kb-retrieval) | AWS Knowledge Base retrieval via Bedrock | `npx @modelcontextprotocol/server-aws-kb-retrieval` |
| [everart](https://github.com/modelcontextprotocol/servers/tree/main/src/everart) | EverArt AI image generation | `npx @modelcontextprotocol/server-everart` |

---

## Browser & Web

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [playwright](https://github.com/microsoft/playwright-mcp) | Full browser automation with Playwright — screenshots, clicks, forms | TypeScript | ⭐⭐⭐⭐⭐ |
| [browserbase](https://github.com/browserbase/mcp-server-browserbase) | Cloud browser automation — run headless browsers in the cloud | TypeScript | ⭐⭐⭐⭐ |
| [browser-use](https://github.com/browser-use/browser-use) | AI-native browser automation agent | Python | ⭐⭐⭐⭐⭐ |
| [crawl4ai](https://github.com/unclecode/crawl4ai) | AI-optimized web crawler — LLM-friendly output | Python | ⭐⭐⭐⭐⭐ |
| [firecrawl](https://github.com/mendableai/firecrawl-mcp-server) | Firecrawl API — scrape, crawl, extract structured data | TypeScript | ⭐⭐⭐⭐ |
| [linkup](https://github.com/LinkupPlatform/python-sdk) | Real-time web search with citations | Python | ⭐⭐⭐ |
| [tavily](https://github.com/tavily-ai/tavily-mcp) | Tavily search API — AI-optimized web search | TypeScript | ⭐⭐⭐⭐ |
| [exa](https://github.com/exa-labs/exa-mcp-server) | Exa search — neural + keyword web search | TypeScript | ⭐⭐⭐ |

---

## Database & Storage

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [supabase](https://github.com/supabase-community/supabase-mcp) | Full Supabase access — database, auth, storage, realtime | TypeScript | ⭐⭐⭐⭐⭐ |
| [mysql](https://github.com/benborla29/mcp-server-mysql) | MySQL database queries and management | Python | ⭐⭐⭐ |
| [mongodb](https://github.com/kiliczsh/mcp-mongo-server) | MongoDB CRUD operations and queries | TypeScript | ⭐⭐⭐ |
| [redis](https://github.com/redis/mcp-redis) | Redis operations — get, set, lists, pubsub | TypeScript | ⭐⭐⭐⭐ |
| [neon](https://github.com/neondatabase/mcp-server-neon) | Neon serverless Postgres — create projects, run queries | TypeScript | ⭐⭐⭐⭐ |
| [planetscale](https://github.com/planetscale/database-js) | PlanetScale serverless MySQL | TypeScript | ⭐⭐⭐ |
| [qdrant](https://github.com/qdrant/mcp-server-qdrant) | Qdrant vector database — semantic search, embeddings | Python | ⭐⭐⭐ |
| [pinecone](https://github.com/pinecone-io/pinecone-mcp) | Pinecone vector database operations | TypeScript | ⭐⭐⭐ |
| [turso](https://github.com/tursodatabase/turso-mcp) | Turso edge SQLite — query embedded databases | TypeScript | ⭐⭐⭐ |
| [prisma](https://github.com/prisma/prisma) | Prisma ORM schema and migration management | TypeScript | ⭐⭐⭐⭐ |

---

## Dev Tools & Git

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [github](https://github.com/modelcontextprotocol/servers/tree/main/src/github) | GitHub — repos, issues, PRs, code search, files | TypeScript | ⭐⭐⭐⭐⭐ |
| [linear](https://github.com/linear/linear-mcp) | Linear issue tracker — create, update, query issues | TypeScript | ⭐⭐⭐⭐ |
| [jira](https://github.com/sooperset/mcp-atlassian) | Jira + Confluence — issues, projects, docs | Python | ⭐⭐⭐ |
| [docker](https://github.com/ckreiling/mcp-server-docker) | Docker — manage containers, images, volumes | Python | ⭐⭐⭐⭐ |
| [kubernetes](https://github.com/Flux159/mcp-server-kubernetes) | Kubernetes — pods, deployments, services | TypeScript | ⭐⭐⭐ |
| [terraform](https://github.com/hashicorp/terraform-mcp-server) | Terraform — plan, apply, manage infrastructure | Go | ⭐⭐⭐ |
| [vercel](https://github.com/vercel/mcp-adapter) | Vercel — deployments, domains, env vars | TypeScript | ⭐⭐⭐⭐ |
| [raycast](https://github.com/raycast/extensions) | Raycast script commands and extensions | TypeScript | ⭐⭐⭐ |
| [npm](https://github.com/thinkloop/mcp-node-npm) | npm package info, search, dependency analysis | TypeScript | ⭐⭐⭐ |
| [vscode](https://github.com/microsoft/vscode-mcp) | VS Code — workspace, terminals, editor control | TypeScript | ⭐⭐⭐⭐ |
| [sentry](https://github.com/getsentry/sentry-mcp) | Sentry — error events, issues, performance data | TypeScript | ⭐⭐⭐ |
| [datadog](https://github.com/DataDog/datadog-mcp-server) | Datadog — metrics, logs, monitors, dashboards | Python | ⭐⭐⭐ |

---

## Productivity & Communication

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [notion](https://github.com/makenotion/notion-sdk-js) | Notion — pages, databases, blocks, search | TypeScript | ⭐⭐⭐⭐⭐ |
| [slack](https://github.com/modelcontextprotocol/servers/tree/main/src/slack) | Slack — channels, messages, threads, users | TypeScript | ⭐⭐⭐⭐ |
| [gmail](https://github.com/BurnySc2/monorepo) | Gmail — read, send, search, manage emails | Python | ⭐⭐⭐ |
| [google-calendar](https://github.com/nspaeth/google-calendar-mcp) | Google Calendar — events, scheduling, reminders | TypeScript | ⭐⭐⭐ |
| [obsidian](https://github.com/MarkusMelkersson/mcp-obsidian) | Obsidian vault — read, search, create notes | TypeScript | ⭐⭐⭐⭐ |
| [todoist](https://github.com/abhiz123/todoist-mcp-server) | Todoist — tasks, projects, labels, filters | Python | ⭐⭐⭐ |
| [asana](https://github.com/roychri/mcp-server-asana) | Asana — tasks, projects, teams, workspaces | TypeScript | ⭐⭐⭐ |
| [trello](https://github.com/miroapp/mcp-server-trello) | Trello — boards, cards, lists, members | TypeScript | ⭐⭐⭐ |
| [airtable](https://github.com/domdomegg/airtable-mcp-server) | Airtable — bases, tables, records, formulas | TypeScript | ⭐⭐⭐ |
| [discord](https://github.com/v-3/discordmcp) | Discord — read channels, send messages | TypeScript | ⭐⭐⭐ |
| [telegram](https://github.com/chigkim/Telegram-MCP) | Telegram — send messages, manage chats | Python | ⭐⭐ |

---

## AI & Knowledge

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | Persistent knowledge graph — remember across sessions | TypeScript | ⭐⭐⭐⭐⭐ |
| [sequential-thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) | Dynamic step-by-step problem solving and reasoning | TypeScript | ⭐⭐⭐⭐⭐ |
| [knowledge-graph](https://github.com/shaneholloman/mcp-knowledge-graph) | Persistent knowledge graph with entity relationships | TypeScript | ⭐⭐⭐⭐ |
| [openai](https://github.com/openai/openai-mcp) | OpenAI API — completions, embeddings, images, TTS | TypeScript | ⭐⭐⭐⭐ |
| [orkas-video-studio](https://github.com/Orkas-AI/Orkas-VideoStudio) | Agent-driven video composition, editing, transcription, and optional generation from editable timelines | TypeScript | ⭐⭐⭐ |
| [langchain](https://github.com/langchain-ai/langchain-mcp-adapters) | LangChain tools as MCP servers | Python | ⭐⭐⭐⭐ |
| [perplexity](https://github.com/ppl-ai/modelcontextprotocol) | Perplexity AI — real-time web search with AI answers | Python | ⭐⭐⭐⭐ |
| [context7](https://github.com/upstash/context7) | Up-to-date library documentation for any package | TypeScript | ⭐⭐⭐⭐⭐ |
| [pieces](https://github.com/pieces-app/pieces-mcp) | Pieces OS — personal code snippets and context | TypeScript | ⭐⭐⭐ |
| [arxiv](https://github.com/blazickjp/arxiv-mcp-server) | arXiv — search and read research papers | Python | ⭐⭐⭐ |
| [wikipedia](https://github.com/rudra-ravi/wikipedia-mcp) | Wikipedia — search and retrieve article content | Python | ⭐⭐⭐ |

---

## API & External Services

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [stripe](https://github.com/stripe/agent-toolkit) | Stripe — payments, customers, invoices, subscriptions | TypeScript | ⭐⭐⭐⭐⭐ |
| [twilio](https://github.com/twilio-labs/mcp) | Twilio — SMS, voice calls, WhatsApp messages | TypeScript | ⭐⭐⭐⭐ |
| [sendgrid](https://github.com/hannesrudolph/mcp-sendgrid-email-server) | SendGrid — transactional emails | TypeScript | ⭐⭐⭐ |
| [openweather](https://github.com/mcp-labs/mcp-weather-server) | OpenWeatherMap — current weather and forecasts | TypeScript | ⭐⭐⭐ |
| [spotify](https://github.com/varunneal/spotify-mcp) | Spotify — playback control, playlists, search | TypeScript | ⭐⭐⭐⭐ |
| [youtube](https://github.com/kimtaeyoon83/mcp-server-youtube-transcript) | YouTube — transcripts, video data, search | TypeScript | ⭐⭐⭐⭐ |
| [cloudflare](https://github.com/cloudflare/mcp-server-cloudflare) | Cloudflare — Workers, KV, D1, R2, analytics | TypeScript | ⭐⭐⭐⭐ |
| [resend](https://github.com/resend/mcp-send-email) | Resend — send emails via API | TypeScript | ⭐⭐⭐ |
| [shopify](https://github.com/shopify/dev-mcp) | Shopify — products, orders, customers, storefront | TypeScript | ⭐⭐⭐⭐ |
| [hubspot](https://github.com/hubspot/mcp-server) | HubSpot CRM — contacts, deals, companies | TypeScript | ⭐⭐⭐ |
| [maps-platform](https://github.com/googlemaps/js-maps-mcp) | Google Maps Platform — places, routes, geocoding | TypeScript | ⭐⭐⭐ |

---

## File System & OS

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | Secure local file system access with configurable roots | TypeScript | ⭐⭐⭐⭐⭐ |
| [everything](https://github.com/modelcontextprotocol/servers/tree/main/src/everything) | MCP testing server — comprehensive tool examples | TypeScript | ⭐⭐⭐⭐ |
| [desktop-commander](https://github.com/wonderwhy-er/DesktopCommanderMCP) | Terminal commands, file system, process management | TypeScript | ⭐⭐⭐⭐⭐ |
| [shell](https://github.com/zed-industries/zed) | Execute shell commands with configurable permissions | TypeScript | ⭐⭐⭐⭐ |
| [iterm2](https://github.com/ferrislucas/iterm-mcp) | iTerm2 terminal integration — run commands, read output | TypeScript | ⭐⭐⭐ |
| [windows-cli](https://github.com/SimonB97/win-cli-mcp-server) | Windows command-line tools — cmd, PowerShell | TypeScript | ⭐⭐⭐ |

---

## Finance & Data

| Server | Description | Language | Stars |
|--------|-------------|----------|-------|
| [alpaca](https://github.com/alpacahq/alpaca-mcp) | Alpaca — stock trading, market data, portfolio | TypeScript | ⭐⭐⭐ |
| [coinbase](https://github.com/coinbase/agentkit) | Coinbase — crypto prices, wallets, transactions | TypeScript | ⭐⭐⭐ |
| [polygon](https://github.com/polygon-io/client-python) | Polygon.io — real-time & historical stock data | Python | ⭐⭐⭐ |
| [yahoo-finance](https://github.com/narumiruna/yfinance-mcp) | Yahoo Finance — quotes, history, fundamentals | Python | ⭐⭐⭐ |

---

## Setup Guides

### Cursor

Add to `.cursor/mcp.json` in your project root or `~/.cursor/mcp.json` globally:

```jsonc
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allow"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token-here"
      }
    },
    "supabase": {
      "command": "npx",
      "args": ["-y", "@supabase/mcp-server-supabase@latest", "--access-token", "your-token"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

### Claude Desktop

Add to `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) or `%APPDATA%\Claude\claude_desktop_config.json` (Windows):

```jsonc
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/yourname/projects"]
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://localhost/mydb"]
    }
  }
}
```

Full setup guides in the [docs/](docs/) folder.

---

## Contributing

This list is community-maintained. To add a server:

1. Fork this repository
2. Add your server to the appropriate category in `README.md`
3. Follow the table format: `| [name](link) | description | language | ⭐ rating |`
4. Make sure the server is:
   - Publicly available and working
   - Has a clear README with install instructions
   - Actually implements the MCP protocol
5. Submit a Pull Request

**Rating guide:**
- ⭐⭐⭐⭐⭐ — Essential, widely used, actively maintained
- ⭐⭐⭐⭐ — Very useful, good quality
- ⭐⭐⭐ — Useful, works well
- ⭐⭐ — Early stage, use with caution

---

## Resources

- [MCP Official Docs](https://modelcontextprotocol.io) — Protocol specification and guides
- [MCP TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk) — Build your own server
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk) — Python server SDK
- [Anthropic MCP Announcement](https://www.anthropic.com/news/model-context-protocol) — Original blog post
- [Build Your First MCP Server](https://modelcontextprotocol.io/quickstart/server) — Official quickstart

---

## License

[MIT](LICENSE) — free to use, share, and contribute.

---

<div align="center">

If this list saves you time finding the right MCP server, a star helps a lot.

[![GitHub followers](https://img.shields.io/github/followers/MhmmdFaizal04?style=for-the-badge&color=6C63FF&labelColor=0a0a0f&logo=github)](https://github.com/MhmmdFaizal04)

Maintained by [MhmmdFaizal04](https://github.com/MhmmdFaizal04)

</div>
