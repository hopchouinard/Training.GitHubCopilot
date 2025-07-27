---
feature: "MCP Server Discovery and Installation"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription with Chat"
  - "Basic understanding of MCP (Model Context Protocol)"
audience: "Developers wanting to extend AI capabilities with external tools and services"
---

# 🚀 Feature Training: `MCP Server Discovery and Installation` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `MCP Server Discovery and Installation`
- **Release Version:** `1.102`
- **Feature Type:** `AI Extension Framework`
- **Summary:**  
  Streamlined system for finding, installing, and managing MCP servers through a curated gallery and integrated management interface within VS Code.

## 2. Why It Matters

- **Easy Discovery:** Find relevant MCP servers through curated gallery and community recommendations
- **One-Click Installation:** Install servers directly from gallery with integrated VS Code experience
- **Centralized Management:** Manage all installed MCP servers from unified interface
- **Community Access:** Leverage community-contributed tools and integrations
- **Target Users:** Developers, DevOps teams, and users wanting to extend AI capabilities
- **Status:** Generally available in VS Code 1.102+ as part of full MCP support

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription with Chat enabled
- Understanding of MCP concepts and client-server architecture
- Network access for downloading and installing servers

### 3.2 How to Enable/Access

- **Extensions View:** "MCP SERVERS" section with welcome content
- **Gallery Access:** Links to curated MCP servers list at [code.visualstudio.com/mcp](https://code.visualstudio.com/mcp)
- **Auto-Discovery:** Enable `chat.mcp.discovery.enabled` setting
- **Management View:** "MCP SERVERS - INSTALLED" section in Extensions view

### 3.3 Step-by-Step Usage

1. **Browse Available Servers:**
   - Visit Extensions view → "MCP SERVERS" section
   - Click links to curated server gallery
   - Browse community-contributed servers by category

2. **Install an MCP Server:**
   - Select "Install" on desired server from gallery
   - VS Code opens MCP server editor automatically
   - Review server README, manifest, and capabilities
   - Confirm installation to add to VS Code

3. **Verify Installation:**
   - Check "MCP SERVERS - INSTALLED" view in Extensions
   - Verify server appears in Chat view's tools Quick Pick
   - Test server functionality in Copilot Chat

4. **Manage Installed Servers:**
   - Use context menu for server management actions
   - Start/Stop/Restart servers as needed
   - Configure model access and permissions
   - View logs for troubleshooting

### 3.4 Example(s)

- **Simple example:**  
  Install a file management MCP server from the gallery that allows Copilot to perform advanced file operations beyond the current workspace.

- **Advanced/tip:**  
  Set up auto-discovery to automatically detect MCP servers configured in other applications like Claude Desktop, reducing manual configuration across tools.

**Installation workflow:**

```
1. Browse Gallery → 🔍 Find relevant MCP server
2. Click Install → 📥 VS Code opens server details
3. Review Details → 📋 Check README and manifest
4. Confirm Install → ✅ Server added to VS Code
5. Verify Setup → 🔧 Test in Chat tools Quick Pick
```

**MCP server management actions:**

- **Start Server** / **Stop Server** / **Restart Server** - Control server state
- **Disconnect Account** - Remove account access for authenticated servers
- **Show Output** - View server logs for debugging
- **Show Configuration** - Display runtime settings
- **Configure Model Access** - Set which AI models server can use
- **Browse Resources** - Explore server-provided resources
- **Uninstall** - Remove server from VS Code

## 4. Troubleshooting & FAQ

- **Q: Where can I find available MCP servers?**
  - A: Visit the curated gallery at code.visualstudio.com/mcp or check the Extensions view "MCP SERVERS" section.

- **Q: How do I know if an MCP server is trustworthy?**
  - A: Review the server's README, check the publisher, and examine the manifest. Only install from trusted sources.

- **Q: Can I use MCP servers across different VS Code workspaces?**
  - A: Yes, servers can be installed globally (user level) or per workspace. Global servers sync via Settings Sync.

- **Q: What if an MCP server isn't working?**
  - A: Check the server output logs via "Show Output" action, verify model access permissions, and ensure server is started.

- **Q: How do I enable auto-discovery for MCP servers?**
  - A: Set `chat.mcp.discovery.enabled` to `true` in settings to detect servers from other applications.

**Common Issues:**

- **Server not appearing in tools:** Verify installation completed and server is started
- **Installation fails:** Check network connectivity and server URL accessibility
- **Server crashes:** Review output logs and check system requirements
- **Permission errors:** Ensure proper model access configuration and account authentication

**Security Considerations:**

- MCP servers run arbitrary code - only install from trusted publishers
- Review server permissions and model access carefully
- Monitor server activity through output logs
- Uninstall unused servers to reduce attack surface

## 5. Additional Resources

- MCP Gallery: [VS Code MCP Servers](https://code.visualstudio.com/mcp)
- Official documentation: [MCP Servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
- Developer guide: [Building MCP Servers](https://code.visualstudio.com/api/extension-guides/ai/mcp)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: MCP Support, MCP as First-Class Resources

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for MCP Server Discovery and Installation |
