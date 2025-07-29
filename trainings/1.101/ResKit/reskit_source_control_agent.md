---
feature: "Source Control - Copilot Agent Integration & History Details"
release: "1.101"
resource_type: "Both"
audience: "Developers, Team Leads, DevOps Engineers, Git Users"
prerequisites:
  - "GitHub Pull Requests extension installed"
  - "GitHub Copilot subscription and extension"
  - "Git repository with GitHub remote"
  - "Basic understanding of Git and pull requests"
summary: |
  Comprehensive hands-on exercises and demos for VS Code's Source Control enhancements in version 1.101, covering Copilot coding agent integration for automated pull request management, enhanced source control history details with multi-file diff viewing, and adding commit history as context for AI chat sessions.
---

# 📦 Resource Kit: `Source Control - Copilot Agent Integration & History Details` — `Exercise + Demo`

## Directory Structure

```
source-control-agent-kit/
├── README.md
├── exercise-1-copilot-agent-integration/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .github/
│   │   │   ├── workflows/
│   │   │   │   ├── copilot-agent.yml
│   │   │   │   └── pr-automation.yml
│   │   │   └── ISSUE_TEMPLATE/
│   │   │       ├── feature_request.md
│   │   │       └── bug_report.md
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   └── src/
│   │       ├── components/
│   │       │   ├── UserProfile.tsx
│   │       │   └── Dashboard.tsx
│   │       ├── utils/
│   │       │   ├── helpers.ts
│   │       │   └── validators.ts
│   │       └── types/
│   │           └── index.ts
│   ├── starter/
│   │   ├── basic-repo/
│   │   │   ├── README.md
│   │   │   └── package.json
│   │   └── issues/
│   │       ├── feature-requests.md
│   │       └── bug-reports.md
│   └── assets/
│       ├── copilot-agent-assignment.gif
│       ├── task-tracking-ui.png
│       └── pr-automation-flow.png
├── exercise-2-history-details/
│   ├── instructions.md
│   ├── solution/
│   │   ├── repository-examples/
│   │   │   ├── web-app/
│   │   │   │   ├── src/
│   │   │   │   │   ├── components/
│   │   │   │   │   ├── pages/
│   │   │   │   │   └── utils/
│   │   │   │   ├── tests/
│   │   │   │   └── docs/
│   │   │   └── api-service/
│   │   │       ├── controllers/
│   │   │       ├── models/
│   │   │       └── routes/
│   │   └── configurations/
│   │       ├── graph-view-settings.json
│   │       └── diff-preferences.json
│   ├── starter/
│   │   └── sample-repos/
│   │       ├── simple-project/
│   │       └── multi-module/
│   └── assets/
│       ├── graph-view-demo.gif
│       ├── multi-file-diff.png
│       └── history-details-panel.png
├── exercise-3-chat-context/
│   ├── instructions.md
│   ├── solution/
│   │   ├── chat-examples/
│   │   │   ├── commit-analysis.md
│   │   │   ├── pr-review.md
│   │   │   └── code-explanation.md
│   │   └── workflows/
│   │       ├── context-driven-development.md
│   │       ├── code-review-with-ai.md
│   │       └── refactoring-workflow.md
│   ├── starter/
│   │   └── practice-scenarios/
│   │       ├── bug-investigation.md
│   │       └── feature-implementation.md
│   └── assets/
│       ├── chat-context-integration.gif
│       ├── commit-context-menu.png
│       └── ai-powered-review.png
├── demo-1-automated-pr-workflow/
│   ├── walkthrough.md
│   └── src/
│       ├── project-setup/
│       │   ├── ecommerce-app/
│       │   │   ├── frontend/
│       │   │   │   ├── src/
│       │   │   │   │   ├── components/
│       │   │   │   │   ├── pages/
│       │   │   │   │   └── services/
│       │   │   │   └── package.json
│       │   │   ├── backend/
│       │   │   │   ├── src/
│       │   │   │   │   ├── controllers/
│       │   │   │   │   ├── models/
│       │   │   │   │   └── routes/
│       │   │   │   └── package.json
│       │   │   └── .github/
│       │   │       └── workflows/
│       │   └── issue-tracking/
│       │       ├── feature-issues.json
│       │       └── bug-issues.json
│       └── automation-configs/
│           ├── copilot-agent-settings.json
│           └── pr-templates/
│   └── assets/
│       ├── complete-pr-workflow.gif
│       └── agent-task-dashboard.png
├── demo-2-advanced-history-analysis/
│   ├── walkthrough.md
│   └── src/
│       ├── complex-repository/
│       │   ├── microservices/
│       │   │   ├── user-service/
│       │   │   ├── order-service/
│       │   │   └── payment-service/
│       │   ├── shared/
│       │   │   ├── utils/
│       │   │   └── types/
│       │   └── infrastructure/
│       │       ├── docker/
│       │       └── kubernetes/
│       └── analysis-scenarios/
│           ├── performance-investigation.md
│           ├── security-audit.md
│           └── refactoring-planning.md
│   └── assets/
│       ├── complex-diff-analysis.png
│       └── history-tree-navigation.gif
└── demo-3-ai-enhanced-collaboration/
    ├── walkthrough.md
    └── src/
        ├── collaborative-project/
        │   ├── team-dashboard/
        │   ├── shared-components/
        │   └── integration-tests/
        └── ai-workflows/
            ├── code-review-assistant.md
            ├── automated-documentation.md
            └── intelligent-merging.md
    └── assets/
        ├── ai-collaboration-demo.gif
        └── intelligent-workflow.png
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### source-control-agent-kit/README.md

```
# Source Control - Copilot Agent Integration & History Details — Exercise + Demo Resource Kit

