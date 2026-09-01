# Setup MCP in Claude Desktop

Claude Desktop has native MCP support. Here's how to configure it.

---

## Config File Location

| OS | Path |
|----|------|
| macOS | `~/Library/Application Support/Claude/claude_desktop_config.json` |
| Windows | `%APPDATA%\Claude\claude_desktop_config.json` |
| Linux | `~/.config/Claude/claude_desktop_config.json` |

---

## Starter Config

```jsonc
{
  "mcpServers": {

    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/yourname/Desktop",
        "/Users/yourname/projects"
      ]
    },

    "fetch": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-fetch"]
    },

    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },

    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    }

  }
}
```

---

## Python-based Servers (uvx)

Some servers use Python with `uvx`:

```jsonc
{
  "mcpServers": {
    "git": {
      "command": "uvx",
      "args": ["mcp-server-git", "--repository", "/path/to/repo"]
    },
    "sqlite": {
      "command": "uvx",
      "args": ["mcp-server-sqlite", "--db-path", "/path/to/db.sqlite"]
    }
  }
}
```

Install `uvx`: `pip install uv` or `curl -LsSf https://astral.sh/uv/install.sh | sh`

---

## After Editing Config

1. **Fully quit** Claude Desktop (Cmd+Q / Alt+F4 — not just close window)
2. Reopen Claude Desktop
3. Click the 🔧 icon in the chat to see available tools
4. A green dot next to a server name = connected successfully

---

## Troubleshooting

**Server not showing up:**
- Check JSON syntax — use a JSON validator
- Make sure `npx` is in your PATH (`which npx` in terminal)
- Check Claude Desktop logs: `~/Library/Logs/Claude/` (macOS)

**Permission errors:**
- Make sure the paths in `args` actually exist
- Check file/folder permissions

**npx not found:**
- Install Node.js from [nodejs.org](https://nodejs.org)
- Or use full path: `"/usr/local/bin/npx"`
