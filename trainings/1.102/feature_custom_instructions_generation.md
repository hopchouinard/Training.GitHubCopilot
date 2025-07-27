---
feature: "Custom Instructions Generation"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription"
  - "Basic understanding of project structure"
audience: "Team leads, project managers, and developers who want to improve Copilot's code suggestions"
---

# 🚀 Feature Training: `Custom Instructions Generation` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Custom Instructions Generation`
- **Release Version:** `1.102`
- **Feature Type:** `AI Enhancement Tool`
- **Summary:**  
  Automated command that analyzes your codebase to generate project-specific instructions for Copilot, improving AI suggestions by reflecting your coding standards and project conventions.

## 2. Why It Matters

- **Improved Code Quality:** Copilot suggestions align with your team's specific coding standards and conventions
- **Faster Onboarding:** New team members get project context automatically through Copilot's enhanced guidance  
- **Consistency:** Ensures all AI-generated code follows project patterns and requirements
- **Target Users:** Team leads, project managers, and developers working on established codebases
- **Status:** Available by default in VS Code 1.102+ with Copilot Chat

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription with Chat enabled
- An existing workspace/project with code files

### 3.2 How to Enable/Access

- **Command Palette:** Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)
- **Command:** Type "Chat: Generate Instructions"
- **Alternative Access:** Via Configure menu in the Chat view (gear icon)
- **No Settings Required:** Works out-of-the-box with any codebase

### 3.3 Step-by-Step Usage

1. **Open Your Project:**
   - Ensure you have a workspace open with existing code files

2. **Run the Command:**
   - Open Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
   - Type "Chat: Generate Instructions" and select it

3. **Agent Analysis:**
   - Copilot agent analyzes your codebase structure
   - Examines technologies, frameworks, and coding patterns
   - Identifies conventions and best practices

4. **File Creation:**
   - Creates `copilot-instructions.md` in your `.github` folder
   - If file exists, suggests improvements instead of overwriting

5. **Review and Customize:**
   - Open the generated file
   - Review the auto-generated instructions
   - Edit and customize to match your team's specific needs

### 3.4 Example(s)

- **Simple example:**  
  For a React TypeScript project, the generated instructions might include:

  ```markdown
  # Copilot Instructions
  
  ## Project Context
  - React 18 with TypeScript
  - Uses functional components with hooks
  - Material-UI for styling
  
  ## Coding Standards
  - Use arrow functions for components
  - Prefer const assertions for type safety
  - Follow kebab-case for file names
  ```

- **Advanced/tip:**  
  Create multiple `.instructions.md` files for different folders (e.g., `/backend/.instructions.md`, `/frontend/.instructions.md`) with specific guidance for each area of your codebase.

**Sample generated instruction file:**

```markdown
# Project Instructions for Copilot

## Technology Stack
- Node.js with Express.js backend
- React frontend with TypeScript
- MongoDB database with Mongoose ODM

## Coding Conventions
- Use camelCase for variables and functions
- Use PascalCase for component names
- Always include error handling in async functions
- Prefer async/await over Promises

## Architecture Patterns
- Follow MVC pattern for backend routes
- Use custom hooks for shared logic
- Implement proper data validation on both client and server
```

## 4. Troubleshooting & FAQ

- **Q: Where is the generated file saved?**
  - A: The file is created as `copilot-instructions.md` in your `.github` folder. If `.github` doesn't exist, it will be created.

- **Q: What if the generated instructions are incomplete?**
  - A: The generated file is a starting point. Review and edit it to add any missing team-specific requirements or standards.

- **Q: Can I have different instructions for different parts of my project?**
  - A: Yes, create multiple `.instructions.md` files in specific folders and use glob patterns to apply them contextually.

- **Q: How often should I regenerate instructions?**
  - A: Regenerate when your project structure, technologies, or coding standards change significantly.

## 5. Additional Resources

- Official VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Documentation: [Customizing AI responses with instructions](https://code.visualstudio.com/docs/copilot/copilot-customization)
- Related features: Custom Chat Modes, Open Source Copilot Chat Extension

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Custom Instructions Generation |
