---
feature: "Terminal Auto-Approval (Experimental)"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription with Chat"
  - "Understanding of terminal commands and security implications"
  - "Basic knowledge of regular expressions (optional)"
audience: "Power users, DevOps engineers, and developers comfortable with terminal automation"
---

# 🚀 Feature Training: `Terminal Auto-Approval (Experimental)` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Terminal Auto-Approval (Experimental)`
- **Release Version:** `1.102`
- **Feature Type:** `Chat Agent Enhancement`
- **Summary:**  
  Experimental feature in Copilot Chat agent mode that automatically approves selected terminal commands based on configurable allow/deny lists, reducing the need for manual confirmation.

## 2. Why It Matters

- **Workflow Efficiency:** Reduces interruptions by auto-approving safe, commonly used commands
- **Development Speed:** Enables faster CI/CD workflows and automated testing without constant confirmations
- **Customizable Security:** Teams can define their own trust boundaries for command execution
- **Reduced Friction:** Streamlines agent mode interactions for repetitive, safe operations
- **Target Users:** Power users, DevOps engineers, and development teams with established command patterns
- **Status:** Experimental feature requiring manual configuration

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription with Chat agent mode
- Understanding of terminal command security implications
- Basic knowledge of regular expressions (helpful for advanced patterns)

### 3.2 How to Enable/Access

- **Settings Configuration:** Manual setup in `settings.json`
- **Setting Names:**
  - `github.copilot.chat.agent.terminal.allowList`
  - `github.copilot.chat.agent.terminal.denyList`
- **Scope:** Can be configured at user, workspace, or global levels
- **Format:** JSON object with command patterns as keys and boolean values

### 3.3 Step-by-Step Usage

1. **Configure Allow List:**

   ```json
   {
     "github.copilot.chat.agent.terminal.allowList": {
       "npm run test": true,
       "/^git (status|log)$/": true,
       "echo": true,
       "ls": true,
       "pwd": true
     }
   }
   ```

2. **Set Up Deny List (Optional):**

   ```json
   {
     "github.copilot.chat.agent.terminal.denyList": {
       "rm": true,
       "del": true,
       "npm run danger": true
     }
   }
   ```

3. **Test the Configuration:**
   - Use Copilot Chat in agent mode
   - Ask agent to run commands from your allow list
   - Verify commands execute without approval prompts

4. **Monitor and Adjust:**
   - Review which commands are being auto-approved
   - Refine patterns based on actual usage
   - Add or remove commands as needed

### 3.4 Example(s)

- **Simple example:**  
  Configure auto-approval for basic file operations and git status checks:

  ```json
  {
    "github.copilot.chat.agent.terminal.allowList": {
      "ls": true,
      "pwd": true,
      "git status": true,
      "git log": true
    }
  }
  ```

- **Advanced/tip:**  
  Use regular expressions for flexible pattern matching:

  ```json
  {
    "github.copilot.chat.agent.terminal.allowList": {
      "/^npm run (test|build|lint)$/": true,
      "/^git (status|log|diff)$/": true
    },
    "github.copilot.chat.agent.terminal.denyList": {
      "/.*rm.*/": true,
      "/.*delete.*/": true
    }
  }
  ```

**Command execution flow:**

```
User: "Run the tests"
Agent: Executes `npm run test` → ✅ Auto-approved (in allow list)

User: "Delete all files" 
Agent: Wants to run `rm -rf *` → ❌ Blocked (in deny list or not in allow list)

User: "Check git status"
Agent: Executes `git status` → ✅ Auto-approved (matches regex pattern)
```

## 4. Troubleshooting & FAQ

- **Q: How do chained commands work?**
  - A: For commands like `foo && bar`, ALL sub-commands must be in the allow list. The system checks each part individually.

- **Q: What happens if a command isn't in either list?**
  - A: Commands not explicitly allowed require manual approval, which is the default behavior.

- **Q: Can workspace settings override user settings?**
  - A: Yes, settings are merged across scopes. Workspace settings can add to or override user-level configurations.

- **Q: What are some recommended safe commands for the allow list?**
  - A: `echo`, `ls`, `pwd`, `cat`, `git status`, `git log`, basic npm scripts like `npm run test`

**Security Best Practices:**

- Start with minimal allow lists and expand gradually
- Avoid broad patterns that might match unexpected commands
- Regularly audit your allow/deny lists
- Be especially careful with commands that can modify files or system state
- Use workspace-specific settings for project-related commands

**Default Suggestions (being considered):**

- **Allow list:** `echo`, `cd`, `ls`, `cat`, `pwd`, `git status`, `git log`
- **Deny list:** `rm`, `rmdir`, `del`, `kill`, `curl`, `wget`, `eval`, `chmod`

## 5. Additional Resources

- Official VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: Copilot Chat Agent Mode, Terminal Integration
- Security documentation: [Workspace Trust](https://code.visualstudio.com/docs/editing/workspaces/workspace-trust)

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Terminal Auto-Approval |
