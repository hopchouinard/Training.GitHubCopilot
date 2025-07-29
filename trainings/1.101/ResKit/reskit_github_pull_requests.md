---
feature: "GitHub Pull Requests Extension - Enhanced Experience & Copilot Integration"
release: "1.101"
resource_type: "Both"
audience: "Software Developers, Code Reviewers, DevOps Engineers"
prerequisites:
  - "GitHub Pull Requests extension (GitHub.vscode-pull-request-github)"
  - "GitHub account with repository access"
  - "GitHub Copilot subscription for agent features"
  - "Basic understanding of Git and GitHub workflows"
summary: |
  Streamlined exercises and demos for VS Code's GitHub Pull Requests extension enhancements in version 1.101, covering enhanced media support for private repositories, improved notification management, in-editor link handling, and Copilot agent integration for automated PR assistance.
---

# 🔗 Resource Kit: `GitHub Pull Requests Extension - Enhanced Experience & Copilot Integration` — `Exercise + Demo`

## Directory Structure

```
github-pr-extension-kit/
├── README.md
├── exercise-1-enhanced-media-support/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   ├── sample-pr-templates/
│   │   │   ├── bug-report.md
│   │   │   ├── feature-request.md
│   │   │   └── design-review.md
│   │   ├── test-repositories/
│   │   │   ├── public-repo/
│   │   │   │   └── README.md
│   │   │   └── private-repo-simulation/
│   │   │       ├── assets/
│   │   │       │   ├── screenshot.png
│   │   │       │   ├── diagram.svg
│   │   │       │   └── mockup.jpg
│   │   │       └── README.md
│   │   └── pr-examples/
│   │       ├── design-feedback-pr.md
│   │       ├── ui-changes-pr.md
│   │       └── architecture-review-pr.md
│   ├── starter/
│   │   ├── basic-pr/
│   │   │   └── README.md
│   │   └── media-templates/
│   │       └── comment-template.md
│   └── assets/
│       ├── private-media-demo.gif
│       └── image-rendering.png
├── exercise-2-notification-management/
│   ├── instructions.md
│   ├── solution/
│   │   ├── notification-configs/
│   │   │   ├── team-lead-settings.json
│   │   │   ├── reviewer-settings.json
│   │   │   └── contributor-settings.json
│   │   ├── workflow-examples/
│   │   │   ├── daily-review-routine.md
│   │   │   ├── urgent-notifications.md
│   │   │   └── batch-processing.md
│   │   └── automation-scripts/
│   │       ├── notification-filters.js
│   │       └── priority-sorter.js
│   ├── starter/
│   │   └── basic-notifications/
│   │       └── default-config.json
│   └── assets/
│       ├── notifications-workflow.gif
│       └── priority-indicators.png
├── demo-1-copilot-agent-integration/
│   ├── walkthrough.md
│   └── src/
│       ├── sample-project/
│       │   ├── .vscode/
│       │   │   └── settings.json
│       │   ├── src/
│       │   │   ├── main.py
│       │   │   └── utils.py
│       │   ├── tests/
│       │   │   └── test_main.py
│       │   └── README.md
│       ├── pr-scenarios/
│       │   ├── code-review-assignment.md
│       │   ├── bug-fix-assistance.md
│       │   └── feature-implementation.md
│       └── copilot-workflows/
│           ├── assignment-process.md
│           ├── session-management.md
│           └── tracking-progress.md
│   └── assets/
│       ├── copilot-assignment.gif
│       └── agent-workflow.png
└── demo-2-unified-pr-workflow/
    ├── walkthrough.md
    └── src/
        ├── complete-workflow/
        │   ├── .github/
        │   │   ├── pull_request_template.md
        │   │   └── workflows/
        │   │       └── pr-automation.yml
        │   ├── documentation/
        │   │   ├── code-review-guide.md
        │   │   └── pr-workflow.md
        │   └── examples/
        │       ├── feature-branch/
        │       │   ├── new-feature.py
        │       │   └── tests/
        │       └── bugfix-branch/
        │           ├── fixed-component.py
        │           └── tests/
        └── workflow-templates/
            ├── review-checklist.md
            ├── testing-guidelines.md
            └── merge-criteria.md
    └── assets/
        ├── unified-workflow.gif
        └── pr-lifecycle.png
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### github-pr-extension-kit/README.md

```
# GitHub Pull Requests Extension - Enhanced Experience & Copilot Integration — Exercise + Demo Resource Kit

