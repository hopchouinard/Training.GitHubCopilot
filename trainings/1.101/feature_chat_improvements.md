---
feature: "Chat Improvements"
release: "1.101"
prerequisites:
  - "Basic understanding of VS Code Chat functionality"
  - "Familiarity with GitHub Copilot or AI assistants"
  - "Knowledge of JSON and Markdown file formats"
audience: "All Users, Developers, Power Users customizing AI workflows"
---

# 🚀 Feature Training: `Chat Improvements` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Chat Improvements`
- **Release Version:** `1.101`
- **Feature Type:** `AI/Chat Enhancement, User Experience`
- **Summary:**  
  Comprehensive chat enhancements including tool sets for organizing related tools, custom chat modes for specialized workflows, improved UX with better visual distinction and navigation, enhanced context awareness, and diagnostic integration for smarter AI responses.

## 2. Why It Matters

- **Core Problem Solved:** Streamlines chat workflows by organizing tools, enables specialized AI behavior through custom modes, improves chat readability and navigation, and provides better context awareness for more accurate AI responses.
- **Target Users:** All VS Code users leveraging AI chat, developers customizing AI workflows, teams collaborating with shared chat configurations, power users creating specialized tools.
- **Context:** Features are progressively enabled; custom chat modes are in preview. Tool sets and UX improvements are available immediately.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- GitHub Copilot or compatible AI assistant extension
- For custom modes: Understanding of Markdown and YAML front matter

### 3.2 How to Enable/Access

- **Tool Sets:** Command Palette → `Configure Tool Sets` → `Create new tool sets file`
- **Custom Chat Modes:** Command Palette → `Chat: Configure Chat Modes`
- **Chat View:** Side panel or Command Palette → `View: Toggle Chat`
- **Floating Windows:** Drag chat panel to create floating window
- **Tool Configuration:** In chat, click **Configure Tools** button

### 3.3 Step-by-Step Usage

#### 3.3.1 Creating and Using Tool Sets

1. **Create Tool Set:** Command Palette → `Configure Tool Sets` → `Create new tool sets file`
2. **Define Tool Set:** Configure in JSON format:

```json
{
  "gh-news": {
    "tools": [
      "list_notifications",
      "dismiss_notification", 
      "get_notification_details"
    ],
    "description": "Manage GitHub notifications",
    "icon": "github-project"
  }
}
```

1. **Use Tool Set:** In chat, reference with `#gh-news` or select from tool picker
1. **Manage Tool Sets:** Edit the JSON file to add/remove tools or create new sets

#### 3.3.2 Custom Chat Modes (Preview)

1. **Create Custom Mode:** Command Palette → `Chat: Configure Chat Modes`
2. **Configure Mode File:** Edit the generated `*.chatprompt.md` file:

```markdown
---
description: Generate implementation plans for new features
tools: ['codebase', 'search', 'usages', 'findTestFiles']
---
# Planning Mode Instructions
You are in planning mode. Generate implementation plans without making code edits.

Create a plan with these sections:
* Overview: Brief feature description
* Requirements: Feature requirements list  
* Implementation Steps: Detailed implementation steps
* Testing: Required test implementations
```

1. **Select Mode:** In Chat view, use chat mode dropdown to select your custom mode
1. **Use Mode:** Submit prompts - AI will follow custom instructions and use specified tools

#### 3.3.3 Enhanced UX Features

1. **Visual Distinction:** User and AI messages now have distinct appearances for clarity
1. **Undo Requests:**
   - Hover over request → Click `X` button to undo
   - Use keyboard shortcut to undo edits
1. **Implicit Context:**
   - Current file offered as suggested context
   - Press `Shift+Tab, Enter` to quickly add current file
1. **Floating Windows:**
   - Drag chat to create floating window
   - Use **Dock** button to return to main window
   - Use **New Chat** button for additional sessions

#### 3.3.4 Tool Customization

1. **Access Tool Configuration:** In agent mode, click **Configure Tools** button
2. **Enable/Disable Tools:** Use tool picker to select desired tools:
   - Disable `editFiles` to prevent direct file editing
   - Disable `runCommands` to prevent terminal command execution
   - Enable specific tool sets for focused workflows
3. **Apply Changes:** Tool configuration applies to current and future chats

### 3.4 Example(s)

#### Simple Example: Using Tool Sets

```
User: #gh-news show me unread notifications
AI: [Uses GitHub notification tools to list unread notifications]

User: #gh-news dismiss all notifications older than 7 days  
AI: [Uses dismiss_notification tool to clean up old notifications]
```

#### Advanced Example: Custom Planning Mode

```markdown
---
description: Architecture review mode for system design
tools: ['codebase', 'search', 'usages', 'githubRepo']
---
# Architecture Review Instructions
You are an architecture reviewer. Analyze codebases for:
- Design patterns and adherence to principles
- Performance bottlenecks and scalability issues  
- Security vulnerabilities and best practices
- Documentation gaps and improvement suggestions

Provide structured reviews with prioritized recommendations.
```

**Usage:**

1. Select "Architecture Review" mode from dropdown
2. Query: "Review the authentication system in this codebase"
3. AI analyzes code using only read-only tools, provides structured architecture review

## 4. Troubleshooting & FAQ

### Common Issues

- **Custom Mode Not Appearing:** Ensure `*.chatprompt.md` file is properly formatted with valid YAML front matter
- **Tool Set Not Working:** Verify JSON syntax in tool sets configuration file
- **Tools Not Available:** Check if required extensions are installed and tools are enabled in configuration
- **Context Not Adding:** Ensure file is saved and use `Shift+Tab, Enter` shortcut for quick context addition

### How to Disable

- **Remove Tool Sets:** Delete entries from tool sets JSON configuration file
- **Disable Custom Modes:** Remove `*.chatprompt.md` files or don't select custom modes
- **Reset Tool Configuration:** Use **Configure Tools** to reset to default tool selection
- **Revert UX Changes:** Features are UI improvements without disable options

### Edge Cases

- **Preview Features:** Custom chat modes are in preview and may change
- **Tool Conflicts:** Some tools may conflict; test custom configurations thoroughly
- **Performance:** Large tool sets or complex custom modes may impact response time
- **Context Limits:** Large context additions may hit model token limits

## 5. Additional Resources

- **Official Documentation:** [Chat in VS Code](https://code.visualstudio.com/docs/copilot/chat/copilot-chat)
- **Custom Chat Modes:** [Chat Modes Guide](https://code.visualstudio.com/docs/copilot/chat/chat-modes)
- **Tool Sets Documentation:** [Chat Agent Mode](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode#_define-tool-sets)
- **Context Guide:** [Adding Context in Chat](https://code.visualstudio.com/docs/copilot/chat/copilot-chat-context)
- **Related Features:** MCP Enhancements, Agent Mode improvements, Task Configuration

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Chat Improvements |