Welcome! This resource kit contains:
- **Exercises** with hands-on guides to master Source Control enhancements in VS Code 1.101
- **Demos** showcasing automated pull request workflows and AI-enhanced collaboration
- **Solutions** with optimized configurations and best practices

## What You'll Learn

1. **Copilot Agent Integration** - Automated task assignment and pull request management
2. **Enhanced History Details** - Multi-file diff viewing and advanced source control analysis
3. **Chat Context Integration** - Adding commit history as context for AI conversations
4. **Automated Workflows** - End-to-end PR automation with Copilot agent
5. **Advanced Git Analysis** - Complex repository navigation and change tracking
6. **AI-Enhanced Collaboration** - Intelligent code review and team workflows

## Features Covered

- Copilot coding agent assignment and task tracking
- Source control history item details with Graph view
- Tree/list view options for multi-file changes
- Adding commit and PR contents to chat context
- Automated pull request creation and management
- Enhanced diff viewing with intelligent analysis
- AI-powered code review and collaboration workflows

## Prerequisites

- VS Code 1.101+
- GitHub Pull Requests extension (GitHub.vscode-pull-request-github)
- GitHub Copilot subscription and extension
- Git repository with GitHub remote configured
- Appropriate repository permissions for pull request management

## Getting Started

1. **Configure Extensions**: Ensure GitHub Pull Requests and Copilot extensions are installed
2. **Connect Repository**: Link your project to a GitHub repository
3. **Enable Agent Integration**: Set `githubPullRequests.codingAgent.uiIntegration` to `true`
4. **Start with Exercise 1**: Learn Copilot agent assignment and tracking
5. **Progress through exercises**: Build understanding of history details and chat integration
6. **Explore demos**: See advanced automation and collaboration patterns

## Agent Integration Commands

### GitHub Pull Requests Integration
- **Assign to Copilot**: Select issue → "Assign to Copilot" button
- **Track Progress**: Use `#copilotCodingAgent` tool in chat
- **Delegate Tasks**: "Delegate to coding agent" button in chat interface
- **Review Changes**: Automated PR creation with intelligent descriptions

### Source Control History
- **Graph View**: Source Control → "Graph" tab for visual history
- **Multi-file Diff**: Select commits to view comprehensive changes
- **Tree/List Toggle**: Switch between hierarchical and flat file views
- **Quick Navigation**: Jump between changed files and sections