Welcome! This streamlined resource kit contains:
- **Essential Exercises** with focused guides for key GitHub PR extension features
- **Practical Demos** showcasing real-world workflows with AI assistance
- **Simplified Solutions** with optimized configurations for immediate productivity

## What You'll Learn

1. **Enhanced Media Support** - View private repository images directly in VS Code
2. **Notification Management** - Streamlined notification workflow and priority handling
3. **Copilot Agent Integration** - AI-assisted PR management and automated assistance
4. **Unified PR Workflow** - Complete development lifecycle within VS Code

## Features Covered

- Private repository image rendering in PR comments
- Improved notifications view with better management
- In-editor link handling for seamless navigation
- Copilot agent assignment and session management
- Integrated PR review and management workflow

## Prerequisites

- VS Code 1.101+
- GitHub Pull Requests extension (GitHub.vscode-pull-request-github)
- GitHub account with repository access
- GitHub Copilot subscription for agent features
- Basic understanding of Git and GitHub workflows

## Getting Started

1. **Install Extensions**: Ensure GitHub PR and Copilot extensions are installed
2. **Authenticate GitHub**: Sign in through VS Code's account management
3. **Start with Exercise 1**: Learn enhanced media support
4. **Progress through exercises**: Build expertise with notifications and AI integration
5. **Explore demos**: See complete workflows for team collaboration

## GitHub PR Extension Features

### Enhanced Media Support
- **Private Repository Images**: Secure rendering of images from private repos
- **Inline Comments**: Visual content appears directly in comment threads
- **Context Integration**: Design discussions integrated with code review
- **Automatic Permissions**: Seamless handling of private repository access

### Notification Management
- **Default Notifications View**: Collapsed by default for better workspace management
- **Priority Indicators**: Visual cues for urgent notifications
- **Batch Operations**: Manage multiple notifications simultaneously
- **Contextual Actions**: Quick responses directly from VS Code

### Copilot Integration
- **Agent Assignment**: "Assign to Copilot" action for automated assistance
- **Session Tracking**: Monitor Copilot's progress on assigned tasks
- **Timeline Integration**: Session controls and status in PR timeline
- **Automated Reviews**: AI-assisted code review and suggestions

### Link Handling
- **In-Editor Navigation**: PR and issue links open within VS Code
- **Context Preservation**: Maintain working context while exploring references
- **Cross-Reference Support**: Navigate between linked issues and PRs seamlessly

## Common Workflows

### Code Review
- **Visual Reviews**: Enhanced media support for design feedback
- **AI Assistance**: Copilot agent support for complex reviews
- **Notification Management**: Streamlined review request handling
- **Unified Interface**: Complete review workflow within VS Code

### Team Collaboration
- **Shared Standards**: Consistent PR templates and review processes
- **Automated Assistance**: Copilot integration for routine tasks
- **Efficient Communication**: Enhanced media and notification support
- **Seamless Navigation**: In-editor link handling for better workflow

### Project Management
- **Assignment Tracking**: Monitor AI agent progress and contributions
- **Priority Management**: Enhanced notification sorting and handling
- **Cross-Repository**: Unified experience across multiple projects
- **Documentation**: Integrated support for visual documentation and feedback

## Keyboard Shortcuts

### GitHub PR Extension
- **Open PR View**: `Ctrl+Shift+P` → "GitHub Pull Requests: Open PR"
- **Create PR**: `Ctrl+Shift+P` → "GitHub Pull Requests: Create PR"
- **Review Changes**: `Ctrl+Shift+P` → "GitHub Pull Requests: Review Changes"
- **Assign to Copilot**: Available in PR context menu

### Navigation
- **Focus PR View**: `Ctrl+Shift+G` → Select GitHub tab
- **Open Notifications**: `Ctrl+Shift+P` → "GitHub Pull Requests: Show Notifications"
- **Link Navigation**: `Ctrl+Click` on PR/issue links

### Copilot Integration
- **Chat with Copilot**: `Ctrl+Shift+I` → Access Copilot chat
- **Agent Assignment**: Context menu in PR view
- **Session Management**: Available in PR timeline

Happy collaborating with enhanced GitHub integration and AI assistance!
```

---

### github-pr-extension-kit/exercise-1-enhanced-media-support/instructions.md

```
# Exercise 1: Enhanced Media Support for Private Repositories

