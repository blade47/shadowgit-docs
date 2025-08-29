# ShadowGit Documentation

Official documentation for ShadowGit MCP Server - give your AI assistants perfect memory of your code changes.

## What is ShadowGit?

ShadowGit saves every keystroke and feeds your complete code history to AI assistants like Claude and Cursor via MCP (Model Context Protocol). Your AI stops guessing and knows exactly what worked before.

## Installation & Setup

### Prerequisites

- **Node.js 18+** installed ([Download Node.js](https://nodejs.org))
- **ShadowGit desktop app** running with at least one tracked repository ([Download ShadowGit](https://shadowgit.com))

### Install MCP Server

**Option 1: npm (Recommended)**
```bash
npm install -g shadowgit-mcp-server
```

**Option 2: From GitHub**
```bash
git clone https://github.com/blade47/shadowgit-mcp.git
cd shadowgit-mcp
npm install && npm run build
npm install -g .
```

### Configure Your AI Tool

Choose your AI assistant and follow the setup:

#### Claude Code
```bash
# One command setup
claude mcp add shadowgit -- shadowgit-mcp-server

# Restart Claude Code
```

#### Claude Desktop
1. Edit your config file:
   - **Mac/Linux**: `~/.config/Claude/claude_desktop_config.json`
   - **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

2. Add ShadowGit server:
```json
{
  "mcpServers": {
    "shadowgit": {
      "command": "shadowgit-mcp-server"
    }
  }
}
```

#### Cursor
1. Open Cursor Settings (`Cmd/Ctrl + ,`)
2. Search for "MCP"
3. Add configuration:
```json
{
  "mcpServers": {
    "shadowgit": {
      "command": "shadowgit-mcp-server"
    }
  }
}
```

### Verify Installation

Ask your AI: **"What ShadowGit repositories do I have?"**

Your AI should list your tracked repositories. If not, see troubleshooting below.

## Key Benefits

- **66% fewer tokens** - AI knows your history, no re-reading codebases
- **Fix bugs in one shot** - AI sees what broke and when  
- **Perfect memory** - Never explain context again
- **100% local** - Your code never leaves your machine

## What Your AI Can Do

Once configured, your AI can:

```bash
# See recent commits
"Show me what changed in the last hour"

# Debug issues
"When did this function last work correctly?"

# Find patterns
"What files usually change together with auth.ts?"

# Time travel
"What was I working on yesterday at 3 PM?"
```

## Documentation Structure

This documentation covers:

- **Getting Started**: Introduction and installation guide
- **AI Tool Integration**: Detailed setup guides for Claude Code, Cursor, and Windsurf
- **MCP Server**: Complete configuration and usage examples

## Links

- **ShadowGit Website**: [https://shadowgit.com](https://shadowgit.com)
- **GitHub Repository**: [https://github.com/blade47/shadowgit-mcp](https://github.com/blade47/shadowgit-mcp)
- **MCP Server Package**: [shadowgit-mcp-server on npm](https://www.npmjs.com/package/shadowgit-mcp-server)
- **Support**: [support@shadowgit.com](mailto:support@shadowgit.com)
- **Live Documentation**: [docs.shadowgit.com](https://docs.shadowgit.com)

## Troubleshooting

### "No repositories found"
1. Open ShadowGit desktop app
2. Add at least one repository (click + button)
3. Wait for first snapshot (usually 3 minutes)
4. Ask your AI again

### "Command not found: shadowgit-mcp-server"
```bash
# Check if installed
npm list -g shadowgit-mcp-server

# If not found, reinstall from npm
npm install -g shadowgit-mcp-server

# Or install from GitHub
git clone https://github.com/blade47/shadowgit-mcp.git
cd shadowgit-mcp && npm install && npm run build && npm install -g .

# Use full path in config if needed
which shadowgit-mcp-server
```

### AI doesn't see ShadowGit
1. **Restart your AI application** completely after adding config
2. **Check Node.js is installed**: `node --version`
3. **Verify ShadowGit app is running** with tracked repositories

### Permission errors (macOS)
Grant your AI tool full disk access:
1. System Preferences → Security & Privacy
2. Privacy → Full Disk Access  
3. Add your AI application (Claude, Cursor, etc.)

---

Transform your AI development workflow with ShadowGit. Perfect memory, instant debugging, massive token savings. 🚀