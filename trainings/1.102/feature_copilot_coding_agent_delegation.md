---
feature: "Copilot Coding Agent Delegation"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription"
  - "GitHub repository with Copilot Coding Agent enabled"
  - "GitHub Pull Requests and Issues extension"
audience: "Developers and teams wanting to automate routine coding tasks"
---

# 🚀 Feature Training: `Copilot Coding Agent Delegation` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Copilot Coding Agent Delegation`
- **Release Version:** `1.102`
- **Feature Type:** `AI Automation Enhancement`
- **Summary:**  
  Ability to delegate coding tasks to GitHub Copilot Coding Agent, which works autonomously in the background using GitHub Actions and creates pull requests with the completed work.

## 2. Why It Matters

- **Task Automation:** Delegate routine, well-defined coding tasks to focus on complex work
- **Background Processing:** Agent works autonomously without blocking your development workflow
- **Transparent Process:** Full visibility into agent decisions and actions through session logs
- **Quality Control:** Agent creates pull requests for review before code integration
- **Target Users:** Development teams with established repositories and routine coding tasks
- **Status:** Available for repositories with Copilot Coding Agent enabled

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription
- Repository with Copilot Coding Agent enabled
- GitHub Pull Requests and Issues extension installed
- Proper repository permissions for creating pull requests

### 3.2 How to Enable/Access

- **Repository Setup:** Enable Copilot Coding Agent in repository settings
- **Extension Required:** GitHub Pull Requests and Issues extension
- **Access Point:** Pull Requests view in VS Code Activity Bar
- **Delegation Methods:**
  - Assign GitHub Issues to the coding agent
  - Use `#copilotCodingAgent` tool in Copilot Chat
  - "Delegate to coding agent" button (experimental UI integration)

### 3.3 Step-by-Step Usage

1. **Enable Experimental UI (Optional):**
   - Set `githubPullRequests.codingAgent.uiIntegration` to `true`
   - Enables additional UI integration features

2. **Delegate a Task:**
   - **Method 1:** In Pull Requests view, assign GitHub Issue to coding agent
   - **Method 2:** Use `#copilotCodingAgent` in Copilot Chat with task description
   - **Method 3:** Click "Delegate to coding agent" button in Chat view

3. **Monitor Progress:**
   - Check "Copilot on My Behalf" section in Pull Requests view
   - View real-time progress updates
   - Track numeric badge for new changes

4. **Review Session Details:**
   - Click "View Session" to see detailed action log
   - Review every decision and action taken by the agent
   - Understand the agent's problem-solving approach

5. **Review and Merge:**
   - Agent creates pull request when task is complete
   - Review the code changes as you would any PR
   - Merge, request changes, or provide feedback

### 3.4 Example(s)

- **Simple example:**  
  Delegate a refactoring task: "Refactor the user authentication module to use modern async/await patterns instead of callbacks."

- **Advanced/tip:**  
  Delegate feature implementation: "Add a trending posts section to the homepage, including database schema changes, API endpoints, and UI components."

**Delegation workflow:**

```
1. Task Assignment → 🤖 Agent receives task via GitHub Actions
2. Background Work → ⚙️ Agent implements changes autonomously  
3. Pull Request → 📝 Agent creates PR with completed work
4. Review Process → 👀 Developer reviews and merges/requests changes
```

**Types of tasks suitable for delegation:**

- ✅ Code refactoring and cleanup
- ✅ Adding logging and instrumentation
- ✅ Implementing well-defined features
- ✅ Backlog "nice to have" items
- ✅ Initial project scaffolding
- ❌ Complex architectural decisions
- ❌ Tasks requiring human judgment
- ❌ Customer-facing design decisions

## 4. Troubleshooting & FAQ

- **Q: How is this different from agent mode in Copilot Chat?**
  - A: Coding Agent works remotely via GitHub Actions and creates PRs, while agent mode works locally in your VS Code environment.

- **Q: Can I stop an agent session if I'm not happy with progress?**
  - A: Yes, you can terminate any agent session at any time from the "Copilot on My Behalf" section.

- **Q: What happens if the agent encounters issues?**
  - A: The agent will document any problems in the session log and may create a partial PR or issue for further guidance.

- **Q: How do I know what the agent is doing?**
  - A: Full transparency through session logs showing every action, decision, and code change made by the agent.

**Common Issues:**

- **Agent not available:** Ensure repository has Copilot Coding Agent enabled
- **Tasks not starting:** Check repository permissions and GitHub Actions availability
- **No session tracking:** Install GitHub Pull Requests and Issues extension
- **UI features missing:** Enable experimental UI integration setting

## 5. Additional Resources

- Official blog post: [Copilot Coding Agent](https://code.visualstudio.com/blogs/2025/07/17/copilot-coding-agent)
- Documentation: [About Copilot Coding Agent](https://docs.github.com/en/copilot/concepts/about-copilot-coding-agent)
- Extension: [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)
- Related features: Agent Mode, Custom Chat Modes, MCP Support

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Copilot Coding Agent Delegation |