## Goal
Learn to use VS Code's enhanced media support for GitHub Pull Requests, including private repository image rendering and visual content integration in code reviews.

## Task
1. Set up GitHub PR extension with enhanced media support
2. Test private repository image rendering
3. Practice visual code review workflows
4. Configure media display settings

## Input/Output
**Starter**: Basic GitHub repository setup with sample media
**Expected Outcome**: Fully functional visual code review workflow with enhanced media support

## Steps

1. **Configure GitHub PR Extension**
    ```json
    {
        "githubPullRequests.pullBranch": "always",
        "githubPullRequests.defaultMergeMethod": "squash",
        "githubPullRequests.createOnPublishBranch": "always",
        "githubPullRequests.remotes": ["origin", "upstream"]
    }
    ```

- Ensure GitHub authentication is active
- Verify extension permissions for private repositories
- Test basic PR creation and viewing

2. **Test Private Repository Media**
   - Create a PR with image attachments in comments
   - Add screenshots, diagrams, or mockups to PR descriptions
   - Verify images render directly in VS Code PR view
   - Compare with browser experience

3. **Practice Visual Code Review**
   - Review PRs containing UI changes with screenshots
   - Add visual feedback using image comments
   - Use enhanced media for design discussions
   - Test inline image rendering in comment threads

4. **Optimize Media Display Settings**

    ```json
    {
        "githubPullRequests.showInlineComments": true,
        "githubPullRequests.fileListLayout": "tree",
        "githubPullRequests.focusedMode": false
    }
    ```

   - Configure optimal media rendering settings
   - Adjust comment display preferences
   - Test different layout configurations

## Tips

- Use descriptive filenames for uploaded images
- Test both public and private repository scenarios
- Verify image permissions and access rights
- Compare VS Code rendering with GitHub web interface
- Practice visual feedback workflows for better collaboration

```

---

### github-pr-extension-kit/exercise-1-enhanced-media-support/solution/.vscode/settings.json

```json
{
  // GitHub Pull Requests Configuration
  "githubPullRequests.pullBranch": "always",
  "githubPullRequests.defaultMergeMethod": "squash",
  "githubPullRequests.createOnPublishBranch": "always",
  "githubPullRequests.remotes": ["origin", "upstream"],
  
  // Enhanced Media Support
  "githubPullRequests.showInlineComments": true,
  "githubPullRequests.fileListLayout": "tree",
  "githubPullRequests.focusedMode": false,
  "githubPullRequests.terminalLinksHandler": true,
  
  // Visual Review Settings
  "githubPullRequests.commentInsertMode": "replace",
  "githubPullRequests.assignCreated": "never",
  "githubPullRequests.workingIssueFormatScm": "#${issueNumberLabel}",
  
  // Private Repository Support
  "githubPullRequests.queries": [
    {
      "label": "Waiting For My Review",
      "query": "is:open is:pr review-requested:@me archived:false"
    },
    {
      "label": "Assigned To Me",
      "query": "is:open is:pr assignee:@me archived:false"
    },
    {
      "label": "Created By Me",
      "query": "is:open is:pr author:@me archived:false"
    }
  ],
  
  // Notification Management
  "githubPullRequests.notifications": "all",
  "githubPullRequests.overrideDefaultBranch": false,
  
  // Media Display Optimization
  "editor.wordWrap": "on",
  "editor.rulers": [80, 120],
  "markdown.preview.fontSize": 14,
  "markdown.preview.lineHeight": 1.6,
  
  // GitHub Integration
  "git.openRepositoryInParentFolders": "always",
  "git.fetchOnPull": true,
  "git.autofetch": true,
  
  // File Explorer
  "explorer.confirmDelete": false,
  "explorer.confirmDragAndDrop": false,
  
  // Terminal Integration
  "terminal.integrated.defaultProfile.windows": "PowerShell",
  "terminal.integrated.copyOnSelection": true
}
```

---

### github-pr-extension-kit/exercise-2-notification-management/instructions.md

```
# Exercise 2: Notification Management and Priority Handling

## Goal
Master VS Code's improved notification management for GitHub Pull Requests, including priority indicators, batch operations, and streamlined workflow configuration.

## Task
1. Configure enhanced notification settings
2. Practice priority-based notification handling
3. Set up batch operation workflows
4. Optimize notification display and management

