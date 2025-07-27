---
feature: "Open Source Copilot Chat Extension"
release: "1.102"
prerequisites:
  - "Basic understanding of VS Code interface"
  - "GitHub Copilot subscription"
audience: "All developers using VS Code with Copilot"
---

# 🚀 Feature Training: `Open Source Copilot Chat Extension` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Open Source Copilot Chat Extension`
- **Release Version:** `1.102`
- **Feature Type:** `AI Extension Enhancement`
- **Summary:**  
  GitHub Copilot Chat extension is now open source under MIT license, enabling community contributions, transparency, and extensibility for AI-powered chat experiences in VS Code.

## 2. Why It Matters

- **Transparency:** Developers can now see exactly how the chat extension works and understand its implementation
- **Community Contributions:** Open source nature allows developers to contribute directly to AI-powered chat experiences
- **Extensibility:** Enables building better AI developer tools on top of the existing framework
- **Learning Opportunity:** Developers can study implementations of agent mode, inline chat, and MCP integration
- **Target Users:** All VS Code developers, extension authors, and AI tool builders
- **Status:** Available by default with GitHub Copilot Chat extension

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription
- Git knowledge for contributing to open source projects (optional)

### 3.2 How to Enable/Access

- **Repository Access:** Visit [`microsoft/vscode-copilot-chat`](https://github.com/microsoft/vscode-copilot-chat)
- **License:** MIT License
- **No Configuration Required:** The feature is available by default when using Copilot Chat
- **Contributing:** Follow standard GitHub contribution workflow (fork, branch, PR)

### 3.3 Step-by-Step Usage

1. **Explore the Repository:**
   - Navigate to <https://github.com/microsoft/vscode-copilot-chat>
   - Browse the source code structure

2. **Understand Key Components:**
   - Agent mode implementation: `src/extension/prompts/node/agent/agentPrompt.tsx`
   - Inline chat: `src/extension/prompts/node/inline/inlineChatEditCodePrompt.tsx`
   - MCP integration: `src/extension/mcp/vscode-node/mcpToolCallingLoop.tsx`

3. **Contributing (Optional):**
   - Fork the repository
   - Create feature branch
   - Submit pull requests with improvements

### 3.4 Example(s)

- **Simple example:**  
  Browse the repository to understand how chat modes are implemented and how the extension integrates with VS Code APIs.

- **Advanced/tip:**  
  Study the MCP integration code to understand how to build your own Model Context Protocol servers or integrate with external AI services.

**Sample code exploration:**

```typescript
// Example from agent mode implementation
// Shows how prompts are structured for AI interactions
export const agentPrompt = {
  systemMessage: "You are an AI coding assistant...",
  tools: ["editFiles", "runCommands", "search"],
  // ... implementation details
};
```

## 4. Troubleshooting & FAQ

- **Q: Can I contribute without a Copilot subscription?**
  - A: Yes, you can contribute to the open source code without a subscription, but testing requires access to Copilot services.

- **Q: Will my contributions affect all VS Code users?**
  - A: Contributions go through Microsoft's review process before being integrated into the official extension.

- **Q: How do I report bugs or suggest features?**
  - A: Use the GitHub Issues section in the vscode-copilot-chat repository.

## 5. Additional Resources

- Official repository: <https://github.com/microsoft/vscode-copilot-chat>
- Blog post: [Open Source AI Editor - First Milestone](https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: Custom Chat Modes, MCP Integration, Agent Mode

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Open Source Copilot Chat Extension |
