---
feature: "MCP Servers as First-Class Resources"
release: "1.102"
prerequisites:
  - "Understanding of VS Code profiles"
  - "Basic knowledge of MCP servers"
  - "Familiarity with Settings Sync (optional)"
audience: "Developers using multiple VS Code profiles and MCP servers across different workflows"
---

# 🚀 Feature Training: `MCP Servers as First-Class Resources` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `MCP Servers as First-Class Resources`
- **Release Version:** `1.102`
- **Feature Type:** `Architecture Enhancement`
- **Summary:**  
  Major architectural improvement that moves MCP servers from user settings to dedicated profile-specific configuration files, enabling better workflow isolation, Settings Sync integration, and cleaner configuration management.

## 2. Why It Matters

- **Better Organization:** MCP servers have dedicated storage separate from general VS Code settings
- **Profile Isolation:** Each VS Code profile maintains its own set of MCP servers for workflow-specific configurations
- **Enhanced Syncing:** Granular control over which MCP configurations sync across devices
- **Cleaner Settings:** General settings.json stays focused without MCP server clutter
- **Target Users:** Developers using multiple profiles, teams with different workflows, and users with complex MCP setups
- **Status:** Automatic migration provided for existing MCP configurations

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- Understanding of VS Code profiles concept
- Existing MCP server configurations (for migration scenarios)
- Knowledge of JSON configuration files

### 3.2 How to Enable/Access

- **Automatic Migration:** Existing settings.json MCP servers are automatically migrated
- **New Storage Location:** `mcp.json` file within each profile directory
- **Settings Sync Integration:** Controlled through Settings Sync preferences
- **Profile Management:** Each profile maintains independent MCP configuration

### 3.3 Step-by-Step Usage

1. **Migration (Automatic):**
   - VS Code detects existing MCP servers in settings.json
   - Automatically migrates to new mcp.json format
   - Shows notification explaining the change
   - Original settings are preserved during transition

2. **Profile-Specific Configuration:**
   - Create or switch to desired VS Code profile
   - Configure MCP servers specific to that profile's workflow
   - Servers only appear when that profile is active

3. **Settings Sync Management:**
   - Choose which MCP configurations sync across devices
   - Enable/disable MCP sync independently of other settings
   - Control sharing of sensitive server configurations

4. **Access Configuration Files:**
   - Use "MCP: Open User Configuration" command
   - Use "MCP: Open Remote User Configuration" for remote environments
   - Direct file editing for advanced configurations

### 3.4 Example(s)

- **Simple example:**  
  Web development profile with Playwright MCP server, Python profile with data analysis servers, each isolated from the other.

- **Advanced/tip:**  
  Configure Dev Container with specific MCP servers in devcontainer.json that automatically apply when container starts.

**Configuration structure:**

```json
// Profile 1: Web Development (mcp.json)
{
  "servers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"]
    },
    "browser-automation": {
      "command": "node", 
      "args": ["./browser-tools.js"]
    }
  }
}

// Profile 2: Data Science (mcp.json)  
{
  "servers": {
    "jupyter": {
      "command": "python",
      "args": ["-m", "jupyter_mcp"]
    },
    "database": {
      "command": "python",
      "args": ["./db_mcp_server.py"]
    }
  }
}
```

**Dev Container support:**

```json
// devcontainer.json
{
  "image": "mcr.microsoft.com/devcontainers/typescript-node:latest",
  "customizations": {
    "vscode": {
      "mcp": {
        "servers": {
          "playwright": {
            "command": "npx",
            "args": ["@playwright/mcp@latest"]
          }
        }
      }
    }
  }
}
```

## 4. Troubleshooting & FAQ

- **Q: What happened to my MCP servers after upgrading?**
  - A: They were automatically migrated to the new mcp.json format. Check "MCP SERVERS - INSTALLED" view to verify.

- **Q: Can I still share MCP configurations with my team?**
  - A: Yes, through workspace-specific mcp.json files, Dev Container configurations, or Settings Sync.

- **Q: How do I configure different MCP servers for different projects?**
  - A: Use VS Code profiles with profile-specific MCP configurations, or workspace-level mcp.json files.

- **Q: Where are the new MCP configuration files stored?**
  - A: In profile-specific directories, accessible via "MCP: Open User Configuration" command.

**Migration Considerations:**

- **Settings cleanup:** Remove old MCP entries from settings.json after successful migration
- **Profile organization:** Review which MCP servers belong with which profiles
- **Sync preferences:** Configure Settings Sync to include/exclude MCP configurations as needed
- **Team sharing:** Update team documentation to reflect new configuration locations

**Cross-Environment Support:**

- ✅ Local VS Code installations
- ✅ Remote SSH environments  
- ✅ WSL (Windows Subsystem for Linux)
- ✅ GitHub Codespaces
- ✅ Dev Containers
- ✅ Settings Sync across devices

## 5. Additional Resources

- Official documentation: [MCP Servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
- Profile documentation: [VS Code Profiles](https://code.visualstudio.com/docs/configure/profiles)
- Settings Sync: [Settings Sync Documentation](https://code.visualstudio.com/docs/configure/settings-sync)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: MCP Support, MCP Server Discovery

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for MCP Servers as First-Class Resources |
