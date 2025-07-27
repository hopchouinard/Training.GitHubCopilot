---
feature: "Improved Editing Support for Chat Modes/Prompts/Instructions"
release: "1.102"
prerequisites:
  - "Basic understanding of VS Code editor features"
  - "Familiarity with chat modes and instruction files"
audience: "Developers creating custom chat modes, prompts, and instruction files"
---

# 🚀 Feature Training: `Improved Editing Support for Chat Modes/Prompts/Instructions` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Improved Editing Support for Chat Modes/Prompts/Instructions`
- **Release Version:** `1.102`
- **Feature Type:** `Editor Enhancement`
- **Summary:**  
  Enhanced editor experience for creating and editing chat mode files, prompts, and instruction files with completions, validation, and contextual help through hovers.

## 2. Why It Matters

- **Improved Productivity:** IntelliSense and completions speed up authoring of chat configurations
- **Error Prevention:** Real-time validation catches configuration mistakes before they cause issues
- **Better Documentation:** Hover tooltips provide immediate context and explanations for properties
- **Easier Onboarding:** New users can learn configuration options through built-in help
- **Target Users:** Anyone creating custom chat modes, prompts, or instruction files
- **Status:** Available by default when editing relevant file types in VS Code 1.102+

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- Basic understanding of markdown and YAML front matter
- Files with appropriate extensions (`.chatmode.md`, `.instructions.md`, `.prompt.md`)

### 3.2 How to Enable/Access

- **Automatic Activation:** Features activate automatically when editing supported files
- **File Types Supported:**
  - Chat mode files (`.chatmode.md`)
  - Instruction files (`.instructions.md`)
  - Prompt files (`.prompt.md`)
- **No Configuration Required:** Works out-of-the-box

### 3.3 Step-by-Step Usage

1. **Create or Open a Chat Mode File:**
   - Open any `.chatmode.md` file in VS Code
   - Enhanced editing features activate automatically

2. **Use IntelliSense Completions:**
   - Type in the front matter section
   - Press `Ctrl+Space` to trigger completions
   - Select from available metadata properties

3. **Leverage Hover Documentation:**
   - Hover over any property in the front matter
   - Read contextual tooltips explaining property purpose
   - Understand valid values and usage patterns

4. **Benefit from Real-time Validation:**
   - Invalid properties are highlighted with red squiggles
   - Check Problems panel for detailed error messages
   - Fix issues as you type for immediate feedback

### 3.4 Example(s)

- **Simple example:**  
  When creating a chat mode, type `mod` and see IntelliSense suggest `model` with documentation about specifying AI models.

- **Advanced/tip:**  
  Use hover documentation to understand the difference between `tools` array and `toolsets` reference, and see examples of valid model identifiers.

**Editor features in action:**

```yaml
---
description: "Custom code review mode"  # ← Hover shows: Description text for mode
tools: ["codebase", "search"]           # ← IntelliSense suggests available tools
model: "gpt-4"                          # ← Completions show valid model names
invalidProperty: "test"                 # ← Red squiggle indicates unknown property
---
```

**Validation examples:**

- ✅ Valid: `model: "gpt-4"`
- ❌ Invalid: `model: "nonexistent-model"` (validation error)
- ✅ Valid: `tools: ["codebase", "search"]`
- ❌ Invalid: `tools: "not-an-array"` (type validation error)

## 4. Troubleshooting & FAQ

- **Q: Why aren't I seeing completions in my file?**
  - A: Ensure your file has the correct extension (`.chatmode.md`, `.instructions.md`, etc.) and the front matter is properly formatted with `---` delimiters.

- **Q: What metadata properties are supported?**
  - A: Common properties include `description`, `tools`, `model`, `toolsets`. Use IntelliSense to see all available options for your file type.

- **Q: How do I see what models are available?**
  - A: Use IntelliSense when typing the `model` property value. Available models depend on your Copilot subscription and configuration.

- **Q: Can I turn off validation if it's too strict?**
  - A: Validation helps prevent configuration errors, but you can check VS Code settings for language-specific validation options if needed.

**Common Validation Issues:**

- **Unknown property:** Check spelling and use IntelliSense to see valid properties
- **Invalid model:** Ensure the model name is supported by your Copilot subscription
- **Wrong type:** Arrays should use `["item1", "item2"]` format, not comma-separated strings
- **Missing front matter:** Ensure your file starts and ends the metadata section with `---`

## 5. Additional Resources

- Official documentation: [Chat Modes](https://code.visualstudio.com/docs/copilot/chat/chat-modes)
- Related documentation: [Custom Instructions](https://code.visualstudio.com/docs/copilot/copilot-customization)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: Custom Chat Modes, Import via Link

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Improved Editing Support |