## Input/Output
**Starter**: Default notification configuration
**Expected Outcome**: Efficient notification management system with priority handling and batch operations

## Steps

1. **Configure Notification Settings**
    ```json
    {
        "githubPullRequests.notifications": "all",
        "githubPullRequests.queries": [
        {
            "label": "High Priority Reviews",
            "query": "is:open is:pr review-requested:@me label:priority-high"
        },
        {
            "label": "Team Reviews",
            "query": "is:open is:pr team-review-requested:@me"
        }
        ]
    }
    ```

- Set up custom notification queries
- Configure priority-based filtering
- Test notification view collapsed state

2. **Practice Priority Management**
   - Create PRs with different priority labels
   - Test priority indicator display
   - Practice urgent notification handling
   - Configure team-specific priority rules

3. **Implement Batch Operations**
   - Select multiple notifications
   - Practice batch review assignments
   - Test bulk notification actions
   - Configure automated batch processing

4. **Optimize Workflow Integration**
   - Integrate with daily review routines
   - Set up notification scheduling
   - Configure context switching minimization
   - Test cross-repository notification management

## Tips

- Use priority labels consistently across team projects
- Configure notification filters to reduce noise
- Practice batch operations for efficiency
- Set up notification grouping by project or team
- Use collapsed view to maintain workspace focus

```

---

### github-pr-extension-kit/demo-1-copilot-agent-integration/walkthrough.md

```

# Demo 1: Copilot Agent Integration Walkthrough

## Overview

This demo showcases how to use GitHub Copilot agent integration with the GitHub Pull Requests extension for automated assistance in code review and PR management.

## Scenario

You're working on a Python project and want to leverage Copilot agent for automated PR assistance, code review, and issue resolution.

## Setup

1. **Prerequisites**
   - GitHub Copilot subscription active
   - GitHub Pull Requests extension installed
   - Sample Python project opened
   - Active GitHub repository with PR access

2. **Initial Configuration**
   - Authenticate GitHub account in VS Code
   - Enable Copilot agent mode
   - Verify PR extension permissions

## Step-by-Step Walkthrough

### Step 1: Create a Feature Branch and PR

```bash
# Create and switch to feature branch
git checkout -b feature/new-calculator

# Make changes to main.py
# Add calculator functionality

# Commit changes
git add .
git commit -m "Add calculator functionality"

# Push branch
git push origin feature/new-calculator
```

### Step 2: Assign Copilot Agent to PR

1. **Open PR in VS Code**
   - Navigate to GitHub Pull Requests view
   - Open the created PR
   - View PR details and timeline

2. **Assign to Copilot**
   - Right-click on PR
   - Select "Assign to Copilot"
   - Monitor agent assignment in timeline

### Step 3: Monitor Copilot Session

1. **Session Tracking**
   - View "Start working" action in timeline
   - Monitor Copilot's progress indicators
   - Check session status updates

2. **Review Copilot Suggestions**
   - Examine code review comments from Copilot
   - Review suggested improvements
   - Apply relevant recommendations

### Step 4: Interact with Copilot Agent

1. **Chat Integration**

   ```
   @workspace Please review the calculator implementation for edge cases
   @workspace Suggest improvements for error handling
   @workspace Generate unit tests for the new functionality
   ```

2. **Session Management**
   - Use "Stop working" when needed
   - Resume sessions as required
   - Track overall progress

## Key Features Demonstrated

### Agent Assignment

- **Automatic Assignment**: Seamless Copilot integration
- **Session Tracking**: Real-time progress monitoring
- **Timeline Integration**: Visual session management

### AI-Assisted Review

- **Code Analysis**: Automated code quality assessment
- **Suggestion Generation**: Intelligent improvement recommendations
- **Test Generation**: Automated test case creation

### Workflow Integration

- **Unified Interface**: Complete workflow within VS Code
- **Context Preservation**: Maintain development focus
- **Collaboration**: Enhanced team productivity

## Expected Outcomes

- Copilot agent successfully assigned to PR
- Automated code review and suggestions provided
- Session tracking visible in PR timeline
- Improved code quality through AI assistance

## Tips for Success

- Use descriptive PR titles and descriptions for better AI context
- Review Copilot suggestions before applying changes
- Combine manual review with AI assistance for best results
- Leverage chat integration for specific questions and requests

This demo showcases the power of AI-assisted development workflows integrated directly into your VS Code environment.

