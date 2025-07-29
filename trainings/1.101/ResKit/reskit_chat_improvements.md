---
feature: "Chat Improvements"
release: "1.101"
resource_type: "Both"
audience: "All Users, Developers, Power Users customizing AI workflows"
prerequisites:
  - "Basic understanding of VS Code Chat functionality"
  - "Familiarity with GitHub Copilot or AI assistants"
  - "Knowledge of JSON and Markdown file formats"
summary: |
  Comprehensive hands-on exercises and demos for VS Code's Chat Improvements in version 1.101, covering tool sets organization, custom chat modes creation, UX enhancements, diagnostic awareness, context management, and floating window workflows. Learn to customize and optimize AI chat interactions.
---

# 📦 Resource Kit: `Chat Improvements` — `Exercise + Demo`

## Directory Structure

```
chat-improvements-kit/
├── README.md
├── exercise-1-tool-sets/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── tool-sets.json
│   │   └── github-notifications/
│   │       ├── setup.md
│   │       └── examples.md
│   ├── starter/
│   │   └── tool-sets-template.json
│   └── assets/
│       ├── gh-news-screenshot.png
│       └── tool-set-picker.png
├── exercise-2-custom-chat-modes/
│   ├── instructions.md
│   ├── solution/
│   │   ├── planning.chatprompt.md
│   │   ├── code-review.chatprompt.md
│   │   └── documentation.chatprompt.md
│   ├── starter/
│   │   └── custom-mode-template.md
│   └── assets/
│       ├── custom-mode-dropdown.png
│       └── planning-mode-example.png
├── exercise-3-ux-improvements/
│   ├── instructions.md
│   ├── solution/
│   │   ├── keyboard-shortcuts.md
│   │   └── workflow-examples.md
│   ├── starter/
│   │   └── practice-prompts.md
│   └── assets/
│       ├── undo-edits-demo.gif
│       └── attachment-navigation.png
├── demo-1-diagnostic-awareness/
│   ├── walkthrough.md
│   └── src/
│       ├── buggy-project/
│       │   ├── package.json
│       │   ├── src/
│       │   │   ├── main.js
│       │   │   └── utils.js
│       │   └── .vscode/
│       │       └── tasks.json
│       └── examples/
│           └── diagnostic-scenarios.md
│   └── assets/
│       └── task-error-chat.png
├── demo-2-floating-windows/
│   ├── walkthrough.md
│   └── src/
│       ├── multi-chat-setup/
│       │   ├── project-a/
│       │   │   └── README.md
│       │   └── project-b/
│       │       └── README.md
│       └── workflows/
│           └── floating-window-usage.md
│   └── assets/
│       ├── floating-chat-dock.png
│       └── new-chat-button.png
└── demo-3-context-management/
    ├── walkthrough.md
    └── src/
        ├── context-examples/
        │   ├── large-file.js
        │   ├── config.json
        │   └── documentation.md
        └── workflows/
            ├── implicit-context-flow.md
            └── terminal-cwd-examples.md
    └── assets/
        ├── implicit-context-demo.gif
        └── terminal-context.png
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### chat-improvements-kit/README.md

```
# Chat Improvements — Exercise + Demo Resource Kit

Welcome! This resource kit contains:
- **Exercises** with hands-on guides to master Chat Improvements in VS Code 1.101
- **Demos** showcasing real-world workflows and advanced features
- **Solutions** with best practices and complete implementations

## What You'll Learn

1. **Tool Sets** - Organize and manage related tools for efficient workflows
2. **Custom Chat Modes** - Create specialized AI behavior for specific tasks
3. **UX Improvements** - Navigate and interact with enhanced chat interface
4. **Diagnostic Awareness** - Leverage AI understanding of errors and warnings
5. **Floating Windows** - Multi-chat workflows and window management
6. **Context Management** - Optimize context addition and terminal awareness

## Features Covered