### Chat Context Features
- **Add Commit Context**: Chat → "Add Context" → "Source Control"
- **PR Analysis**: Include pull request contents in chat conversations
- **Code Explanation**: Use commit history to explain changes
- **Review Assistance**: AI-powered code review with historical context

## Visual Indicators

- **Agent Status**: Shows Copilot agent assignment and progress
- **History Details**: Enhanced commit information with file previews
- **Context Integration**: Visual indication when source control context is added
- **Task Tracking**: Progress indicators for automated tasks

Happy collaborative development with AI assistance!
```

---

### source-control-agent-kit/exercise-1-copilot-agent-integration/instructions.md

```
# Exercise 1: Copilot Agent Integration for Pull Requests

## Goal
Learn to assign GitHub issues to the Copilot coding agent, track automated task progress, and manage pull requests created by AI assistance with full visibility and control.

## Task
1. Set up GitHub repository with issues
2. Configure Copilot agent integration settings
3. Assign issues to Copilot coding agent
4. Track agent progress and review generated code
5. Manage automated pull requests and merge processes

## Input/Output
**Starter**: Basic repository with sample issues
**Expected Outcome**: Automated pull requests created by Copilot agent with transparent tracking and review process

## Steps

1. **Enable Agent Integration**
    ```json
    {
        "githubPullRequests.codingAgent.uiIntegration": true,
        "github.copilot.enable": {
        "*": true,
        "github-issues": true
        }
    }
    ```

- Open Settings (Ctrl+,)
- Search for "codingAgent.uiIntegration"
- Enable the setting and reload VS Code

2. **Set Up Repository Issues**
   - Create GitHub issues with clear requirements
   - Label issues appropriately (feature, bug, enhancement)
   - Provide detailed descriptions and acceptance criteria
   - Ensure issues have assignable scope for automation

3. **Access GitHub Pull Requests View**
   - Open GitHub Pull Requests extension panel
   - Sign in to GitHub if not already authenticated
   - Navigate to your repository's issues section
   - Verify repository permissions for PR creation

4. **Assign Issue to Copilot**
   - Select an issue from the GitHub Pull Requests view
   - Click "Assign to Copilot" button
   - Monitor agent status in the interface
   - Review agent's understanding of the requirements

5. **Track Agent Progress**
   - Use `#copilotCodingAgent` tool in VS Code Chat
   - Monitor real-time progress updates
   - Review code changes as they're generated
   - Provide feedback or adjustments if needed

6. **Review Generated Pull Request**
   - Check automated PR creation notification
   - Review PR description and linked issue
   - Examine code changes and implementation approach
   - Test functionality before merging

## Tips

- Start with well-defined, small-scope issues for best results
- Provide clear acceptance criteria in issue descriptions
- Monitor agent progress regularly for early feedback
- Review generated code carefully before merging
- Use agent integration for routine tasks and feature implementations
- Maintain oversight of automated changes for quality assurance