```

---

### github-pr-extension-kit/demo-2-unified-pr-workflow/walkthrough.md

```

# Demo 2: Unified PR Workflow Walkthrough

## Overview

This demo demonstrates a complete pull request workflow using VS Code's enhanced GitHub integration, from feature development to merge, all within the editor environment.

## Scenario

You're implementing a new feature in a team project, using the enhanced PR workflow with improved notifications, link handling, and media support.

## Setup

1. **Team Project Setup**
   - Multi-contributor repository
   - Established PR templates and workflows
   - Configured notification preferences
   - Enhanced media support enabled

2. **Workflow Configuration**
   - PR templates configured
   - Automated checks enabled
   - Review requirements set
   - Notification preferences optimized

## Complete Workflow Steps

### Phase 1: Feature Development

1. **Create Feature Branch**

   ```bash
   git checkout -b feature/user-authentication
   ```

2. **Implement Feature**
   - Write code with VS Code IntelliSense
   - Use integrated testing
   - Document changes with screenshots

3. **Prepare for PR**
   - Add visual documentation
   - Include screenshots in commit messages
   - Prepare feature description

### Phase 2: PR Creation and Management

1. **Create PR from VS Code**
   - Use integrated PR creation
   - Auto-populate from templates
   - Add visual documentation

2. **Enhanced Media Integration**
   - Include UI mockups in PR description
   - Add before/after screenshots
   - Attach architecture diagrams

3. **Notification Management**
   - Configure reviewer notifications
   - Set priority indicators
   - Manage notification batching

### Phase 3: Review and Collaboration

1. **Review Process**
   - Receive notifications in VS Code
   - View PR with enhanced media support
   - Use in-editor link navigation

2. **Collaborative Feedback**
   - Visual feedback on UI changes
   - Inline comments with image support
   - Cross-reference related issues

3. **AI-Assisted Review**
   - Assign Copilot for code review
   - Get automated suggestions
   - Track AI session progress

### Phase 4: Resolution and Merge

1. **Address Feedback**
   - Implement suggested changes
   - Update visual documentation
   - Respond to review comments

2. **Final Approval**
   - Verify all checks pass
   - Confirm reviewer approval
   - Prepare for merge

3. **Merge and Cleanup**
   - Merge from VS Code interface
   - Clean up feature branch
   - Update project documentation

## Key Workflow Benefits

### Unified Experience

- **Single Environment**: Complete workflow in VS Code
- **Context Preservation**: No switching between tools
- **Integrated Tools**: All features accessible from editor

### Enhanced Collaboration

- **Visual Feedback**: Rich media support for better communication
- **Smart Notifications**: Priority-based notification management
- **AI Assistance**: Copilot integration for automated help

### Improved Productivity

- **Streamlined Process**: Reduced context switching
- **Better Organization**: Enhanced notification and link management
- **Team Efficiency**: Consistent workflows and standards

## Configuration Example

### PR Template Integration

```markdown
## Feature Description
Brief description of the feature

## Visual Changes
- [ ] Screenshots included
- [ ] UI mockups attached
- [ ] Before/after comparisons

## Testing
- [ ] Unit tests added
- [ ] Integration tests pass
- [ ] Manual testing completed

## Review Checklist
- [ ] Code follows team standards
- [ ] Documentation updated
- [ ] Visual assets included
```

### Notification Settings

```json
{
  "githubPullRequests.notifications": "all",
  "githubPullRequests.queries": [
    {
      "label": "High Priority Reviews",
      "query": "is:open is:pr review-requested:@me label:priority-high"
    },
    {
      "label": "Ready for Review",
      "query": "is:open is:pr assignee:@me -label:work-in-progress"
    }
  ]
}
```

This unified workflow demonstrates how VS Code's enhanced GitHub integration creates a seamless development experience from code creation to deployment.

```

This resource kit focuses on the core GitHub Pull Requests extension enhancements with:

✅ **2 Focused Exercises** - Enhanced media support and notification management
✅ **2 Practical Demos** - Copilot agent integration and unified workflow
✅ **Simplified Structure** - Reduced complexity while maintaining comprehensiveness
✅ **Essential Features** - Private repository images, notifications, Copilot integration, link handling

The resource kit provides hands-on experience with the key improvements while keeping the scope manageable and focused on practical workflows.

Ready to continue with the next major feature! What would you like me to work on next?
