---
feature: "Tasks - Instance Policy"
release: "1.101"
prerequisites:
  - "Basic understanding of VS Code tasks and tasks.json"
  - "Familiarity with JSON configuration files"
  - "Knowledge of command line tools and build processes"
audience: "Developers, DevOps Engineers, Build Engineers, Power Users"
---

# 🚀 Feature Training: `Tasks - Instance Policy` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Tasks - Instance Policy`
- **Release Version:** `1.101`
- **Feature Type:** `Task Management Enhancement, Workflow Control`
- **Summary:**  
  New `instancePolicy` property in task `runOptions` that provides fine-grained control over task behavior when reaching the `instanceLimit`. This feature allows developers to specify what happens when attempting to run a task that has already reached its maximum number of concurrent instances.

## 2. Why It Matters

- **Core Problem Solved:** Eliminates uncertainty and provides predictable behavior when multiple instances of the same task are requested. Prevents accidental duplicate processes while allowing flexible task management strategies.
- **Target Users:** Developers using build systems, DevOps engineers managing deployment tasks, teams with automated workflows, and power users with complex task configurations.
- **Context:** Enhances existing task system without breaking changes. Default behavior maintains backward compatibility while providing new control options.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- Understanding of VS Code tasks and `.vscode/tasks.json` configuration
- Basic knowledge of JSON syntax and task properties
- Familiarity with concurrent process management concepts

### 3.2 How to Enable/Access

- **Configuration:** Edit `.vscode/tasks.json` in your workspace
- **Task Runner:** Access via Command Palette → `Tasks: Run Task`
- **Task Configuration:** Command Palette → `Tasks: Configure Task`
- **Property Location:** Add `instancePolicy` to task's `runOptions` object

### 3.3 Step-by-Step Usage

#### 3.3.1 Basic Instance Policy Configuration

1. **Open Task Configuration:** Command Palette → `Tasks: Configure Task` or edit `.vscode/tasks.json`
2. **Add runOptions:** Include `runOptions` object in your task definition
3. **Set Instance Policy:** Add `instancePolicy` property with desired behavior
4. **Test Behavior:** Run task multiple times to verify policy enforcement

#### 3.3.2 Instance Policy Options

**Available Policies:**

- **`prompt` (default):** Ask user what to do when instance limit is reached
- **`silent`:** Ignore new task requests when limit is reached
- **`terminateNewest`:** Stop the most recently started instance to make room for new one
- **`terminateOldest`:** Stop the oldest running instance to make room for new one
- **`warn`:** Show warning but don't start new instance

#### 3.3.3 Configuration Examples

##### Example 1: Build Task with Prompt Policy

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build-project",
      "type": "shell",
      "command": "npm run build",
      "runOptions": {
        "instanceLimit": 1,
        "instancePolicy": "prompt"
      }
    }
  ]
}
```

##### Example 2: Watch Task with Silent Policy

```json
{
  "label": "watch-files",
  "type": "shell",
  "command": "npm run watch",
  "runOptions": {
    "instanceLimit": 1,
    "instancePolicy": "silent"
  }
}
```

##### Example 3: Test Runner with Terminate Policy

```json
{
  "label": "run-tests",
  "type": "shell",
  "command": "npm test",
  "runOptions": {
    "instanceLimit": 2,
    "instancePolicy": "terminateOldest"
  }
}
```

### 3.4 Example(s)

#### Simple Example: Development Server

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "dev-server",
      "type": "shell",
      "command": "npm start",
      "runOptions": {
        "instanceLimit": 1,
        "instancePolicy": "terminateOldest"
      },
      "group": "build",
      "presentation": {
        "echo": true,
        "reveal": "always",
        "focus": false,
        "panel": "new"
      }
    }
  ]
}
```

**Behavior:** If you try to start the dev server while one is already running, the old instance will be terminated and a new one started.

