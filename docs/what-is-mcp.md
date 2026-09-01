# What is MCP?

**Model Context Protocol (MCP)** is an open standard created by Anthropic in November 2024.

It defines a universal way for AI assistants to connect to external tools, APIs, databases, and data sources — solving the "context problem" that every AI developer faces.

---

## The Problem MCP Solves

Before MCP, every AI tool had to build its own integration for every data source:

```
ChatGPT plugins  →  custom plugin format
Copilot          →  custom extension API
Claude Tools     →  custom tool format
Cursor           →  custom context format
```

This meant:
- Developers had to rebuild the same integrations for each platform
- AI assistants couldn't share tools or context
- Every integration was a one-off, poorly maintained

---

## The MCP Solution

MCP gives every AI assistant a **single, standardized way** to talk to external services:

```
Any AI Assistant (Claude, Cursor, Windsurf...)
         │
         ▼
    MCP Client
         │
    ┌────┴──────────────────────┐
    │                           │
    ▼                           ▼
MCP Server A              MCP Server B
(filesystem)              (github)
    │                           │
    ▼                           ▼
Local files               GitHub API
```

Build an MCP server once → works everywhere that supports MCP.

---

## Key Concepts

### MCP Server
A process that exposes **tools**, **resources**, and **prompts** via the MCP protocol. Can be:
- A local process (`npx @modelcontextprotocol/server-filesystem`)
- A remote HTTP server
- A Docker container

### Tools
Functions the AI can call:
```json
{
  "name": "read_file",
  "description": "Read contents of a file",
  "inputSchema": {
    "type": "object",
    "properties": {
      "path": { "type": "string" }
    }
  }
}
```

### Resources
Data sources the AI can read — files, database records, API responses.

### Prompts
Reusable prompt templates with arguments.

---

## Supported Clients

| Client | MCP Support |
|--------|-------------|
| Claude Desktop | Full support (official) |
| Cursor | Full support (`.cursor/mcp.json`) |
| Windsurf | Full support |
| Continue.dev | Full support |
| Zed | Full support |
| VS Code (Copilot) | Partial |

---

## Build Your Own MCP Server

### TypeScript

```bash
npm install @modelcontextprotocol/sdk
```

```typescript
import { Server } from '@modelcontextprotocol/sdk/server/index.js'
import { StdioServerTransport } from '@modelcontextprotocol/sdk/server/stdio.js'

const server = new Server(
  { name: 'my-server', version: '1.0.0' },
  { capabilities: { tools: {} } }
)

server.setRequestHandler('tools/list', async () => ({
  tools: [{
    name: 'hello',
    description: 'Say hello',
    inputSchema: {
      type: 'object',
      properties: { name: { type: 'string' } }
    }
  }]
}))

server.setRequestHandler('tools/call', async (request) => {
  const { name } = request.params.arguments as { name: string }
  return { content: [{ type: 'text', text: `Hello, ${name}!` }] }
})

const transport = new StdioServerTransport()
await server.connect(transport)
```

### Python

```bash
pip install mcp
```

```python
from mcp.server import Server
from mcp.server.stdio import stdio_server

app = Server("my-server")

@app.list_tools()
async def list_tools():
    return [Tool(name="hello", description="Say hello", inputSchema={...})]

@app.call_tool()
async def call_tool(name, arguments):
    return [TextContent(type="text", text=f"Hello, {arguments['name']}!")]

async def main():
    async with stdio_server() as (read, write):
        await app.run(read, write, app.create_initialization_options())
```

---

## Resources

- [Official MCP Documentation](https://modelcontextprotocol.io)
- [MCP TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [Anthropic MCP Announcement](https://www.anthropic.com/news/model-context-protocol)
