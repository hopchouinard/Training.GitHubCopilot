---
feature: "Custom Chat Modes"
release: "1.102"
resource_type: "Both"
audience: "Developers and teams wanting to create specialized AI chat workflows"
prerequisites:
  - "GitHub Copilot subscription with Chat"
  - "Basic understanding of markdown and YAML"
summary: |
  "Hands-on exercises and demos for creating, configuring, and using custom chat modes in VS Code. Learn to build specialized AI assistants for code review, planning, and team-specific workflows."
---

# 📦 Resource Kit: `Custom Chat Modes` — `Exercise & Demo`

## Directory Structure

```
CustomChatModes/
├── README.md
├── Exercise1-BasicMode/
│   ├── instructions.md
│   ├── solution/
│   │   └── code-review.chatmode.md
│   ├── starter/
│   │   └── template.chatmode.md
│   └── assets/
│       └── sample-code.js
├── Exercise2-AdvancedMode/
│   ├── instructions.md
│   ├── solution/
│   │   └── team-standards.chatmode.md
│   ├── starter/
│   │   └── advanced-template.chatmode.md
│   └── assets/
│       └── company-standards.md
├── Demo1-QuickStart/
│   ├── walkthrough.md
│   └── src/
│       └── planning-mode.chatmode.md
└── Demo2-TeamWorkflow/
    ├── walkthrough.md
    ├── src/
    │   └── multi-mode-setup.json
    └── assets/
        └── team-config-guide.md
```

## File Listings and Contents

For each file in the structure above, define the complete contents here. This section enables automation agents to generate the full directory and file tree as specified.

---

### CustomChatModes/README.md

```markdown
# Custom Chat Modes — Exercise & Demo Resource Kit

Welcome! This resource kit contains:
- Exercises and solutions to guide mastery of Custom Chat Modes in VS Code 1.102
- Demos with step-by-step walkthroughs for creating specialized AI assistants
- Real-world examples for code review, planning, and team workflows

## What You'll Learn
- How to create basic and advanced custom chat modes
- Best practices for mode configuration and tool selection
- Team collaboration patterns using shared chat modes
- Integration with existing development workflows

## Prerequisites
- VS Code 1.102 or later
- GitHub Copilot subscription with Chat enabled
- Basic understanding of markdown and YAML front matter

## Getting Started
1. Start with Exercise1-BasicMode for fundamental concepts
2. Progress to Exercise2-AdvancedMode for complex scenarios
3. Review demos for practical implementation patterns
```

---

### CustomChatModes/Exercise1-BasicMode/instructions.md

```markdown
# Exercise 1: Create a Basic Code Review Chat Mode

## Goal
Learn to create a simple custom chat mode specialized for code review tasks.

## Task
Create a chat mode called "code-review.chatmode.md" that:
1. Focuses on security and code quality
2. Uses specific tools for code analysis
3. Provides structured review feedback

## Steps
1. Create a new .chatmode.md file
2. Configure the front matter with appropriate metadata
3. Write instructions for security-focused code review
4. Test the mode with the provided sample code

## Input/Output
- **Input**: Use the template.chatmode.md as starting point
- **Sample Code**: assets/sample-code.js for testing
- **Expected Output**: A working chat mode that provides security-focused code reviews

## Success Criteria
- Mode appears in Chat view mode picker
- Mode provides security-specific feedback on sample code
- Mode uses only specified tools (codebase, search, problems)

## Tips
- Keep instructions clear and specific
- Use the `tools` array to limit available functionality
- Test with different code examples to verify behavior
```

---

### CustomChatModes/Exercise1-BasicMode/starter/template.chatmode.md

```markdown
---
description: "TODO: Add description for your code review mode"
tools: []
---

# TODO: Add your custom instructions here

You are a code reviewer focused on...

[Complete this template with your own instructions]
```

---

### CustomChatModes/Exercise1-BasicMode/solution/code-review.chatmode.md

```markdown
---
description: "Security-focused code review assistant"
tools: ["codebase", "search", "problems"]
---

# Security Code Review Mode

You are a security-focused code reviewer. When reviewing code, prioritize:

## Security Checks
- Input validation and sanitization
- Authentication and authorization mechanisms
- SQL injection and XSS vulnerabilities
- Secure data handling and storage
- Error handling that doesn't leak sensitive information

## Code Quality
- Follow secure coding practices
- Check for proper error handling
- Verify logging doesn't expose sensitive data
- Ensure proper resource cleanup

## Review Format
Provide feedback in this structure:
1. **Security Issues**: List any security concerns
2. **Code Quality**: General improvements
3. **Recommendations**: Specific actionable changes

Focus on practical, actionable feedback that improves security posture.
```

---

### CustomChatModes/Exercise1-BasicMode/assets/sample-code.js

