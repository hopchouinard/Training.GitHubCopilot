# Features in Visual Studio Code 1.101 (May 2025)

- **MCP Enhancements**
  - Support for prompts: Define reusable snippets/tasks for language models via MCP servers.
  - Support for resources: Resource templates, saving resources from MCP tool calls, and browsing resources across servers.
  - Support for sampling (Experimental): MCP servers can make requests back to the model, with user confirmation and request logs.
  - Support for authentication: Interact with MCP servers requiring authentication, supporting multiple authorization specs and account management.
  - Development mode for MCP servers: Add a `dev` key to server config for file watching and debugging.
  - MCP extension APIs: Extensions can publish/discover MCP servers.

- **Chat Improvements**
  - Tool sets: Group related tools for easier management and use in agent mode.
  - Custom chat modes (Preview): Define custom chat modes with tailored instructions and tool access.
  - Chat UX improvements: Distinct user/AI messages, easier undo, improved attachment navigation.
  - Task diagnostic awareness: Chat agent is aware of errors/warnings from problem matchers.
  - Terminal cwd context: Agent mode is aware of terminal working directory.
  - Floating window improvements: Dock and start new chat sessions in floating windows.
  - Fetch tool confirmation: Added warning about prompt injection.
  - Customize built-in tools: Enable/disable all built-in tools in agent/custom modes.
  - Send elements to chat (Experimental): Select and attach web elements from Simple Browser/Live Preview.
  - Implicit context: Streamlined context addition from current file/editor.

- **Accessibility**
  - User action required sound: Accessibility signal for chat requiring user action.
  - New code action sounds: Distinct sounds for code action triggered/applied.
  - Agent mode accessibility: Rich info in confirmation dialogs for screen readers.

- **Editor Experience**
  - Find as you type: Control find-on-type behavior in Find control.
  - Custom menus with native window title bar: Specify menu style for menu/context menus.
  - Linux native window context menu: Support for native context menu on Linux.
  - Process explorer web support: Process explorer now available in web/remote.
  - Windows shell environment discovery: VS Code inherits PowerShell profile environments.
  - Unpublished extension warning: Warning indicator for extensions no longer in Marketplace.
  - Settings search suggestions (Preview): AI search for semantically similar settings.
  - Search keyword suggestions (Preview): Improved performance and moved to VS Code core.
  - Semantic search behavior options (Preview): Control when semantic search is triggered.
  - Edit Context: Editor input powered by EditContext API (enabled by default).

- **Code Editing**
  - NES import suggestions: Improved suggestions for missing imports in JS/TS/Python.
  - NES acceptance flow: Seamless keyboard navigation for accepting suggestions.

- **Notebooks**
  - Follow mode for agent cell execution: Notebook view scrolls to currently executed cell.
  - Notebook tools for agent mode: Kernel configuration, environment setup, and cell execution.
  - Long running agent workflows: Internal Notebook Summary tool for context.
  - Cell preview in run confirmation: Preview code when agent requests cell execution.

- **Source Control**
  - Copilot coding agent integration: Assign/track tasks for Copilot agent in PR/issue view.
  - Source control history item details: View resources of history items in Graph view.
  - Add history item to chat context: Add commit/PR contents as chat context.

- **Tasks**
  - Instance policy: New `instancePolicy` property for task runOptions (prompt, silent, terminateNewest/Oldest, warn).

- **Terminal**
  - Language server based terminal suggest: LSP completions in Python REPL sessions.

- **Remote Development**
  - SSH pre-connection script and Remote Explorer improvements.

- **Python Extension**
  - New chat tools: Get Python environment info, install packages, configure environment.
  - Project creation from template: Create Python packages/scripts with scaffolding.
  - PyEnv and Poetry support: Environment and package management.

- **GitHub Pull Requests Extension**
  - Images in comments from private repos shown in PR comments.
  - Notifications view shown by default.
  - Issue/PR links open in VS Code.
  - "Assigned to Me" query removed; Copilot queries added for Copilot-enabled repos.
  - Copilot session status/actions in timeline.

- **Extension Authoring**
  - Secret scanning when packaging extensions: VSCE scans for secrets and warns/errors.
  - Web environment detection: Node.js extension host update, breaking change for `navigator` global object.

- **Proposed APIs**
  - Authentication Providers: Declare supported authorization servers for MCP.

- **Engineering**
  - Electron 35 update: Chromium 134, Node.js 22.15.1.
  - ESM support: Real-world adoption in GitHub Issue Notebooks extension.

- **Notable Fixes**
  - Tree-Sitter based syntax highlighting depends on model service.

- **Thank You**
  - Acknowledgement of contributors to VS Code and related projects.