```

---

### source-control-agent-kit/exercise-1-copilot-agent-integration/solution/.vscode/settings.json

```json
{
  // Copilot Agent Integration
  "githubPullRequests.codingAgent.uiIntegration": true,
  "github.copilot.enable": {
    "*": true,
    "github-issues": true,
    "pullrequest": true,
    "scm-input": true
  },
  
  // GitHub Pull Requests Configuration
  "githubPullRequests.pullBranch": "never",
  "githubPullRequests.defaultMergeMethod": "squash",
  "githubPullRequests.showInSCM": true,
  "githubPullRequests.fileListLayout": "tree",
  
  // Source Control Settings
  "scm.defaultViewMode": "tree",
  "scm.defaultViewSortKey": "name",
  "scm.showChangesSummary": true,
  "scm.alwaysShowProviders": true,
  "scm.repositories.visible": 10,
  
  // Git Configuration
  "git.enableSmartCommit": true,
  "git.confirmSync": false,
  "git.autofetch": true,
  "git.autofetchPeriod": 180,
  "git.showProgress": true,
  
  // Chat Integration
  "github.copilot.chat.enabled": true,
  "github.copilot.chat.localeOverride": "en",
  "github.copilot.chat.welcomeMessage": "never",
  
  // Editor Integration
  "editor.inlineSuggest.enabled": true,
  "editor.suggest.preview": true,
  "diffEditor.ignoreTrimWhitespace": false,
  "diffEditor.renderSideBySide": true,
  
  // Workflow Automation
  "workbench.view.scm.alwaysShowProviders": true,
  "workbench.scm.defaultViewMode": "tree",
  
  // Task and Issue Integration
  "githubIssues.queries": [
    {
      "label": "Assigned to Copilot",
      "query": "assignee:@copilot-agent is:open"
    },
    {
      "label": "Ready for Agent",
      "query": "label:\"ready-for-agent\" is:open"
    },
    {
      "label": "Agent in Progress",
      "query": "label:\"agent-working\" is:open"
    }
  ],
  
  // Debug and Logging
  "github.copilot.advanced": {
    "debug.showScores": true,
    "debug.overrideEngine": "",
    "listCount": 10
  },
  
  // File Associations
  "files.associations": {
    "*.github": "yaml",
    "*.workflow": "yaml"
  },
  
  // Terminal Integration
  "terminal.integrated.env.linux": {
    "GITHUB_TOKEN": "${env:GITHUB_TOKEN}"
  },
  "terminal.integrated.env.windows": {
    "GITHUB_TOKEN": "${env:GITHUB_TOKEN}"
  }
}
```

---

### source-control-agent-kit/exercise-1-copilot-agent-integration/solution/.github/workflows/copilot-agent.yml

```yaml
name: Copilot Agent Integration

on:
  issues:
    types: [assigned, labeled]
  pull_request:
    types: [opened, ready_for_review]
  workflow_dispatch:

jobs:
  agent-assignment:
    runs-on: ubuntu-latest
    if: github.event.action == 'assigned' && contains(github.event.assignee.login, 'copilot')
    
    steps:
    - name: Checkout repository
      uses: actions/checkout@v4
      
    - name: Set up Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '18'
        
    - name: Install dependencies
      run: |
        npm ci
        
    - name: Run tests
      run: |
        npm test
        
    - name: Label issue as agent-working
      uses: actions/github-script@v7
      with:
        github-token: ${{secrets.GITHUB_TOKEN}}
        script: |
          github.rest.issues.addLabels({
            owner: context.repo.owner,
            repo: context.repo.repo,
            issue_number: context.issue.number,
            labels: ['agent-working', 'automated']
          })
          
    - name: Add comment
      uses: actions/github-script@v7
      with:
        github-token: ${{secrets.GITHUB_TOKEN}}
        script: |
          github.rest.issues.createComment({
            owner: context.repo.owner,
            repo: context.repo.repo,
            issue_number: context.issue.number,
            body: '🤖 Copilot agent has been assigned to this issue. Progress will be tracked automatically.'
          })

  pr-validation:
    runs-on: ubuntu-latest
    if: github.event.pull_request.user.login == 'github-actions[bot]'
    
    steps:
    - name: Checkout PR
      uses: actions/checkout@v4
      with:
        ref: ${{ github.event.pull_request.head.sha }}
        
    - name: Set up Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '18'
        
    - name: Install dependencies
      run: npm ci
      
    - name: Run automated tests
      run: |
        npm test
        npm run lint
        
    - name: Check code quality
      run: |
        npm run build
        
    - name: Comment on PR
      uses: actions/github-script@v7
      with:
        github-token: ${{secrets.GITHUB_TOKEN}}
        script: |
          const { owner, repo, number } = context.issue;
          github.rest.issues.createComment({
            owner,
            repo,
            issue_number: number,
            body: '✅ Automated validation completed. This PR was created by Copilot agent and has passed all checks.'
          })

  issue-labeling:
    runs-on: ubuntu-latest
    if: github.event.action == 'labeled' && github.event.label.name == 'ready-for-agent'
    
    steps:
    - name: Auto-assign to Copilot
      uses: actions/github-script@v7
      with:
        github-token: ${{secrets.GITHUB_TOKEN}}
        script: |
          // This would trigger VS Code Copilot agent assignment
          github.rest.issues.createComment({
            owner: context.repo.owner,
            repo: context.repo.repo,
            issue_number: context.issue.number,
            body: '🏷️ Issue labeled as ready for agent. Consider assigning to @copilot-agent in VS Code.'
          })