```javascript
// Sample code for testing the code review mode
function loginUser(username, password) {
    // TODO: This code has several security issues for review
    const query = "SELECT * FROM users WHERE username = '" + username + "' AND password = '" + password + "'";
    
    try {
        const result = database.query(query);
        if (result.length > 0) {
            console.log("Login successful for: " + username);
            return { success: true, user: result[0] };
        } else {
            console.log("Login failed for: " + username);
            return { success: false, error: "Invalid credentials" };
        }
    } catch (error) {
        console.log("Database error: " + error.message);
        return { success: false, error: "Database error: " + error.message };
    }
}

function getUserData(userId) {
    // Another function with potential issues
    const userData = database.query("SELECT * FROM users WHERE id = " + userId);
    return userData;
}
```

---

### CustomChatModes/Exercise2-AdvancedMode/instructions.md

```markdown
# Exercise 2: Advanced Team Standards Mode

## Goal
Create an advanced chat mode that enforces team coding standards and integrates with external instruction files.

## Task
Build a comprehensive team standards mode that:
1. References external instruction files
2. Uses multiple tool categories
3. Specifies a particular AI model
4. Includes team-specific conventions

## Steps
1. Create advanced-template.chatmode.md with complex configuration
2. Reference the external company-standards.md file
3. Configure multiple tools and specify model
4. Test with team workflow scenarios

## Input/Output
- **Input**: advanced-template.chatmode.md and company-standards.md
- **Expected Output**: A sophisticated mode that enforces team standards

## Advanced Features to Implement
- Model specification (`model` property)
- External file references using `@file:` syntax
- Multiple tool categories
- Conditional instructions based on file types

## Tips
- Use `@file:company-standards.md` to reference external instructions
- Specify model like "gpt-4" or "claude-3-sonnet"
- Include tools for different development phases
- Make instructions specific to your team's needs
```

---

### CustomChatModes/Exercise2-AdvancedMode/starter/advanced-template.chatmode.md

```markdown
---
description: "TODO: Team standards enforcement mode"
tools: ["codebase", "search"]
model: "TODO: specify model"
---

# Team Standards Mode

TODO: Add comprehensive team standards instructions

Reference external standards: @file:company-standards.md

TODO: Add specific instructions for:
- Code formatting
- Naming conventions  
- Architecture patterns
- Testing requirements
```

---

### CustomChatModes/Exercise2-AdvancedMode/solution/team-standards.chatmode.md

```markdown
---
description: "Comprehensive team coding standards enforcement"
tools: ["codebase", "search", "editFiles", "problems", "runTests"]
model: "gpt-4"
---

# Team Standards Enforcement Mode

Apply our team's comprehensive coding standards when reviewing and suggesting code changes.

@file:company-standards.md

## Additional Enforcement Rules

### Code Organization
- Follow feature-based folder structure
- Group related functionality together
- Maintain clear separation of concerns

### Testing Requirements
- All new functions must have unit tests
- Integration tests for API endpoints
- Minimum 80% code coverage for new code

### Performance Guidelines
- Avoid nested loops where possible
- Use efficient data structures
- Profile critical code paths

### Documentation Standards
- JSDoc comments for all public functions
- README updates for new features
- Architecture decision records for significant changes

When reviewing code, prioritize these standards and provide specific, actionable feedback.
```

---

### CustomChatModes/Exercise2-AdvancedMode/assets/company-standards.md

```markdown
# Company Coding Standards

## Naming Conventions
- Use camelCase for variables and functions
- Use PascalCase for classes and components
- Use UPPER_SNAKE_CASE for constants
- Use kebab-case for file names

## Code Formatting
- Use 2 spaces for indentation
- Maximum line length: 100 characters
- Always use semicolons in JavaScript
- Use trailing commas in multi-line structures

## Architecture Patterns
- Follow MVC pattern for backend services
- Use custom hooks for shared React logic
- Implement repository pattern for data access
- Use dependency injection for testability

## Security Requirements
- Always validate input at API boundaries
- Use parameterized queries for database access
- Implement proper authentication middleware
- Log security events for audit purposes

## Error Handling
- Use structured error responses
- Don't expose internal error details to clients
- Implement proper logging with correlation IDs
- Use try-catch blocks for async operations
```

---

### CustomChatModes/Demo1-QuickStart/walkthrough.md

```markdown
# Demo: Quick Start with Planning Mode

## What You'll See
A demonstration of creating a simple planning-focused chat mode from scratch and using it for project planning tasks.

## Steps

1. **Create the mode file**

    ```bash
    # Open Command Palette (Ctrl+Shift+P)
    # Type: "Chat: New Mode File"
    # Choose workspace location
    ```

2. **Configure basic metadata**

    ```yaml
    ---
    description: "Project planning and architecture assistant"
    tools: ["codebase", "search"]
    ---
    ```

3. **Add planning instructions**

    ```markdown
    # Planning Assistant Mode
    
    Focus on high-level architecture and planning. Break down complex 
    features into smaller, manageable tasks.
    ```

4. **Test the mode**

   - Select "planning-mode" from Chat view
   - Ask: "Help me plan a user authentication system"
   - Observe focused, planning-oriented responses

5. **Iterate and improve**

   - Add more specific tools if needed
   - Refine instructions based on usage
   - Share with team via workspace configuration

## Expected Output

A working chat mode that provides structured, planning-focused responses for software architecture and project breakdown tasks.

```

---

### CustomChatModes/Demo1-QuickStart/src/planning-mode.chatmode.md

