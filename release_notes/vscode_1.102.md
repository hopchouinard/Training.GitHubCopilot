---
Order: 111
TOCTitle: June 2025
PageTitle: Visual Studio Code June 2025
MetaDescription: Learn what is new in the Visual Studio Code June 2025 Release (1.102)
MetaSocialImage: 1_102/release-highlights.png
Date: 2025-07-09
DownloadVersion: 1.102.2
---
# June 2025 (version 1.102)

## Release date: July 9, 2025

**Update 1.102.1**: The update addresses these [issues](https://github.com/microsoft/vscode/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22June+2025+Recovery+1%22+).

**Update 1.102.2**: The update addresses these [issues](https://github.com/microsoft/vscode/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22June+2025+Recovery+2%22+).

---

Welcome to the June 2025 release of Visual Studio Code. There are many updates in this version that we hope you'll like, some of the key highlights include:

* **Chat**
  * Explore and contribute to the open sourced GitHub Copilot Chat extension ([Read our blog post](https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone)).
  * Generate custom instructions that reflect your project's conventions ([Show more](#generate-custom-instructions)).
  * Use custom modes to tailor chat for tasks like planning or research ([Show more](#chat-mode-improvements)).
  * Automatically approve selected terminal commands ([Show more](#terminal-auto-approval)).
  * Edit and resubmit previous chat requests ([Show more](#edit-previous-requests-experimental)).

* **MCP**
  * MCP support is now generally available in VS Code ([Show more](#mcp-support-in-vs-code-is-generally-available)).
  * Easily install and manage MCP servers with the MCP view and gallery ([Show more](#mcp-server-discovery-and-installation)).
  * MCP servers as first-class resources in profiles and Settings Sync ([Show more](#mcp-servers-as-first-class-resources)).

* **Editor experience**
  * Delegate tasks to Copilot coding agent and let it handle them in the background ([Show more](#start-a-coding-agent-session-preview)).
  * Scroll the editor on middle click ([Show more](#scroll-on-middle-click)).

> If you'd like to read these release notes online, go to [Updates](https://code.visualstudio.com/updates) on [code.visualstudio.com](https://code.visualstudio.com).
**Insiders:** Want to try new features as soon as possible? You can download the nightly [Insiders](https://code.visualstudio.com/insiders) build and try the latest updates as soon as they are available.

## Chat

### Copilot Chat is open source

We're excited to announce that we've open sourced the GitHub Copilot Chat extension! The source code is now available at [`microsoft/vscode-copilot-chat`](https://github.com/microsoft/vscode-copilot-chat) under the MIT license.

This marks a significant milestone in our commitment to transparency and community collaboration. By open sourcing the extension, we're enabling the community to:

* **Contribute directly** to the development of AI-powered chat experiences in VS Code
* **Understand the implementation** of chat modes, custom instructions, and AI integrations
* **Build upon our work** to create even better AI developer tools
* **Participate in shaping the future** of AI-assisted coding

You can explore the repository to see how features like [agent mode](https://github.com/microsoft/vscode-copilot-chat/blob/e1222084830244174e6aa64683286561fa7e7607/src/extension/prompts/node/agent/agentPrompt.tsx), [inline chat](https://github.com/microsoft/vscode-copilot-chat/blob/e1222084830244174e6aa64683286561fa7e7607/src/extension/prompts/node/inline/inlineChatEditCodePrompt.tsx), and [MCP integration](https://github.com/microsoft/vscode-copilot-chat/blob/e1222084830244174e6aa64683286561fa7e7607/src/extension/mcp/vscode-node/mcpToolCallingLoop.tsx) are implemented. We welcome contributions, feedback, and collaboration from the community.

To learn more about this milestone and our broader vision for open source AI editor tooling, read our detailed blog post: [Open Source AI Editor - First Milestone](https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone).

### Chat mode improvements

Last milestone, we previewed [custom chat modes](https://code.visualstudio.com/docs/copilot/chat/chat-modes#_custom-chat-modes). In addition to the built-in chat modes 'Ask', 'Edit' and 'Agent', you can define your own chat modes with specific instructions and a set of allowed tools that you want the LLM to follow when replying to a request.

This milestone, we have made several improvements and bug fixes in this area.

#### Configure language model

Upon popular request, you can now also specify which language model should be used for a chat mode. Add the `model` metadata property to your `chatmode.md` file and provide the model identifier (we provide IntelliSense for the model info).

![Screenshot that shows the IntelliSense for the model metadata property in chat mode file.](images/1_102/prompt-file-model-code-completion.png)

#### Improved editing support

The editor for [chat modes](https://code.visualstudio.com/docs/copilot/chat/chat-modes), [prompts](https://code.visualstudio.com/docs/copilot/copilot-customization#_prompt-files-experimental), and [instruction files](https://code.visualstudio.com/docs/copilot/copilot-customization#_custom-instructions) now supports completions, validation, and hovers for all supported metadata properties.

![Screenshot that shows the hover information for tools.](images/1_102/tools-hover.png)

![Screenshot that shows the model diagnostics when a model is not available for a specific chat mode.](images/1_102/prompt-file-diagnostics.png)

#### Gear menu in the chat view

The **Configure Chat** action in the Chat view toolbar lets you manage custom modes as well as reusable instructions, prompts, and tool sets:

![Screenshot that shows the Configure Chat menu in the Chat view.](images/1_102/chat-gear.png)

Selecting **Modes** shows all currently installed custom modes and enables you to open, create new, or delete modes.

#### Import modes, prompts and instructions via a `vscode` link

You can now import chat mode, reusable prompt and instruction files from external links, such as a gist or our [awesome-copilot](https://github.com/github/awesome-copilot) community repository. For example, the following link will import the chat mode file for Burke's GPT 4.1 Beast Mode:

[Add GPT 4.1 Beast Mode to VS Code](vscode:chat-mode/install?url=https://raw.githubusercontent.com/github/awesome-copilot/refs/heads/main/chatmodes/4.1-Beast.chatmode.md)

This will prompt for a destination, either your current workspace or your user settings, and confirm the name before importing the mode file from the URL.

Try it out on the 100+ community-contributed instructions, prompts, and chat modes at [awesome-copilot](https://github.com/github/awesome-copilot).

### Generate custom instructions

Setting up [custom instructions](https://code.visualstudio.com/docs/copilot/copilot-customization) for your project can significantly improve AI suggestions by providing context about your coding standards and project conventions. However, creating effective instructions from scratch might be challenging.

This milestone, we're introducing the **Chat: Generate Instructions** command to help you bootstrap custom instructions for your workspace. Run this command from the Command Palette or the Configure menu in the Chat view, and agent mode will analyze your codebase to generate tailored instructions that reflect your project's structure, technologies, and patterns.

The command creates a `copilot-instructions.md` file in your `.github` folder or suggests improvements to existing instruction files. You can then review and customize the generated instructions to match your team's specific needs.

Learn more about [customizing AI responses with instructions](https://code.visualstudio.com/docs/copilot/copilot-customization).

...existing content truncated for brevity...
