---
feature: "Edit and Resubmit Previous Chat Requests (Experimental)"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription with Chat"
  - "Understanding of chat conversation flow"
audience: "Power users and developers who frequently iterate on chat prompts"
---

# 🚀 Feature Training: `Edit and Resubmit Previous Chat Requests (Experimental)` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Edit and Resubmit Previous Chat Requests (Experimental)`
- **Release Version:** `1.102`
- **Feature Type:** `Chat Enhancement`
- **Summary:**  
  Experimental feature allowing users to edit previous chat requests and resubmit them, with options to modify text, context, mode, and model while maintaining conversation flow.

## 2. Why It Matters

- **Iterative Refinement:** Easily refine and improve prompts without starting new conversations
- **Context Adjustment:** Modify attached files or code context for better AI responses
- **Mode Switching:** Change between different chat modes (Ask, Edit, Agent) for the same prompt
- **Model Experimentation:** Try different AI models on the same request for comparison
- **Target Users:** Power users, prompt engineers, and developers who iterate frequently on AI requests
- **Status:** Experimental feature with multiple interaction modes for testing

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription with Chat enabled
- Understanding of chat modes and conversation flow
- Experimental settings enabled for different edit modes

### 3.2 How to Enable/Access

- **Setting Configuration:** `chat.editRequests` with three modes:
  - `chat.editRequests.inline` - Edit directly within chat request
  - `chat.editRequests.hover` - Toolbar button appears on hover
  - `chat.editRequests.input` - Edit in input box at bottom
- **Activation:** Hover over any previous chat request to reveal edit options
- **No Additional Extensions Required**

### 3.3 Step-by-Step Usage

1. **Locate Previous Request:**
   - Scroll to any previous chat request in your conversation
   - Hover over the request to reveal edit options

2. **Initiate Edit Mode:**
   - **Inline Mode:** Select text directly within the request
   - **Hover Mode:** Click the edit button that appears
   - **Input Mode:** Use toolbar to edit in input box

3. **Modify Request Components:**
   - **Text Content:** Change the prompt wording
   - **Attached Context:** Add/remove files or code selections
   - **Chat Mode:** Switch between Ask, Edit, Agent modes
   - **AI Model:** Select different language model

4. **Resubmit Request:**
   - Confirm your changes
   - Request is resubmitted with modifications
   - All subsequent requests are removed
   - Any edits made after original request are undone

### 3.4 Example(s)

- **Simple example:**  
  Original request: "Explain this function"
  Edited request: "Explain this function and suggest improvements"
  Result: New response with additional suggestions

- **Advanced/tip:**  
  Switch from Ask mode to Agent mode on the same prompt to get different types of responses - Ask gives explanations, Agent might provide actionable code changes.

**Edit workflow:**

```
1. Original: "Fix this bug" (Ask mode) → 🔧 Response explanation
2. Edit: "Fix this bug" (Agent mode) → 🤖 Automatic code fixes
3. Edit: "Fix this bug and add tests" → ✅ Fixes + test cases
```

**Configuration options:**

```json
{
  "chat.editRequests": "hover"  // or "inline" or "input"
}
```

**What gets reset when editing:**

- ❌ All chat responses after the edited request
- ❌ Any code edits applied from subsequent responses  
- ❌ Files modified by later agent actions
- ✅ New conversation branch starts from edited request

## 4. Troubleshooting & FAQ

- **Q: Why don't I see edit options when hovering?**
  - A: Ensure you have the `chat.editRequests` setting configured and you're hovering over a previous request, not the current one.

- **Q: What happens to my conversation history after editing?**
  - A: All requests and responses after the edited request are permanently removed to maintain conversation consistency.

- **Q: Can I undo an edit operation?**
  - A: No, editing is permanent. However, you can start a new conversation if you want to preserve the original flow.

- **Q: Which edit mode should I use?**
  - A: Try different modes to see what feels most natural:
    - **Inline:** Quick text changes
    - **Hover:** Clear visual indication of edit capability
    - **Input:** Familiar editing in input box

**Experimental Limitations:**

- Feature behavior may change as it's still experimental
- Not all edit entry points may be available in every VS Code installation
- Some complex edits might not work as expected
- Performance may vary depending on conversation length

## 5. Additional Resources

- Official documentation: [Copilot Chat](https://code.visualstudio.com/docs/copilot/chat/copilot-chat)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: Custom Chat Modes, Agent Mode
- Settings reference: `chat.editRequests` configuration

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Edit and Resubmit Previous Requests |
