---
feature: "MCP Support (Model Context Protocol)"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription"
  - "Understanding of client-server architecture"
  - "Basic knowledge of JSON-RPC (optional)"
audience: "Developers, DevOps engineers, and teams wanting to extend AI capabilities with custom tools"
---

# 🚀 Feature Training: `MCP Support (Model Context Protocol)` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `MCP Support (Model Context Protocol)`
- **Release Version:** `1.102`
- **Feature Type:** `AI Integration Framework`
- **Summary:**  
  Full general availability of Model Context Protocol support in VS Code, enabling AI models to interact with external tools and data sources through standardized MCP servers.

## 2. Why It Matters

- **Extensible AI Capabilities:** Connect Copilot to databases, APIs, and custom tools without building custom integrations
- **Standardized Protocol:** Uses open standard (like Language Server Protocol for AI tools) for consistent integration
- **Team Productivity:** Enable AI to perform complex, domain-specific operations directly from VS Code
- **Reusability:** MCP servers work across different AI clients, not just VS Code
- **Target Users:** Developers building custom tools, DevOps teams, and organizations with specialized workflows
- **Status:** Generally available in VS Code 1.102+

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription with Chat enabled
- Understanding of client-server architecture concepts
- JSON-RPC knowledge (helpful but not required)

### 3.2 How to Enable/Access

- **MCP View:** Available in Extensions view under "MCP SERVERS" section
- **Installation Methods:**
  - From MCP gallery via VS Code website
  - Direct installation from `mcp.json` configuration
  - Command line using `--add-mcp` flag
  - Auto-discovery from other AI tools (like Claude Desktop)
- **Configuration:** Workspace or global configuration files

### 3.3 Step-by-Step Usage

1. **Browse Available MCP Servers:**
   - Visit VS Code MCP gallery or Extensions view
   - Explore community-created MCP servers

2. **Install an MCP Server:**
   - Click "Install" on any MCP server from the gallery
   - Review server details and manifest information
   - Confirm installation

3. **Verify Installation:**
   - Check Extensions view under "MCP SERVERS - INSTALLED"
   - Verify server appears in Chat view's tools Quick Pick

4. **Use MCP Tools in Chat:**
   - Open Copilot Chat
   - Ask questions that require external data or tools
   - AI automatically invokes MCP server capabilities when relevant

5. **Manage MCP Servers:**
   - Start/Stop/Restart servers from context menu
   - Configure model access permissions
   - View server output logs for troubleshooting

### 3.4 Example(s)

- **Simple example:**  
  Install a file management MCP server that allows Copilot to read, write, and organize files across your system beyond the current workspace.

- **Advanced/tip:**  
  Build a custom MCP server that connects to your company's internal APIs, enabling Copilot to fetch project status, create tickets, or query documentation directly from chat.

**Sample MCP server configuration in `mcp.json`:**

```json
{
  "servers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"]
    },
    "custom-db": {
      "command": "node",
      "args": ["./my-mcp-server.js"],
      "env": {
        "DB_CONNECTION": "postgresql://localhost:5432/mydb"
      }
    }
  }
}
```

**Example chat interaction with MCP:**

```
User: "Check the status of our CI/CD pipeline"
Copilot: [Invokes MCP server] "Your pipeline has 3 jobs running: 
- Build: ✅ Completed (2m 15s)
- Tests: 🔄 Running (1m 30s remaining)  
- Deploy: ⏳ Waiting"
```

## 4. Troubleshooting & FAQ

- **Q: What's the difference between MCP servers and VS Code extensions?**
  - A: MCP servers are protocol-based tools that work across AI clients. VS Code extensions are editor-specific and have different capabilities.

- **Q: Can I use MCP servers without an internet connection?**
  - A: Yes, MCP supports local tools via STDIO transport. Remote tools require internet for HTTP+SSE transport.

- **Q: How do I create my own MCP server?**
  - A: Follow the MCP specification using JSON-RPC 2.0 messaging. VS Code provides developer documentation and examples.

- **Q: Are MCP servers secure?**
  - A: MCP servers run with the permissions of the VS Code process. Review server code and use trusted sources only.

## 5. Additional Resources

- Official VS Code MCP documentation: [MCP in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
- MCP developer guide: [Building MCP Servers](https://code.visualstudio.com/api/extension-guides/ai/mcp)
- Model Context Protocol specification: [MCP Standard](https://modelcontextprotocol.io/)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: Open Source Copilot Chat, Custom Instructions

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for MCP Support |