- Tool sets creation and usage (#-mention syntax)
- Custom chat modes with YAML front matter
- Visual distinction between user/AI messages
- Undo functionality and keyboard shortcuts
- Implicit context suggestions
- Task diagnostic integration
- Terminal working directory awareness
- Floating window actions and workflows

## Prerequisites

- VS Code 1.101+
- GitHub Copilot or compatible AI assistant
- Basic understanding of JSON and Markdown
- Familiarity with VS Code Chat functionality

## Getting Started

1. Begin with `exercise-1-tool-sets`
2. Progress through exercises sequentially
3. Explore demos for advanced implementations
4. Use solutions as reference guides

Happy chatting!
```

---

### chat-improvements-kit/exercise-1-tool-sets/instructions.md

```
# Exercise 1: Creating and Using Tool Sets

## Goal
Learn to create tool sets for organizing related tools, use #-mention syntax to reference tool sets in chat, and configure tool sets for different workflows.

## Task
1. Create a tool sets configuration file
2. Define tool sets for GitHub notifications, file operations, and development tasks
3. Use tool sets in chat queries with #-mention syntax
4. Configure tool availability in different chat modes
5. Test tool set functionality in agent mode

## Input/Output
**Starter**: Template tool sets configuration
**Expected Outcome**: Working tool sets accessible via #-mention in chat with organized tool groupings

## Steps

1. **Create Tool Sets File**
   - Run Command Palette → `Configure Tool Sets` → `Create new tool sets file`
   - Use the provided template as starting point
   - Define at least 3 different tool sets

2. **Configure GitHub Notifications Tool Set**
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

3. **Test Tool Set Usage**
   - Open VS Code Chat
   - Use #-mention syntax: `#gh-news help me manage my notifications`
   - Verify tools are available and working
   - Test tool picker integration

4. **Create Additional Tool Sets**
   - File operations tool set
   - Development workflow tool set
   - Code review tool set

5. **Verify Integration**
   - Test in both agent mode and ask mode
   - Check tool availability in custom modes
   - Verify descriptions and icons display correctly

## Tips
- Tool sets appear in the tool picker with their icons
- Use descriptive names and clear descriptions
- Test tool sets with actual GitHub tokens for full functionality
- Tool sets can be referenced by name in natural language queries
```

---

### chat-improvements-kit/exercise-1-tool-sets/starter/tool-sets-template.json

```json
{
  "template-set": {
    "tools": [
      "tool1",
      "tool2",
      "tool3"
    ],
    "description": "Description of what this tool set does",
    "icon": "icon-name"
  }
}
```

---

### chat-improvements-kit/exercise-1-tool-sets/solution/.vscode/tool-sets.json

```json
{
  "gh-news": {
    "tools": [
      "list_notifications",
      "dismiss_notification",
      "get_notification_details",
      "mark_read"
    ],
    "description": "Manage GitHub notifications efficiently",
    "icon": "github-project"
  },
  "file-ops": {
    "tools": [
      "readFile",
      "writeFile",
      "listDirectory",
      "createDirectory",
      "deleteFile"
    ],
    "description": "Core file system operations",
    "icon": "file-directory"
  },
  "dev-workflow": {
    "tools": [
      "runTask",
      "debugStart",
      "runTests",
      "buildProject",
      "lintCode"
    ],
    "description": "Development workflow automation",
    "icon": "tools"
  },
  "code-review": {
    "tools": [
      "findProblems",
      "suggestFixes",
      "checkStyle",
      "analyzeComplexity",
      "generateDocs"
    ],
    "description": "Code review and quality analysis",
    "icon": "checklist"
  },
  "web-research": {
    "tools": [
      "fetch",
      "searchCode",
      "browseResources",
      "extractContent"
    ],
    "description": "Web research and content gathering",
    "icon": "search"
  }
}
```

---

### chat-improvements-kit/exercise-1-tool-sets/solution/github-notifications/setup.md

```markdown
# GitHub Notifications Tool Set Setup

## Prerequisites

1. **GitHub Token**: Create a personal access token with `notifications` scope
2. **MCP Server**: Install GitHub MCP server
3. **Configuration**: Add to VS Code MCP configuration

## Installation Steps

### 1. Install GitHub MCP Server

```bash
npm install -g @github/github-mcp-server
```

### 2. Configure MCP Server

Add to `.vscode/mcp.json`:

```json
{
  "servers": {
    "github": {
      "command": "github-mcp-server",
      "env": {
        "GITHUB_TOKEN": "${env:GITHUB_TOKEN}"
      }
    }
  }
}
```

### 3. Set Environment Variable

```bash
# Windows (PowerShell)
$env:GITHUB_TOKEN="your_github_token_here"

# macOS/Linux
export GITHUB_TOKEN="your_github_token_here"
```

### 4. Restart VS Code

Restart VS Code to load the new MCP server configuration.

## Testing

1. Open VS Code Chat
2. Type: `#gh-news show me my unread notifications`
3. Verify the tool set is working and notifications are displayed

```

---

### chat-improvements-kit/exercise-1-tool-sets/solution/github-notifications/examples.md

```markdown
# GitHub Notifications Tool Set Examples

## Basic Usage

### List All Notifications
```

# gh-news show me all my notifications

```

### Filter Unread Notifications
```

# gh-news what are my unread notifications?

```

### Dismiss Specific Notification
```

# gh-news dismiss the notification about PR #123

```

### Get Notification Details
```

# gh-news give me details about the notification for microsoft/vscode issue #456

```

## Advanced Workflows

### Daily Notification Review
```

# gh-news help me review today's notifications and prioritize them

```

### Bulk Actions
```

# gh-news mark all notifications from dependabot as read

```

### Integration with Other Tools
```

# gh-news get my notifications and #file-ops save them to notifications.md

```

## Expected Responses

The tool set should provide:
- Structured list of notifications
- Ability to perform actions (dismiss, mark read)
- Links to relevant GitHub pages
- Summary of notification types and counts
```

---

## chat-improvements-kit/exercise-1-tool-sets/assets/gh-news-screenshot.png

```
Screenshot showing:
- Tool set selection in chat interface
- #gh-news being used in a query
- Notification list response from GitHub MCP server
- Tool icons and descriptions in the picker
```

---

### chat-improvements-kit/exercise-1-tool-sets/assets/tool-set-picker.png

```
Screenshot showing:
- Tool picker interface with multiple tool sets
- Icons and descriptions for each tool set
- Selection state and available tools within each set
```

---

### chat-improvements-kit/exercise-2-custom-chat-modes/instructions.md

```
# Exercise 2: Creating Custom Chat Modes

## Goal
Learn to create custom chat modes with specialized instructions and tool configurations for specific workflows like planning, code review, and documentation.

## Task
1. Create custom chat mode files using YAML front matter
2. Define specialized instructions for different use cases
3. Configure tool availability per chat mode
4. Test custom modes in the Chat view
5. Create workflows for planning, code review, and documentation

## Input/Output
**Starter**: Template custom mode file
**Expected Outcome**: Working custom chat modes selectable from dropdown with specialized AI behavior

## Steps

1. **Create Planning Mode**
   - Run Command Palette → `Chat: Configure Chat Modes`
   - Create `planning.chatprompt.md` with read-only tools
   - Define clear planning instructions
   - Test with feature planning scenarios

2. **Create Code Review Mode**
   - Create `code-review.chatprompt.md`
   - Configure tools for analysis and suggestions
   - Add review checklist instructions
   - Test with actual code files

3. **Create Documentation Mode**
   - Create `documentation.chatprompt.md`
   - Configure tools for reading and writing docs
   - Define documentation standards
   - Test with existing code documentation

4. **Test Mode Selection**
   - Open VS Code Chat
   - Select custom mode from dropdown
   - Verify tool availability changes
   - Test specialized behavior

5. **Workflow Integration**
   - Create workflows that utilize multiple modes
   - Test mode switching during conversations
   - Verify instructions are followed consistently

## Tips
- Use YAML front matter for metadata
- Be specific with instructions to guide AI behavior
- Limit tools to prevent unwanted actions
- Test with real-world scenarios
- Custom modes work with all AI assistants
```

---

### chat-improvements-kit/exercise-2-custom-chat-modes/starter/custom-mode-template.md

```markdown
---
description: Brief description of what this mode does
tools: ['tool1', 'tool2', 'tool3']
---
# Custom Mode Instructions

[Add your detailed instructions here for how the AI should behave in this mode]

## Key Guidelines
- 
- 
- 

## Available Tools
The following tools are available in this mode:
- tool1: Description
- tool2: Description
- tool3: Description

## Example Usage
[Provide examples of how this mode should be used]
```

---

### chat-improvements-kit/exercise-2-custom-chat-modes/solution/planning.chatprompt.md

```markdown
---
description: Generate implementation plans for new features or refactoring existing code without making changes
tools: ['codebase', 'fetch', 'findTestFiles', 'githubRepo', 'search', 'usages', 'readFile']
---
# Planning Mode Instructions

You are in planning mode. Your primary task is to generate comprehensive implementation plans for new features or refactoring existing code. **DO NOT make any code edits or file changes** - this is a read-only analysis and planning mode.

## Key Guidelines

- **Read-Only Analysis**: Use only read tools to analyze the codebase
- **Comprehensive Planning**: Create detailed, actionable implementation plans
- **Risk Assessment**: Identify potential challenges and dependencies
- **Resource Estimation**: Suggest time and complexity estimates
- **Testing Strategy**: Include testing approaches in your plans

## Planning Structure

Your implementation plans should include these sections:

### 1. Overview
Brief description of the feature or refactoring task and its business value.

### 2. Current State Analysis
Analysis of existing code, architecture, and relevant components.

### 3. Requirements
- Functional requirements
- Non-functional requirements (performance, security, etc.)
- Dependencies and constraints

### 4. Implementation Steps
Detailed, ordered list of implementation tasks including:
- Code changes required
- New files/modules to create
- Existing files to modify
- Database/configuration changes

### 5. Testing Strategy
- Unit tests required
- Integration tests
- End-to-end testing scenarios
- Performance testing considerations

### 6. Risk Assessment
- Technical risks and mitigation strategies
- Breaking changes and compatibility issues
- Rollback procedures

### 7. Timeline and Effort
- Estimated development time
- Complexity assessment
- Resource requirements

## Available Tools
- **codebase**: Search across the entire codebase for patterns
- **readFile**: Read specific files for detailed analysis
- **search**: Find specific code patterns or implementations
- **usages**: Understand how components are used
- **findTestFiles**: Locate existing tests
- **fetch**: Research external documentation or references
- **githubRepo**: Analyze repository structure and history

## Example Usage
"Plan the implementation of a user authentication system for this web application"
"Create a refactoring plan to migrate from REST to GraphQL API"
"Plan the addition of real-time features using WebSockets"
```

---

### chat-improvements-kit/exercise-2-custom-chat-modes/solution/code-review.chatprompt.md

```markdown
---
description: Perform comprehensive code reviews with focus on quality, security, and best practices
tools: ['codebase', 'readFile', 'search', 'usages', 'findTestFiles', 'problems', 'runTests']
---
# Code Review Mode Instructions

You are in code review mode. Your role is to perform thorough, constructive code reviews focusing on code quality, security, performance, maintainability, and adherence to best practices.

## Review Guidelines

- **Be Constructive**: Provide specific, actionable feedback
- **Focus on Quality**: Emphasize code readability, maintainability, and performance
- **Security First**: Identify potential security vulnerabilities
- **Test Coverage**: Ensure adequate testing is in place
- **Documentation**: Verify code is properly documented

## Review Checklist

### Code Quality
- [ ] Code follows established style guidelines
- [ ] Variable and function names are descriptive and meaningful
- [ ] Functions are focused and have single responsibilities
- [ ] Code complexity is reasonable and well-structured
- [ ] Proper error handling is implemented

### Security
- [ ] Input validation is present where needed
- [ ] No hardcoded secrets or credentials
- [ ] Proper authentication and authorization checks
- [ ] SQL injection and XSS protection in place
- [ ] Sensitive data is properly handled

### Performance
- [ ] Efficient algorithms and data structures used
- [ ] No obvious performance bottlenecks
- [ ] Proper resource management (memory, connections)
- [ ] Caching strategies where appropriate

### Testing
- [ ] Unit tests cover new functionality
- [ ] Edge cases are tested
- [ ] Integration tests for critical paths
- [ ] Test names clearly describe what is being tested

### Documentation
- [ ] Public APIs are documented
- [ ] Complex logic has explanatory comments
- [ ] README and setup instructions are current
- [ ] Breaking changes are clearly noted

## Review Structure

Provide your review in this format:

### Summary
High-level assessment of the changes and overall quality.

### Strengths
What was done well in this code.

### Issues Found
Categorized list of issues:
- **Critical**: Must fix before merge
- **Important**: Should fix before merge  
- **Minor**: Nice to have improvements
- **Suggestions**: Ideas for future improvements

### Security Considerations
Any security-related observations or concerns.

### Testing Assessment
Evaluation of test coverage and quality.

### Recommendations
Specific next steps and improvements.

## Available Tools
- **readFile**: Examine specific files in detail
- **search**: Find similar patterns or implementations
- **usages**: Understand component dependencies
- **findTestFiles**: Locate and review tests
- **problems**: Check for linting and compilation issues
- **runTests**: Execute tests to verify functionality
- **codebase**: Search for related code patterns

## Example Usage
"Review the authentication module changes in src/auth/"
"Check the new payment processing code for security issues"
"Evaluate the test coverage for the user management features"
```

---

### chat-improvements-kit/exercise-2-custom-chat-modes/solution/documentation.chatprompt.md

```markdown
---
description: Create and maintain comprehensive technical documentation with focus on clarity and completeness
tools: ['codebase', 'readFile', 'writeFile', 'search', 'usages', 'createFile', 'fetch']
---
# Documentation Mode Instructions

You are in documentation mode. Your role is to create, update, and maintain high-quality technical documentation that is clear, comprehensive, and user-friendly.

## Documentation Standards

- **Clarity**: Write in clear, concise language accessible to the target audience
- **Completeness**: Cover all necessary information without overwhelming detail
- **Accuracy**: Ensure all code examples and instructions are correct and current
- **Structure**: Use consistent formatting and logical organization
- **Examples**: Include practical examples and use cases

## Documentation Types

### API Documentation
- Complete endpoint descriptions
- Request/response examples
- Error codes and handling
- Authentication requirements
- Rate limiting information

### User Guides
- Step-by-step instructions
- Screenshots and diagrams where helpful
- Troubleshooting sections
- FAQ sections

### Developer Documentation
- Setup and installation instructions
- Architecture overviews
- Code examples and snippets
- Contributing guidelines
- Testing procedures

### README Files
- Project overview and purpose
- Installation instructions
- Basic usage examples
- Link to detailed documentation
- License and contribution information

## Documentation Structure

### For APIs
```markdown
# API Name

## Overview
Brief description of the API purpose and capabilities.

## Authentication
How to authenticate with the API.

## Endpoints

### GET /endpoint
Description of what this endpoint does.

**Parameters:**
- `param1` (string, required): Description
- `param2` (number, optional): Description

**Response:**
```json
{
  "example": "response"
}
```

**Error Codes:**

- 400: Bad Request - Invalid parameters
- 401: Unauthorized - Authentication failed

```

### For Features
```markdown
# Feature Name

## Overview
What the feature does and why it's useful.

## Prerequisites
What users need before using this feature.

## How to Use

### Step 1: Setup
Detailed setup instructions.

### Step 2: Configuration  
Configuration options and examples.

### Step 3: Usage
How to use the feature with examples.

## Troubleshooting
Common issues and solutions.

## Examples
Practical examples and use cases.
```

## Quality Guidelines

- **Test Examples**: All code examples should be tested and working
- **Update Regularly**: Keep documentation current with code changes
- **Cross-Reference**: Link related documentation sections
- **Version Control**: Document version-specific features and changes
- **Accessibility**: Use proper heading structure and alt text for images

## Available Tools

- **readFile**: Examine existing documentation and code
- **writeFile**: Create and update documentation files
- **createFile**: Create new documentation files
- **search**: Find existing documentation patterns
- **usages**: Understand how features are implemented
- **codebase**: Analyze code structure for documentation
- **fetch**: Research external documentation standards

## Example Usage

"Document the new payment API with complete examples"
"Create a user guide for the dashboard features"
"Update the README file with current installation instructions"
"Generate API documentation from the OpenAPI spec"

```

---

### chat-improvements-kit/exercise-2-custom-chat-modes/assets/custom-mode-dropdown.png

```

Screenshot showing:

- Chat mode dropdown with custom modes listed
- Built-in modes (Ask, Edit, Agent) plus custom modes
- Mode descriptions visible on hover
- Current selection highlighted

```

---

### chat-improvements-kit/exercise-2-custom-chat-modes/assets/planning-mode-example.png

```

Screenshot showing:

- Planning mode selected in chat interface
- Example planning output with structured sections
- Read-only tools visible in tool picker
- Planning mode instructions being followed

```

---

### chat-improvements-kit/exercise-3-ux-improvements/instructions.md

```

# Exercise 3: Chat UX Improvements

## Goal

Learn to use the enhanced chat user experience features including visual message distinction, undo functionality, attachment navigation, and keyboard shortcuts.

## Task

1. Explore the improved visual distinction between user and AI messages
2. Practice using the undo functionality with hover and keyboard shortcuts
3. Navigate attachments efficiently in the chat input
4. Use keyboard shortcuts for chat operations
5. Understand the new editing approaches and keybindings

## Input/Output

**Starter**: Practice prompts and scenarios
**Expected Outcome**: Proficient use of all new UX features with improved chat workflow efficiency

## Steps

1. **Visual Message Distinction**
   - Start multiple chat conversations
   - Observe user vs AI message styling
   - Practice identifying message types quickly
   - Test with various message lengths

2. **Undo Functionality**
   - Make several chat requests with file edits
   - Practice hover-to-undo on individual requests
   - Use `Ctrl+Shift+Z` keyboard shortcut
   - Test undoing partial conversation chains

3. **Attachment Navigation**
   - Add multiple file attachments to chat
   - Practice navigating between attachments
   - Test drag-and-drop functionality
   - Use keyboard navigation within attachments

4. **Edit Operation Modes**
   - Test both editing approaches:
     - Top-to-bottom file rewrite
     - Multiple smaller edits
   - Observe auto-save behavior changes
   - Practice new Keep/Undo keybindings

5. **Keyboard Shortcuts Mastery**

   ```
   Ctrl+Shift+Z - Undo chat edits
   Ctrl+K - Accept all changes in file
   Ctrl+Shift+K - Reject all changes in file
   Ctrl+Enter - Accept individual change
   Ctrl+Shift+Enter - Reject individual change
   ```

## Tips

- Practice the new keybindings until they become muscle memory
- Use undo frequently to experiment safely
- Pay attention to auto-save behavior during edits
- Attachments can be reordered by dragging
- Hover states provide additional action buttons

```

---

### chat-improvements-kit/exercise-3-ux-improvements/starter/practice-prompts.md

```markdown
# Practice Prompts for UX Improvements

## Message Distinction Practice

Try these prompts to see the visual distinction between user and AI messages:

1. "Explain how async/await works in JavaScript"
2. "Show me an example of a React component"
3. "What are the benefits of TypeScript?"
4. "Help me debug this function: [paste code]"

## Undo Functionality Practice

Use these prompts that create editable changes:

1. "Add error handling to this function"
2. "Refactor this code to use modern ES6 syntax"
3. "Add JSDoc comments to these functions"
4. "Convert this callback to use promises"

Practice undoing these changes using:
- Hover and click X button
- Keyboard shortcut (Ctrl+Shift+Z)

## Attachment Navigation Practice

Create scenarios with multiple attachments:

1. Add 3-4 different code files
2. Add configuration files (package.json, tsconfig.json)
3. Add documentation files (README.md, docs)
4. Practice navigating between them efficiently

## Keyboard Shortcuts Practice

Test these scenarios:

1. Make edits and accept all changes (Ctrl+K)
2. Make edits and reject all changes (Ctrl+Shift+K)
3. Accept individual changes (Ctrl+Enter)
4. Reject individual changes (Ctrl+Shift+Enter)
```

---

### chat-improvements-kit/exercise-3-ux-improvements/solution/keyboard-shortcuts.md

```markdown
# Chat UX Keyboard Shortcuts Reference

## Primary Shortcuts

| Action | Shortcut | Description |
|--------|----------|-------------|
| Undo Chat Edits | `Ctrl+Shift+Z` | Undo the last chat request and all following requests |
| Accept All Changes | `Ctrl+K` | Accept all changes in the current file |
| Reject All Changes | `Ctrl+Shift+K` | Reject all changes in the current file |
| Accept Individual Change | `Ctrl+Enter` | Accept the current hunk/change |
| Reject Individual Change | `Ctrl+Shift+Enter` | Reject the current hunk/change |

## Context-Specific Shortcuts

### Chat Input
| Action | Shortcut | Description |
|--------|----------|-------------|
| Add Current File Context | `Shift+Tab, Enter` | Quickly add current file as context |
| Navigate Attachments | `Tab` / `Shift+Tab` | Move between attached files |
| Submit Query | `Ctrl+Enter` | Send the chat message |

### During Edits
| Action | Shortcut | Description |
|--------|----------|-------------|
| Navigate Changes | `F8` / `Shift+F8` | Jump between edit hunks |
| Toggle Diff View | `Ctrl+Shift+D` | Switch between diff and full view |
| Focus Editor | `Escape` | Return focus to main editor |

## Workflow Tips

### Efficient Editing Workflow
1. Make chat request for changes
2. Review changes in diff view (`Ctrl+Shift+D`)
3. Navigate between hunks (`F8`)
4. Accept/reject individual changes (`Ctrl+Enter`/`Ctrl+Shift+Enter`)
5. Or accept/reject all (`Ctrl+K`/`Ctrl+Shift+K`)

### Safe Experimentation
1. Make experimental chat request
2. Review results
3. If unsatisfied, use `Ctrl+Shift+Z` to undo
4. Try alternative approach

### Context Management
1. Use `Shift+Tab, Enter` to quickly add current file
2. Navigate attachments with `Tab`
3. Remove unwanted attachments before submitting

## Accessibility Features

- All actions have keyboard equivalents
- Screen reader support for message distinction
- High contrast mode compatible
- Consistent focus management throughout chat interface
```

---

### chat-improvements-kit/exercise-3-ux-improvements/solution/workflow-examples.md

```markdown
# UX Improvements Workflow Examples

## Example 1: Code Refactoring with Undo

### Scenario
Refactoring a JavaScript function to use modern syntax.

### Workflow
1. **Initial Request**: "Refactor this function to use arrow syntax and destructuring"
2. **Review Changes**: Examine the proposed edits in diff view
3. **Partial Accept**: Accept the arrow function change (`Ctrl+Enter`)
4. **Reject Destructuring**: Reject destructuring change (`Ctrl+Shift+Enter`)
5. **Undo if Needed**: If not satisfied, use `Ctrl+Shift+Z` to start over

### Benefits
- Granular control over changes
- Safe experimentation
- Quick recovery from unwanted edits

## Example 2: Multi-File Documentation Update

### Scenario
Updating documentation across multiple files.

### Workflow
1. **Add Context**: Attach README.md, API.md, and CHANGELOG.md
2. **Navigate Attachments**: Use `Tab` to review each file
3. **Submit Request**: "Update all documentation for the new v2.0 API"
4. **Review in Sequence**: Use `F8` to navigate between files and changes
5. **Selective Acceptance**: Accept documentation updates, reject version changes

### Benefits
- Efficient multi-file handling
- Visual distinction helps track progress
- Attachment navigation improves workflow

## Example 3: Iterative Development with Visual Distinction

### Scenario
Building a feature through multiple chat iterations.

### Workflow
1. **Initial Planning**: User message clearly distinguished from AI response
2. **Implementation Request**: Visual separation makes conversation easy to follow
3. **Testing Request**: Clear message history helps track progress
4. **Bug Fix Request**: Easy to identify conversation flow
5. **Final Review**: Message distinction aids in reviewing entire conversation

### Benefits
- Clear conversation flow
- Easy to track development progress
- Reduced cognitive load when reviewing history

## Example 4: Floating Window Multi-Project Workflow

### Scenario
Working on two projects simultaneously.

### Workflow
1. **Main Project**: Keep primary chat in main VS Code window
2. **Secondary Project**: Drag chat to floating window for second project
3. **Context Switching**: Use dock/undock buttons to move chat as needed
4. **New Conversations**: Start new chat in floating window when needed
5. **Parallel Development**: Work on both projects with separate chat contexts

### Benefits
- Multi-project support
- Flexible window management
- Separate conversation contexts
- Improved productivity for complex workflows

## Best Practices

### For Keyboard Users
- Learn all shortcuts for maximum efficiency
- Use keyboard navigation for attachments
- Rely on shortcuts for edit operations

### For Mouse Users
- Utilize hover states for additional actions
- Drag and drop for attachment management
- Click-based undo operations

### For All Users
- Experiment safely with undo functionality
- Use visual cues to track conversation flow
- Take advantage of attachment navigation
- Leverage floating windows for complex workflows
```

---

### chat-improvements-kit/exercise-3-ux-improvements/assets/undo-edits-demo.gif

```
Animated GIF showing:
- Chat request creating file edits
- Hovering over request to reveal X button
- Clicking X to undo edits
- Files reverting to previous state
- Keyboard shortcut alternative (Ctrl+Shift+Z)
```

---

### chat-improvements-kit/exercise-3-ux-improvements/assets/attachment-navigation.png

```
Screenshot showing:
- Multiple file attachments in chat input
- Tab navigation highlighting
- Attachment reordering via drag and drop
- Remove buttons for individual attachments
```

This resource kit provides comprehensive hands-on experience with VS Code's Chat Improvements from version 1.101. The exercises cover tool sets organization, custom chat modes creation, and UX enhancements, while demos showcase advanced workflows like diagnostic awareness, floating windows, and context management.

Would you like me to continue with the next major feature? The next feature would be "Editor Experience" which includes find-as-you-type, custom menus, settings search suggestions, and other editor enhancements.
