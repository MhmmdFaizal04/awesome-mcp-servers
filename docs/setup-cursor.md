# Setup MCP in Cursor

Cursor supports MCP servers natively. Here's how to configure them.

---

## Config File Location

| Scope | File |
|-------|------|
| Project (recommended) | `.cursor/mcp.json` in your project root |
| Global (all projects) | `~/.cursor/mcp.json` |

Project-level config overrides global for that project.

---

## Config Format

```jsonc
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "@scope/package-name", "...args"],
      "env": {
        "API_KEY": "your-key-here"
      }
    }
  }
}
```

---

## Recommended Starter Config

```jsonc
// .cursor/mcp.json
{
  "mcpServers": {

    // File system access — read/write project files
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/yourname/projects"   // ← change to your projects folder
      ]
    },

    // GitHub — repos, issues, PRs, code search
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_..."  // ← your GitHub PAT
      }
    },

    // Persistent memory across conversations
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },

    // Step-by-step reasoning for complex problems
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },

    // Fetch web content and documentation
    "fetch": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-fetch"]
    }

  }
}
```

---

## Add More Servers

### Supabase
```jsonc
"supabase": {
  "command": "npx",
  "args": [
    "-y",
    "@supabase/mcp-server-supabase@latest",
    "--access-token", "sbp_..."
  ]
}
```

### PostgreSQL
```jsonc
"postgres": {
  "command": "npx",
  "args": [
    "-y",
    "@modelcontextprotocol/server-postgres",
    "postgresql://localhost:5432/mydb"
  ]
}
```

### Notion
```jsonc
"notion": {
  "command": "npx",
  "args": ["-y", "@notionhq/mcp"],
  "env": {
    "NOTION_API_KEY": "secret_..."
  }
}
```

### Stripe
```jsonc
"stripe": {
  "command": "npx",
  "args": ["-y", "@stripe/agent-toolkit", "--tools=all"],
  "env": {
    "STRIPE_SECRET_KEY": "sk_test_..."
  }
}
```

### Slack
```jsonc
"slack": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-slack"],
  "env": {
    "SLACK_BOT_TOKEN": "xoxb-...",
    "SLACK_TEAM_ID": "T..."
  }
}
```

---

## Verify It Works

1. Open Cursor
2. Open Settings → Features → MCP
3. You should see your servers listed with a green status indicator
4. In any chat, ask: *"What MCP tools do you have available?"*

---

## Security Notes

- Never commit `.cursor/mcp.json` with real API keys to a public repo
- Add `.cursor/mcp.json` to `.gitignore` if it contains secrets
- Use environment variables or a secrets manager for production
- Only grant filesystem access to directories you trust

```bash
# .gitignore
.cursor/mcp.json
```

Or use a template file without secrets:

```bash
# .cursor/mcp.json.example  ← commit this
# .cursor/mcp.json          ← gitignore this
```