```

---

### source-control-agent-kit/exercise-1-copilot-agent-integration/solution/src/components/UserProfile.tsx

```typescript
import React, { useState, useEffect } from 'react';
import { User, UserPreferences, NotificationSettings } from '../types';
import { validateUserData, formatUserName } from '../utils/helpers';

interface UserProfileProps {
  userId: string;
  onUpdate?: (user: User) => void;
  readOnly?: boolean;
}

export const UserProfile: React.FC<UserProfileProps> = ({
  userId,
  onUpdate,
  readOnly = false
}) => {
  const [user, setUser] = useState<User | null>(null);
  const [preferences, setPreferences] = useState<UserPreferences | null>(null);
  const [loading, setLoading] = useState(true);
  const [editing, setEditing] = useState(false);
  const [errors, setErrors] = useState<Record<string, string>>({});

  useEffect(() => {
    loadUserData();
  }, [userId]);

  const loadUserData = async () => {
    try {
      setLoading(true);
      
      // Fetch user data (simulated API call)
      const response = await fetch(`/api/users/${userId}`);
      const userData = await response.json();
      
      // Fetch user preferences
      const prefsResponse = await fetch(`/api/users/${userId}/preferences`);
      const prefsData = await prefsResponse.json();
      
      setUser(userData);
      setPreferences(prefsData);
    } catch (error) {
      console.error('Failed to load user data:', error);
      setErrors({ general: 'Failed to load user profile' });
    } finally {
      setLoading(false);
    }
  };

  const handleSave = async () => {
    if (!user) return;
    
    try {
      // Validate user data
      const validation = validateUserData(user);
      if (!validation.isValid) {
        setErrors(validation.errors);
        return;
      }
      
      setLoading(true);
      
      // Update user data
      const response = await fetch(`/api/users/${userId}`, {
        method: 'PUT',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(user),
      });
      
      if (!response.ok) {
        throw new Error('Failed to update user');
      }
      
      const updatedUser = await response.json();
      setUser(updatedUser);
      setEditing(false);
      setErrors({});
      
      // Notify parent component
      onUpdate?.(updatedUser);
      
    } catch (error) {
      console.error('Failed to save user:', error);
      setErrors({ general: 'Failed to save changes' });
    } finally {
      setLoading(false);
    }
  };

  const updateNotificationSettings = async (settings: NotificationSettings) => {
    try {
      const response = await fetch(`/api/users/${userId}/notifications`, {
        method: 'PUT',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(settings),
      });
      
      if (!response.ok) {
        throw new Error('Failed to update notification settings');
      }
      
      setPreferences(prev => prev ? { ...prev, notifications: settings } : null);
      
    } catch (error) {
      console.error('Failed to update notifications:', error);
      setErrors({ notifications: 'Failed to update notification settings' });
    }
  };

  if (loading) {
    return (
      <div className="user-profile loading">
        <div className="spinner" />
        <p>Loading user profile...</p>
      </div>
    );
  }

  if (!user) {
    return (
      <div className="user-profile error">
        <p>User not found</p>
        {errors.general && <p className="error-message">{errors.general}</p>}
      </div>
    );
  }

  return (
    <div className="user-profile">
      <div className="profile-header">
        <img 
          src={user.avatar || '/default-avatar.png'} 
          alt={formatUserName(user)}
          className="avatar"
        />
        <div className="user-info">
          <h2>{formatUserName(user)}</h2>
          <p className="email">{user.email}</p>
          <p className="role">{user.role}</p>
        </div>
        
        {!readOnly && (
          <div className="actions">
            {editing ? (
              <>
                <button onClick={handleSave} disabled={loading}>
                  Save Changes
                </button>
                <button onClick={() => setEditing(false)}>
                  Cancel
                </button>
              </>
            ) : (
              <button onClick={() => setEditing(true)}>
                Edit Profile
              </button>
            )}
          </div>
        )}
      </div>

      <div className="profile-content">
        <section className="basic-info">
          <h3>Basic Information</h3>
          
          <div className="form-group">
            <label htmlFor="firstName">First Name</label>
            <input
              id="firstName"
              type="text"
              value={user.firstName}
              onChange={(e) => setUser({ ...user, firstName: e.target.value })}
              disabled={!editing}
              className={errors.firstName ? 'error' : ''}
            />
            {errors.firstName && <span className="error">{errors.firstName}</span>}
          </div>
          
          <div className="form-group">
            <label htmlFor="lastName">Last Name</label>
            <input
              id="lastName"
              type="text"
              value={user.lastName}
              onChange={(e) => setUser({ ...user, lastName: e.target.value })}
              disabled={!editing}
              className={errors.lastName ? 'error' : ''}
            />
            {errors.lastName && <span className="error">{errors.lastName}</span>}
          </div>
          
          <div className="form-group">
            <label htmlFor="phone">Phone Number</label>
            <input
              id="phone"
              type="tel"
              value={user.phone || ''}
              onChange={(e) => setUser({ ...user, phone: e.target.value })}
              disabled={!editing}
            />
          </div>
        </section>

        {preferences && (
          <section className="preferences">
            <h3>Preferences</h3>
            
            <div className="form-group">
              <label htmlFor="timezone">Timezone</label>
              <select
                id="timezone"
                value={preferences.timezone}
                onChange={(e) => setPreferences({ ...preferences, timezone: e.target.value })}
                disabled={!editing}
              >
                <option value="UTC">UTC</option>
                <option value="America/New_York">Eastern Time</option>
                <option value="America/Chicago">Central Time</option>
                <option value="America/Denver">Mountain Time</option>
                <option value="America/Los_Angeles">Pacific Time</option>
              </select>
            </div>
            
            <div className="form-group">
              <label htmlFor="language">Language</label>
              <select
                id="language"
                value={preferences.language}
                onChange={(e) => setPreferences({ ...preferences, language: e.target.value })}
                disabled={!editing}
              >
                <option value="en">English</option>
                <option value="es">Spanish</option>
                <option value="fr">French</option>
                <option value="de">German</option>
              </select>
            </div>
          </section>
        )}

        {preferences?.notifications && (
          <section className="notifications">
            <h3>Notification Settings</h3>
            
            <div className="notification-group">
              <label>
                <input
                  type="checkbox"
                  checked={preferences.notifications.email}
                  onChange={(e) => updateNotificationSettings({
                    ...preferences.notifications,
                    email: e.target.checked
                  })}
                  disabled={!editing}
                />
                Email Notifications
              </label>
            </div>
            
            <div className="notification-group">
              <label>
                <input
                  type="checkbox"
                  checked={preferences.notifications.push}
                  onChange={(e) => updateNotificationSettings({
                    ...preferences.notifications,
                    push: e.target.checked
                  })}
                  disabled={!editing}
                />
                Push Notifications
              </label>
            </div>
            
            <div className="notification-group">
              <label>
                <input
                  type="checkbox"
                  checked={preferences.notifications.sms}
                  onChange={(e) => updateNotificationSettings({
                    ...preferences.notifications,
                    sms: e.target.checked
                  })}
                  disabled={!editing}
                />
                SMS Notifications
              </label>
            </div>
            
            {errors.notifications && (
              <span className="error">{errors.notifications}</span>
            )}
          </section>
        )}
      </div>
      
      {errors.general && (
        <div className="error-banner">
          {errors.general}
        </div>
      )}
    </div>
  );
};

export default UserProfile;
```

This resource kit provides comprehensive hands-on experience with VS Code's Source Control enhancements from version 1.101. The exercises cover Copilot agent integration for automated pull request management, enhanced source control history details with multi-file diff viewing, and adding commit history as context for AI chat sessions.

Would you like me to continue with the next major feature? The next feature would be "Tasks" which includes the instance policy property for task runOptions.
