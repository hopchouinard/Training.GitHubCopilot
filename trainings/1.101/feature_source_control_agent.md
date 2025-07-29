---
feature: "Source Control - Copilot Agent Integration & History Details"
release: "1.101"
prerequisites:
  - "GitHub Pull Requests extension installed"
  - "GitHub Copilot subscription and extension"
  - "Git repository with GitHub remote"
  - "Basic understanding of Git and pull requests"
audience: "Developers, Team Leads, DevOps Engineers, Git Users"
---

# 🚀 Feature Training: `Source Control - Copilot Agent Integration & History Details` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Source Control - Copilot Agent Integration & History Details`
- **Release Version:** `1.101`
- **Feature Type:** `Source Control Enhancement, AI Collaboration, Workflow Integration`
- **Summary:**  
  Enhanced source control features including deep Copilot coding agent integration for automated pull request management, improved source control history item details with file viewing capabilities, and the ability to add commit history as context for AI chat sessions. These features streamline collaborative workflows and provide better visibility into code changes.

## 2. Why It Matters

- **Core Problem Solved:** Bridges the gap between AI-automated coding tasks and traditional source control workflows. Provides transparency and control over automated changes while enhancing code review and collaboration processes.
- **Target Users:** Development teams using GitHub, developers leveraging AI-assisted coding, project maintainers, code reviewers, and teams implementing DevOps workflows.
- **Context:** Requires GitHub Pull Requests extension and Copilot subscription. Features integrate with existing Git workflows without disrupting established practices.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- GitHub Pull Requests extension: `GitHub.vscode-pull-request-github`
- GitHub Copilot extension with active subscription
- Git repository connected to GitHub remote
- Appropriate repository permissions for pull request management

### 3.2 How to Enable/Access

- **Copilot Agent Integration:** Enable `githubPullRequests.codingAgent.uiIntegration` setting
- **Source Control View:** Click Source Control icon in sidebar or `Ctrl+Shift+G`
- **Graph View:** Source Control → "Graph" view tab
- **Chat Integration:** Use `#copilotCodingAgent` tool in chat or "Delegate to coding agent" button
- **History Context:** Chat → "Add Context" → "Source Control"

### 3.3 Step-by-Step Usage

#### 3.3.1 Copilot Coding Agent Integration

1. **Assign Issues to Copilot:** In GitHub Pull Requests view → Select issue → "Assign to Copilot"
2. **Delegate from Chat:** In chat, use `#copilotCodingAgent` tool or click "Delegate to coding agent" button
3. **Track Agent Progress:** View "Copilot on My Behalf" query to see active agent work
4. **Monitor Sessions:** Click "View Session" to see detailed logs of agent actions
5. **Review Results:** Agent creates pull requests automatically with full context preservation

**Delegation Workflow:**

```
Issue Assignment → Chat Delegation → Agent Session Start 
→ Remote Branch Creation → Automated Coding → Pull Request Creation 
→ Session Logging → Review & Merge
```

#### 3.3.2 Source Control History Item Details

1. **Access Graph View:** Source Control → "Graph" tab
2. **Select History Item:** Click any commit in the graph
3. **View File Resources:** See all changed files in tree or list view (toggle via `...` menu)
4. **Individual File Diff:** Click specific file to open diff editor for that file
5. **Multi-file Diff:** Use "Open Changes" action on hover to see all changes together
6. **File Navigation:** Use "Open File" action to view specific version of file

#### 3.3.3 Add History to Chat Context

1. **From Chat View:** "Add Context" → "Source Control" → Select specific commit
2. **From Graph View:** Right-click commit → "Copilot" → "Add History Item to Chat"
3. **Context Usage:** Chat now has commit details, changes, and metadata as context
4. **Analysis Queries:** Ask questions about specific commits or code changes

### 3.4 Example(s)

#### Simple Example: Delegating Bug Fix to Agent

```
1. Open GitHub Pull Requests view
2. Find bug report issue
3. Click "Assign to Copilot"
4. In chat: "Fix the authentication timeout issue described in issue #123"
5. Click "Delegate to coding agent"
6. Monitor progress in "Copilot on My Behalf" query
7. Review created pull request when complete
```

#### Advanced Example: Code Review with History Context

```
1. In Source Control Graph, select commit with complex changes
2. Right-click → "Copilot" → "Add History Item to Chat"
3. Chat query: "Analyze this commit for potential security issues and suggest improvements"
4. AI reviews commit with full context of changed files
5. Receive detailed analysis and recommendations
6. Use insights for code review process
```

#### Agent Session Management Example

```
Active Agent Session:
- View Session → See real-time log of agent actions
- Monitor: File changes, command executions, API calls
- Intervention: Stop agent if needed or provide additional guidance
- Review: Complete session log for audit and learning
```

### 3.5 Agent Session Transparency Features

#### Session Logging

- **Real-time Actions:** View every command and file change as they happen
- **Tool Usage:** See which tools and APIs the agent invokes
- **Decision Points:** Understand agent reasoning and approach
- **Error Handling:** Monitor how agent handles and recovers from errors

#### Pull Request Context

- **Automated PR Creation:** Agent creates PRs with descriptive titles and descriptions
- **Session Linking:** PRs include links to agent session details
- **Change Documentation:** Comprehensive documentation of what was changed and why
- **Review Ready:** PRs include context for human reviewers

## 4. Troubleshooting & FAQ

### Common Issues

- **Agent Button Not Appearing:** Ensure `githubPullRequests.codingAgent.uiIntegration` is enabled and repository is eligible
- **No Session Logs:** Check GitHub Copilot subscription status and permissions
- **Graph View Missing Files:** Ensure Git repository is properly initialized and has commit history
- **Context Addition Fails:** Verify chat extension is active and commit is accessible

### How to Disable

- **Disable Agent Integration:** Set `githubPullRequests.codingAgent.uiIntegration` to `false`
- **Stop Active Sessions:** Use "Copilot on My Behalf" → Select session → Stop
- **Remove History Context:** Delete context items from chat input
- **Traditional Workflow:** Continue using standard Git commands and PR creation

### Edge Cases

- **Large Repository Performance:** Graph view may be slow with very large commit histories
- **Complex Merge Conflicts:** Agent may require human intervention for complex conflicts
- **Permission Issues:** Agent requires appropriate repository write permissions
- **Network Connectivity:** Session monitoring requires stable internet connection

### FAQ

**Q: Can the agent work on private repositories?**
A: Yes, agent works with private repositories if you have appropriate access and Copilot subscription.

**Q: How do I review agent-generated code before merging?**
A: Agent creates standard pull requests that go through your normal review process.

**Q: Can I stop an agent session mid-execution?**
A: Yes, use the "Copilot on My Behalf" view to stop active sessions.

**Q: Does the agent follow branch protection rules?**
A: Yes, agent-created PRs respect all repository settings and protection rules.

## 5. Additional Resources

- **GitHub Pull Requests Extension:** [Marketplace Link](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)
- **Copilot Coding Agent Blog:** [Official Announcement](https://code.visualstudio.com/blogs/2025/07/17/copilot-coding-agent)
- **Source Control Documentation:** [VS Code Git Integration](https://code.visualstudio.com/docs/sourcecontrol/overview)
- **GitHub Copilot Guide:** [Getting Started with Copilot](https://code.visualstudio.com/docs/copilot/overview)
- **Related Features:** Chat Improvements, Agent Mode, GitHub Integration

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Source Control Agent Integration |
