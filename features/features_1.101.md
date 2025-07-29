# Features in Visual Studio Code 1.101 (May 2025)

- **MCP Enhancements**
  - Support for prompts: Define reusable prompts accessible as slash commands in chat, with completions and variable support.
  - Resource support: Resources from MCP tool calls can be saved, attached to chat, and browsed across servers.
  - Sampling (Experimental): MCP servers can request model sampling, with user confirmation and model access controls.
  - Authentication: Interact with MCP servers requiring authentication, supporting multiple authorization specs and account management.
  - Development mode: Enable dev mode for MCP servers with file watching and debugging support for Node.js and Python.
  - Extension APIs: Extensions can publish and discover MCP servers, enabling dynamic integration.

- **Chat Improvements**
  - Tool sets: Group related tools for easier management and use in agent mode or chat queries.
  - Custom chat modes (Preview): Define custom chat modes with tailored instructions and tool access for specialized workflows.
  - UX enhancements: Improved distinction between user/AI messages, visible undo for requests, and better attachment navigation.
  - Task diagnostic awareness: Chat agent responds intelligently to errors/warnings from problem matchers.
  - Terminal cwd context: Agent mode is aware of terminal working directory for more accurate commands.
  - Floating window actions: Dock or start new chat sessions from floating windows.
  - Fetch tool confirmation: Added warning for prompt injection risks.
  - Built-in tool customization: Enable/disable built-in tools and tool sets in agent/custom modes.
  - Send elements to chat (Experimental): Select and attach web elements from Live Preview extension to chat.
  - Implicit context: Streamlined context addition from current editor, with keyboard shortcuts and agent hints.

- **Editor Experience**
  - Find-as-you-type: Configurable search behavior in Find control.
  - Custom menus: Choose menu style for title/context menus via settings.
  - Linux native window context menu: Support for native context menu in custom title bar.
  - Process explorer web support: Floating window infrastructure enables process explorer in web/remote environments.
  - Windows shell environment discovery: VS Code inherits PowerShell profile environments.
  - Unpublished extension warning: Indicator for extensions removed from Marketplace.
  - Settings search suggestions (Preview): AI-powered semantic search for settings, with toggle and feedback.
  - Search keyword suggestions (Preview): Faster keyword suggestions in Search view, now in VS Code core.
  - Semantic search behavior options (Preview): Control when semantic search is triggered in Search view.
  - EditContext API: Editor input powered by EditContext for improved IME and input experience.

- **Code Editing**
  - NES import suggestions: Improved next edit suggestions for missing imports in TypeScript, JavaScript, and Python.
  - NES acceptance flow: Seamless keyboard navigation for accepting suggestions.

- **Notebooks**
  - Follow mode for agent cell execution: Notebook view auto-scrolls to executing cell, toggleable in real-time.
  - Notebook tools for agent mode: Kernel configuration and environment setup via Jupyter extension tools.
  - Long running agent workflows: Internal Notebook Summary tool for context management.
  - Cell preview in run confirmation: Preview notebook cell code when agent requests run confirmation.

- **Source Control**
  - Copilot coding agent integration: Assign and track tasks for Copilot agent in GitHub Pull Requests extension.
  - Source control history item details: View resources of history items in Graph view, with tree/list options and multi-file diff.
  - Add history item to chat context: Add commit or PR contents as context for chat prompts.

- **Tasks**
  - Instance policy: New `instancePolicy` property for task runOptions, controlling behavior when instance limit is reached.

- **Terminal**
  - Language server based terminal suggest: LSP completions in Python REPL sessions, with settings for shell integration and analysis.

- **Remote Development**
  - SSH pre-connection script and Remote Explorer improvements.

- **Python Extension**
  - New chat tools: Get environment info, install packages, configure environment, with seamless context detection.
  - Project creation from template: Create Python packages/scripts with scaffolding and environment setup.
  - PyEnv and Poetry support: Enhanced environment and package management.

- **GitHub Pull Requests Extension**
  - Images in comments from private repos, improved notifications, timeline links open in VS Code, Copilot session actions, and query management.

- **Extension Authoring**
  - Secret scanning in VSCE: Error on packaging if secrets detected, with flags to bypass checks.
  - Web environment detection: Node.js extension host update, navigator global object support, and migration guidance.

- **Proposed APIs**
  - Authentication Providers: Declare supported authorization servers for MCP, with activation and registration examples.

- **Engineering**
  - Electron 35 update: Chromium and Node.js version upgrades.
  - ESM adoption: Real-world extension migration and bundler configuration guidance.

- **Notable Fixes and Contributions**
  - Numerous bug fixes, improvements, and community contributions across VS Code and related extensions.
