---
feature: "MCP Enhancements"
release: "1.101"   # e.g., 1.102
prerequisites:                # List prerequisite features or knowledge (can be empty)
  - "Basic understanding of VS Code Chat and Agent mode"
  - "Familiarity with JSON configuration files"
audience: "Developers, Power Users, AI-assisted coding practitioners"  # e.g., "Python developers", "Data Scientists", "Power Users", "All Users"
---

# 🚀 Feature Training: `MCP Enhancements` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `MCP Enhancements`
- **Release Version:** `1.101`
- **Feature Type:** `AI/Chat Enhancement, Protocol Extension`
- **Summary:**  
  Comprehensive Model Context Protocol (MCP) enhancements that expand AI coding workflows with support for prompts, resources, sampling, authentication, development mode, and extension APIs. These features enable AI models to securely interact with external tools, data sources, and services through a standardized protocol.

## 2. Why It Matters

- **Core Problem Solved:** Enables AI assistants to access and interact with external tools, databases, APIs, and services beyond natural language processing, creating a unified and extensible AI-powered development environment.
- **Target Users:** Developers using AI-assisted coding workflows, power users customizing VS Code with external integrations, teams building custom tooling for AI assistants.
- **Context:** MCP features are progressively enabled and require manual configuration. Some features like sampling are experimental.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- GitHub Copilot or compatible AI assistant extension
- MCP servers (can be installed via extensions or configured manually)

### 3.2 How to Enable/Access

- **MCP Server Management:** Command Palette → `MCP: Add Server...`
- **MCP Resources:** Command Palette → `MCP: Browse Resources`
- **Server List:** Command Palette → `MCP: List Servers`
- **Configuration:** `.vscode/mcp.json` file for server definitions
- **Tool Sets:** Command Palette → `Configure Tool Sets`

### 3.3 Step-by-Step Usage

#### 3.3.1 MCP Prompts

1. **Configure MCP Server:** Add an MCP server that supports prompts (e.g., Gistpad MCP server)
2. **Access Prompts:** In chat, use slash commands in format `/mcp.servername.promptname`
3. **Use Completions:** Type `/mcp.` to see available prompts with auto-completion
4. **Execute Prompt:** Enter variables or plain text as prompted by the MCP server

#### 3.3.2 MCP Resources

1. **Attach Resources:** In Chat view → **Add Context...** → **MCP Resources...**
2. **Save Resources:** When MCP tools return resources, use **Save** button or drag to Explorer
3. **Browse Resources:** Use **MCP: Browse Resources** command to explore across servers

#### 3.3.3 MCP Authentication

1. **Add Authenticated Server:** Use **MCP: Add Server...** for servers requiring auth
2. **Manage Trust:** Account menu → **Manage Trusted MCP Servers**
3. **Configure Accounts:** Use gear button to select which account to use per server
4. **Cleanup:** Use **Authentication: Remove Dynamic Authentication Providers** when needed

#### 3.3.4 MCP Development Mode

1. **Configure Dev Mode:** Add `dev` object to server config in `.vscode/mcp.json`:

```json
{
  "servers": {
    "my-server": {
      "command": "node",
      "args": ["build/index.js"],
      "dev": {
        "watch": "build/**/*.js",
        "debug": { "type": "node" }
      }
    }
  }
}
```

1. **Enable Debugging:** Set breakpoints in your MCP server code
1. **Auto-restart:** Files matching the watch pattern will restart the server automatically

### 3.4 Example(s)

#### Simple Example: Using MCP Prompts

```
User: /mcp.gistpad.generate-changelog
Variables: 
- version: 1.2.0
- features: ["Added dark mode", "Fixed login bug", "Improved performance"]

AI generates a formatted changelog using the MCP prompt template
```

#### Advanced Example: Full MCP Workflow

```json
// .vscode/mcp.json
{
  "servers": {
    "github-integration": {
      "command": "npx",
      "args": ["github-mcp-server"],
      "env": {
        "GITHUB_TOKEN": "${env:GITHUB_TOKEN}"
      }
    }
  }
}
```

1. Configure GitHub MCP server with authentication
2. Use `/mcp.github.create-issue` to create GitHub issues from chat
3. Attach repository resources as context for code analysis
4. Use sampling to let MCP server query AI for automated responses

## 4. Troubleshooting & FAQ

### Common Issues

- **MCP Server Not Found:** Ensure server is properly configured in `.vscode/mcp.json` and dependencies are installed
- **Authentication Failures:** Check tokens/credentials and use **Manage Trusted MCP Servers** to re-authorize
- **Prompts Not Appearing:** Verify server supports prompts and use `/mcp.` autocomplete to discover available prompts
- **Sampling Permissions:** First sampling request requires user confirmation; check **MCP: List Servers** for configuration

### How to Disable

- Remove server entries from `.vscode/mcp.json`
- Use **Authentication: Remove Dynamic Authentication Providers** for cleanup
- Disable specific tools in chat tool configuration

### Edge Cases

- **Experimental Features:** Sampling support is preliminary and may change
- **Server Compatibility:** Not all MCP servers support all features (prompts, resources, sampling)
- **Performance:** Development mode with file watching may impact performance with large codebases

## 5. Additional Resources

- **Official VS Code Documentation:** [MCP Servers Guide](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
- **MCP Specification:** [Model Context Protocol](https://modelcontextprotocol.io/)
- **Extension Development:** [MCP Extension Guide](https://code.visualstudio.com/api/extension-guides/mcp)
- **Sample Servers:** [GitHub MCP Server](https://github.com/github/github-mcp-server), [Gistpad MCP](https://github.com/lostintangent/gistpad-mcp)
- **Related Features:** Chat Tool Sets, Custom Chat Modes, Agent Mode improvements

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for MCP Enhancements |