```markdown
---
description: "Project planning and architecture assistant"
tools: ["codebase", "search"]
---

# Planning Assistant Mode

You are a software architecture and planning specialist. When asked about implementing features or systems:

## Planning Approach
1. **Break down the problem** into smaller, manageable components
2. **Identify dependencies** between different parts
3. **Suggest implementation order** based on complexity and dependencies
4. **Consider scalability** and future requirements
5. **Highlight potential risks** and mitigation strategies

## Response Format
Structure your planning responses as:

### Overview
Brief summary of the feature/system

### Components
List of major components needed

### Implementation Plan
1. Phase 1: [Foundation/Core components]
2. Phase 2: [Additional features]
3. Phase 3: [Advanced/Optional features]

### Technical Considerations
- Architecture patterns to use
- Technology choices and trade-offs
- Performance and scalability concerns

### Next Steps
Concrete actions to begin implementation

Focus on practical, actionable guidance that helps teams move from idea to implementation efficiently.
```

---

### CustomChatModes/Demo2-TeamWorkflow/walkthrough.md

```markdown
# Demo: Team Workflow with Multiple Modes

## What You'll See
How to set up and manage multiple custom chat modes for different team workflows, including sharing and maintenance strategies.

## Steps

1. **Set up multiple modes**

   - Create modes for different purposes: review, planning, debugging
   - Configure each with appropriate tools and instructions
   - Test each mode independently

2. **Organize team configuration**

    ```json
    {
        "modes": {
        "code-review": "Security and quality focused reviews",
        "planning": "Architecture and project planning",
        "debugging": "Problem diagnosis and resolution"
        }
    }
    ```

3. **Share via workspace**
4. 
   - Save modes in `.vscode/` directory
   - Commit to version control
   - Team members get modes automatically

5. **Maintain and update**
6. 
   - Regular review of mode effectiveness
   - Update instructions based on team feedback
   - Version control mode changes

7. **Monitor usage**
8. 
   - Track which modes are most effective
   - Gather team feedback
   - Iterate on configurations

## Expected Output

A complete team workflow with specialized chat modes that improve productivity and consistency across different development activities.

```

---

### CustomChatModes/Demo2-TeamWorkflow/src/multi-mode-setup.json

```json
{
  "teamModes": {
    "codeReview": {
      "file": "code-review.chatmode.md",
      "purpose": "Security-focused code reviews",
      "tools": ["codebase", "search", "problems"],
      "usage": "Before merging pull requests"
    },
    "planning": {
      "file": "planning.chatmode.md", 
      "purpose": "Project and feature planning",
      "tools": ["codebase", "search"],
      "usage": "Sprint planning and architecture discussions"
    },
    "debugging": {
      "file": "debug-assistant.chatmode.md",
      "purpose": "Problem diagnosis and resolution",
      "tools": ["codebase", "search", "problems", "runTests"],
      "usage": "When investigating bugs or issues"
    },
    "documentation": {
      "file": "doc-writer.chatmode.md",
      "purpose": "Technical documentation creation",
      "tools": ["codebase", "search", "editFiles"],
      "usage": "Creating and updating project documentation"
    }
  },
  "workflowIntegration": {
    "pullRequestReview": "Use codeReview mode",
    "sprintPlanning": "Use planning mode",
    "bugTriage": "Use debugging mode",
    "documentationUpdates": "Use documentation mode"
  },
  "maintenanceSchedule": {
    "modeReview": "Monthly team review of mode effectiveness",
    "instructionUpdates": "Quarterly updates based on team feedback",
    "toolEvaluation": "As needed when new tools become available"
  }
}
```

---

### CustomChatModes/Demo2-TeamWorkflow/assets/team-config-guide.md

```markdown
# Team Configuration Guide for Custom Chat Modes

## Setting Up Team Modes

### 1. Workspace Configuration
Place all team chat modes in the `.vscode/` directory of your project:
```

project-root/
├── .vscode/
│   ├── code-review.chatmode.md
│   ├── planning.chatmode.md
│   ├── debugging.chatmode.md
│   └── documentation.chatmode.md

```

### 2. Version Control
- Commit chat mode files to your repository
- Include them in code reviews
- Document changes in pull requests

### 3. Team Onboarding
- Include mode usage in team documentation
- Provide examples of when to use each mode
- Create quick reference guides

## Best Practices

### Mode Design
- Keep instructions focused and specific
- Use descriptive names and descriptions
- Limit tools to what's actually needed
- Test modes with real scenarios

### Team Adoption
- Start with one mode and expand gradually
- Gather feedback and iterate
- Provide training on mode usage
- Celebrate successful adoption

### Maintenance
- Regular review of mode effectiveness
- Update instructions based on team evolution
- Remove unused or ineffective modes
- Keep documentation current

## Troubleshooting Common Issues

### Mode Not Appearing
- Check file extension (.chatmode.md)
- Verify front matter format
- Restart VS Code if needed

### Poor Mode Performance
- Review and refine instructions
- Adjust tool selection
- Gather specific feedback from users

### Team Inconsistency
- Provide clear usage guidelines
- Create shared examples
- Regular training sessions
```