#### Advanced Example: Multi-Environment Deployment

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "deploy-staging",
      "type": "shell",
      "command": "npm run deploy:staging",
      "runOptions": {
        "instanceLimit": 1,
        "instancePolicy": "warn"
      }
    },
    {
      "label": "deploy-production",
      "type": "shell",
      "command": "npm run deploy:prod",
      "runOptions": {
        "instanceLimit": 1,
        "instancePolicy": "prompt"
      }
    },
    {
      "label": "run-tests-parallel",
      "type": "shell",
      "command": "npm run test:parallel",
      "runOptions": {
        "instanceLimit": 3,
        "instancePolicy": "terminateNewest"
      }
    }
  ]
}
```

**Workflow Scenarios:**

- **Staging Deployment:** Shows warning if deployment already running, prevents accidental duplicates
- **Production Deployment:** Prompts user for decision, ensuring deliberate action
- **Parallel Tests:** Allows up to 3 concurrent test runs, terminates newest when limit exceeded

#### Real-World Use Case: CI/CD Pipeline

```json
{
  "label": "ci-pipeline",
  "type": "shell",
  "command": "scripts/ci-pipeline.sh",
  "args": ["${input:environment}"],
  "runOptions": {
    "instanceLimit": 2,
    "instancePolicy": "prompt"
  },
  "dependsOn": ["lint", "test"],
  "problemMatcher": "$eslint-stylish"
}
```

**Benefits:**

- Prevents pipeline conflicts while allowing flexibility
- User control over concurrent pipeline executions
- Clear feedback when limits are reached

## 4. Troubleshooting & FAQ

### Common Issues

- **Policy Not Working:** Ensure VS Code version is 1.101+ and `instancePolicy` is properly nested in `runOptions`
- **Unexpected Terminations:** Check if `terminateOldest` or `terminateNewest` policies are causing unintended behavior
- **Prompt Not Appearing:** Verify `prompt` policy is set correctly and no other policies are overriding
- **Silent Policy Too Aggressive:** Consider using `warn` policy for better user feedback

### How to Disable

- **Remove Property:** Delete `instancePolicy` from `runOptions` to revert to default behavior
- **Use Default:** Set `instancePolicy` to `prompt` for original VS Code behavior
- **Increase Limit:** Raise `instanceLimit` to accommodate more concurrent instances
- **Legacy Behavior:** Remove entire `runOptions` object for pre-1.101 behavior

### Edge Cases

- **Task Dependencies:** Instance policies apply to individual tasks, not their dependencies
- **Different Workspaces:** Each workspace maintains separate instance counts
- **Terminal vs Background Tasks:** Policy behavior may vary based on task presentation settings
- **Process Cleanup:** Terminated tasks may need time for proper cleanup

### FAQ

**Q: What happens if I don't set an instancePolicy?**
A: The default behavior is `prompt`, which asks the user what to do when the limit is reached.

**Q: Can I set different policies for the same task in different situations?**
A: No, the policy is defined per task configuration. Create separate task definitions for different behaviors.

**Q: Does instancePolicy work with background tasks?**
A: Yes, but the user experience may differ for background vs. terminal-based tasks.

**Q: Can I change instancePolicy while tasks are running?**
A: Changes take effect for new task executions; currently running tasks continue with their original policy.

## 5. Additional Resources

- **VS Code Tasks Documentation:** [Configure Tasks](https://code.visualstudio.com/docs/editor/tasks)
- **Task JSON Schema:** [Tasks Schema Reference](https://code.visualstudio.com/docs/editor/tasks-appendix)
- **Community Examples:** [VS Code Tasks Examples](https://github.com/microsoft/vscode/tree/main/extensions/task-common)
- **GitHub Issue:** [Original Feature Request #90125](https://github.com/microsoft/vscode/issues/90125)
- **Related Features:** Terminal Integration, Build Tasks, Debug Configuration

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Tasks Instance Policy |
