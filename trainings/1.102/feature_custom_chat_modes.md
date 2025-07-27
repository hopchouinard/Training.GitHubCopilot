---
feature: "Custom Chat Modes"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription with Chat"
  - "Basic understanding of markdown"
  - "Familiarity with VS Code settings"
audience: "Developers and teams wanting specialized AI chat workflows"
---

# 🚀 Feature Training: `Custom Chat Modes` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Custom Chat Modes`
- **Release Version:** `1.102`
- **Feature Type:** `Chat Enhancement`
- **Summary:**  
  User-defined chat configurations that allow you to create specialized AI assistant behaviors with custom instructions, tools, and even specific language models for targeted workflows.

## 2. Why It Matters

- **Workflow Specialization:** Create focused chat experiences for specific tasks like code review, planning, or bug triage
- **Consistency:** Ensure AI responses follow organizational or project standards
- **Efficiency:** Quick switching between specialized assistant personas without manual setup
- **Customization:** Full control over instructions, available tools, and AI model selection
- **Target Users:** Development teams, project leads, and power users with specialized workflows
- **Status:** Available in VS Code 1.102+ as an improved feature from 1.101

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription with Chat enabled
- Basic understanding of markdown syntax
- Knowledge of file system organization (workspace vs user settings)

### 3.2 How to Enable/Access

- **Command Palette:** `Ctrl+Shift+P` → "Chat: New Mode File"
- **Configure Chat Menu:** Click gear icon in Chat view → "Modes"
- **File Extension:** `.chatmode.md`
- **Storage Locations:**
  - Workspace: `.vscode/` folder (team sharing)
  - User Profile: User settings directory (personal use)

### 3.3 Step-by-Step Usage

1. **Create a New Chat Mode:**
   - Open Command Palette (`Ctrl+Shift+P`)
   - Type "Chat: New Mode File" and select it
   - Choose location (workspace or user profile)

2. **Configure Mode Metadata:**

   ```markdown
   ---
   description: "Code review assistant with security focus"
   tools: ["codebase", "search", "problems"]
   model: "gpt-4"
   ---
   ```

3. **Add Custom Instructions:**

   ```markdown
   # Security-Focused Code Review Mode
   
   You are a security-focused code reviewer. When reviewing code:
   - Check for common security vulnerabilities
   - Verify input validation and sanitization
   - Look for authentication and authorization issues
   - Suggest secure coding practices
   ```

4. **Save and Use:**
   - Save the `.chatmode.md` file
   - Mode appears in Chat view mode selector
   - Select mode before starting conversations

### 3.4 Example(s)

- **Simple example:**  
  Create a "Planning Mode" for project planning discussions:

  ```markdown
  ---
  description: "Project planning and architecture discussions"
  tools: ["codebase", "search"]
  ---
  
  # Planning Assistant
  
  Focus on high-level architecture and planning. Break down complex 
  features into smaller tasks and suggest implementation strategies.
  ```

- **Advanced/tip:**  
  Create a team-specific mode that references external instruction files:

  ```markdown
  ---
  description: "Company coding standards reviewer"
  tools: ["codebase", "search", "problems", "editFiles"]
  model: "gpt-4-turbo"
  ---
  
  # Company Standards Mode
  
  @file:company-coding-standards.md
  
  Apply our company's coding standards when reviewing and suggesting code.
  ```

**Mode comparison:**

| Built-in Modes | Custom Modes |
|----------------|--------------|
| Fixed instructions | User-defined instructions |
| Preset tools | Configurable tools |
| Default model | Selectable model |
| Not editable | Fully editable |
| General purpose | Specialized workflows |

## 4. Troubleshooting & FAQ

- **Q: Where should I save my custom chat modes?**
  - A: For team sharing, save in workspace `.vscode/` folder. For personal use, save in user profile directory.

- **Q: Can I share modes with my team?**
  - A: Yes, modes saved in the workspace are automatically available to all team members who open the project.

- **Q: What tools can I specify in custom modes?**
  - A: Built-in tools like "codebase", "search", "editFiles", "problems", plus any tools provided by extensions or MCP servers.

- **Q: How do I import modes from the community?**
  - A: Use `vscode:` links from repositories like awesome-copilot, or copy `.chatmode.md` files directly.

- **Q: Can I use different AI models in different modes?**
  - A: Yes, specify the `model` property in the metadata. IntelliSense provides available model options.

**Common Issues:**

- **Mode not appearing:** Check file extension is `.chatmode.md` and file is in correct location
- **Tools not working:** Verify tool names are correct and required extensions are installed
- **Model not available:** Ensure specified model is available in your Copilot subscription

## 5. Additional Resources

- Official documentation: [Custom Chat Modes](https://code.visualstudio.com/docs/copilot/chat/chat-modes)
- Community modes: [Awesome Copilot Repository](https://github.com/github/awesome-copilot)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: Custom Instructions, Import via Link, MCP Tools

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Custom Chat Modes |
