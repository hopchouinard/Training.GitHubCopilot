---
Order: 110
TOCTitle: May 2025
PageTitle: Visual Studio Code May 2025
MetaDescription: Learn what is new in the Visual Studio Code May 2025 Release (1.101)
MetaSocialImage: 1_101/release-highlights.png
Date: 2025-06-12
DownloadVersion: 1.101.2
---
# May 2025 (version 1.101)

## _Release date: June 12, 2025_

**Security update**: The following extension has security updates: [ms-python.python](https://marketplace.visualstudio.com/items?itemName=ms-python.python).

**Update 1.101.1**: The update addresses these [issues](https://github.com/microsoft/vscode/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22May+2025+Recovery+1%22+).

**Update 1.101.2**: The update addresses these [issues](https://github.com/microsoft/vscode/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22May+2025+Recovery+2%22+).

<!-- DOWNLOAD_LINKS_PLACEHOLDER -->

---

Welcome to the May 2025 release of Visual Studio Code. There are many updates in this version that we hope you'll like, some of the key highlights include:

* **MCP**
  * Expand your agent coding flow with support for prompts, resources, and sampling ([Show more](#mcp-support-for-prompts)).
  * Access MCP servers that require authentication ([Show more](#mcp-support-for-auth)).
  * Debug MCP servers with development mode ([Show more](#mcp-development-mode)).
  * Publish MCP servers from an extension ([Show more](#mcp-extension-apis)).

* **Chat**
  * Group and manage related tools by combining them in a tool set ([Show more](#chat-tool-sets)).

* **Source Control**
  * View files in Source Control Graph view ([Show more](#source-control-history-item-details)).
  * Assign and track work for GitHub Copilot Coding Agent from within VS Code ([Show more](#copilot-coding-agent-integration)).

>If you'd like to read these release notes online, go to [Updates](https://code.visualstudio.com/updates) on [code.visualstudio.com](https://code.visualstudio.com).
**Insiders:** Want to try new features as soon as possible? You can download the nightly [Insiders](https://code.visualstudio.com/insiders) build and try the latest updates as soon as they are available.

## Chat

### Chat tool sets

VS Code now enables you to define tool sets, either through a proposed API or through the UI. A tool set is a collection of different tools that can be used just like individual tools. Tool sets make it easier to group related tools together, and quickly enable or disable them in agent mode. For instance, the tool set below is for managing GitHub notifications (using the [GitHub MCP server](https://github.com/github/github-mcp-server)).

```json
{
  "gh-news": {
    "tools": [
      "list_notifications",
      "dismiss_notification",
      "get_notification_details",
    ],
    "description": "Manage GH notification",
    "icon": "github-project"
  }
}
```

To create a tool set, run the **Configure Tool Sets** > **Create new tool sets file** command from the Command Palette. You can then select the tools you want to include in the tool set, and provide a description and icon.

To use a tool set in a chat query, reference it by #-mentioning its name, like `#gh-news`. You can also choose it from the tool picker in the chat input box.

![Screenshot of the Chat view showing a query about unread notifications, using the 'gh-news' tool set highlighted in both the chat interface and a JSON configuration file which defines this tool set.](images/1_101/tool-set-gh.png)

Learn more about [tool sets](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode#_define-tool-sets) in our documentation.

### MCP support for prompts

VS Code's Model Context Protocol support now includes prompt support. Prompts can be defined by MCP servers to generate reusable snippets or tasks for the language model. Prompts are accessible as slash `/` commands in chat, in the format `/mcp.servername.promptname`. You can enter plain text or include command output in prompt variables, and we also support completions when servers provide it.

The following example shows how we generate a prompt using AI, save it using the [Gistpad MCP server](https://github.com/lostintangent/gistpad-mcp), and then use it to generate a changelog entry:

<video src="images/1_101/mcp-prompts.mp4" autoplay loop controls muted></video>

### MCP support for resources

VS Code's Model Context Protocol support now includes resource support, which includes support for resource templates. It is available in several places:

1. Resources returned from MCP tool calls are available to the model and can be saved in chat, either via a **Save** button or by dragging the resource onto the Explorer view.
1. Resources can be attached as context via the **Add Context...** button in chat, then selecting **MCP Resources...**.
1. You can browse and view resources across servers using the **MCP: Browse Resources** command or for a server by its entry in the **MCP: List Servers** command.

Here's an example of attaching resources from the [Gistpad MCP server](https://github.com/lostintangent/gistpad-mcp) to chat:

<video src="images/1_101/mcp-resources.mp4" autoplay loop controls muted></video>

### MCP support for sampling (Experimental)

VS Code's Model Context Protocol support now includes sampling, which allows MCP servers to make requests back to the model. You'll be asked to confirm the first time an MCP server makes a sampling request, and you can configure the models the MCP server has access to as well as see a request log by selecting the server in **MCP: List Servers.**

<video src="images/1_101/mcp-sampling.mp4" autoplay loop controls muted></video>

Sampling support is still preliminary and we plan to expand and improve it in future iterations.

### MCP support for auth

VS Code now supports MCP servers that require authentication, allowing you to interact with an MCP server that operates on behalf of your user account for that service.

This feature implements the MCP authorization specification for clients, and supports both:

* [2025-3-26 spec](https://modelcontextprotocol.io/specification/2025-03-26/basic/authorization), where the MCP server behaves as an authorization server.
* [Draft spec](https://modelcontextprotocol.io/specification/draft/basic/authorization), where the MCP server behaves as a resource server (this is expected to be finalized any day now).

If the MCP server implements the draft spec and leverages GitHub or Entra as the auth server, you can manage which MCP servers have access to your account:

![Screenshot of the "Manage Trusted MCP Servers" option in the account menu.](images/1_101/manage-trusted-mcp.png)

![Screenshot of the "Manage Trusted MCP Servers" Quick Pick.](images/1_101/manage-trusted-mcp-quick-pick.png)

You can also manage which account that server should use (via the gear button in the previous quick pick):

![Screenshot of the "Account Preference" Quick Pick.](images/1_101/account-pref-quick-pick.png)

For other MCP servers that rely on dynamic client registration, we include the auth state in the same place as everything else, for example with Linear:

![Screenshot of Linear appearing in the account menu.](images/1_101/linear-account-menu.png)

There you can also sign out. For these we support not only the code authorization flow but also the device code flow should your authorization server support it.

We have also introduced the command `Authentication: Remove Dynamic Authentication Providers` that allows you to clean up any of these dynamic client registrations. This will throw away the client id issued to VS Code and all data associated with this authentication provider.

Remember, you can use the **MCP: Add Server...** command to add MCP servers. This is the same entry point for servers with authentication.

### MCP development mode

You can enable _development mode_ for MCP servers by adding a `dev` key to the server config. This is an object with two properties:

* `watch`: A file glob pattern to watch for files change that will restart the MCP server.
* `debug`: Enables you to set up a debugger with the MCP server. Currently, we only support debugging Node.js and Python servers launched with `node` and `python` respectively.

#### **.vscode/mcp.json**

```diff
{
  "servers": {
    "gistpad": {
      "command": "node",
      "args": ["build/index.js"],
+     "dev": {
+       "watch": "build/**/*.js",
+       "debug": { "type": "node" }
+     },
```

### Chat UX improvements

We're continuously working to improve the chat user experience in VS Code based on your feedback. One such feedback was that it can be difficult to distinguish between user messages and AI responses in the chat. To address this, we've made the appearance of user messages more distinct.

Undoing previous requests is now also more visible - just hover over a request and select the `X` button to undo that request and any following requests. Or even quicker, use the `kb(workbench.action.chat.undoEdits)` keyboard shortcut!

Finally, attachments from the chat input box are now more navigable.

<video src="images/1_101/new-chat-ui-ux.mp4" title="A video of the new chat UI/UX where a request is removed to undo edits since that point." autoplay loop controls muted></video>

Learn more about using [chat in VS Code](https://code.visualstudio.com/docs/copilot/chat/copilot-chat) in our documentation.

### Apply edits more efficiently

When editing files, VS Code can take two different approaches: it either rewrites the file top to bottom or it makes multiple, smaller edits. Both approaches differ, for example the former can be slower for large files and intermediate states do often not compile successfully. Because of that the UI adopts and conditionally disables auto-save and squiggles, but only when needed.

We have also aligned the keybindings for the **Keep** and **Undo** commands. Keeping and undoing individual changes is now done with `kb(chatEditor.action.acceptHunk)` and `kb(chatEditor.action.undoHunk)`. In the same spirit, we have also aligned the keybinding for keeping and undoing all changes in a file, they are now `kb(chatEditor.action.accept)` and `kb(chatEditor.action.reject)`. This is not just for alignment but also removes prior conflicts with popular editing commands (like **Delete All Left**).

### Implicit context

We've streamlined and simplified the way that adding your current file as context works in chat. Many people found the "eyeball toggle" that we previously had to be a bit clunky. Now, your current file is offered as a suggested context item. Just select the item to add or remove it from chat context. From prompt input field, press `Shift+Tab, Enter` to quickly do this with the keyboard.

Additionally, in agent mode, we include a hint about your current editor. This doesn't include the contents of the file, just the file name and cursor position. The agent can then use the tools it has to read the contents of the file on its own, if it thinks that it's relevant to your query.

<video src="images/1_101/implicit-context-flow.mp4" title="A video of the current open editor being suggest as implicit context and added as an attachment." autoplay loop controls muted></video>

Learn more about [adding context in chat](https://code.visualstudio.com/docs/copilot/chat/copilot-chat-context) in our documentation.

### Fix task configuration errors

Configuring tasks and problem matchers can be tricky. Use the **Fix with Github Copilot** action that is offered when there are errors in your task configuration to address them quickly and efficiently.

### Custom chat modes (Preview)

By default, the chat view supports three built-in chat modes: Ask, Edit and Agent. Each chat mode comes with a set of base instructions that describe how the LLM should handle a request, as well as the list of tools that can be used for that.

You can now define your own custom chat modes, which can be used in the Chat view. Custom chat modes allow you to tailor the behavior of chat and specify which tools are available in that mode. This is particularly useful for specialized workflows or when you want to provide specific instructions to the LLM. For example, you can create a custom chat mode for planning new features, which only has read-only access to your codebase.

To define and use a custom chat mode, follow these steps:

1. Define a custom mode by using the **Chat: Configure Chat Modes** command from the Command Palette.
1. Provide the instructions and available tools for your custom chat mode in the `*.chatprompt.md` file that is created.
1. In the Chat view, select the chat mode from the chat mode dropdown list.
1. Submit your chat prompt.

![Screenshot of the custom chat mode selected in the Chat view.](images/1_101/custom-chat-mode-view.png)

The following example shows a custom "Planning" chat mode:

```md
---
description: Generate an implementation plan for new features or refactoring existing code.
tools: ['codebase', 'fetch', 'findTestFiles', 'githubRepo', 'search', 'usages']
---
# Planning mode instructions
You are in planning mode. Your task is to generate an implementation plan for a new feature or for refactoring existing code.
Don't make any code edits, just generate a plan.

The plan consists of a Markdown document that describes the implementation plan, including the following sections:

* Overview: A brief description of the feature or refactoring task.
* Requirements: A list of requirements for the feature or refactoring task.
* Implementation Steps: A detailed list of steps to implement the feature or refactoring task.
* Testing: A list of tests that need to be implemented to verify the feature or refactoring task.
```

> **Note**: The feature is work in progress, but please try it out! Please follow the latest progress in VS Code Insiders and let us know what's not working or is missing.

### Task diagnostic awareness

When the chat agent runs a task, it is now aware of any errors or warnings identified by problem matchers. This diagnostic context allows the chat agent to respond more intelligently to issues as they arise.

### Terminal cwd context

When agent mode has opened a terminal and shell integration is active, the chat agent is aware of the current working directory (cwd). This enables more accurate and context-aware command support.

### Floating window improvements

When you move a chat session into a floating window, there are now two new actions available in the title bar:

* Dock the chat back into the VS Code window where it came from
* Start a new chat session in the floating window.

![Screenshot of the Chat view in a floating window, highlighting the Dock and New Chat buttons in the title bar.](images/1_101/chat-floating.png)

### Fetch tool confirmation

The fetch tool enables you to pull information from a web page. We have added a warning message to the confirmation to inform you about potential prompt injection.

![Screenshot of the fetch tool with a warning about prompt injection.](images/1_101/fetch-warning.png)

### Customize more built-in tools

It's now possible to enable or disable all built-in tools in agent mode or your custom mode. For example, disable `editFiles` to disallow agent mode to edit files directly, or `runCommands` for running terminal commands.

In agent mode, select the **Configure Tools** button to open the tool picker, and select your desired set of tools.

![Screenshot of the tool picker, showing the "editFiles" tool set item cleared.](images/1_101/built-in-toolsets.png)

Some of the entries in this menu represent tool sets that group multiple tools. For example, we give the model multiple tools to edit or create text files and notebooks, which may also differ by model family, and `editFiles` groups all of these.

### Send elements to chat (Experimental)

Last milestone, we added a [new experimental feature](https://code.visualstudio.com/updates/v1_100#_select-and-attach-ui-elements-to-chat-experimental) where you could open the Simple Browser and select web elements to add to chat from the embedded browser.

![Screenshot showing the Live Preview extension, highlighting the overlay controls to select web elements from the web page.](images/1_101/live-preview-select-web-elements.png)

As we continue to improve this feature, we have added support for selecting web elements in the [Live Preview extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server) as well. Check this out by downloading the extension and spinning up a live server from any HTML file.

## Accessibility

### User action required sound

We’ve added an accessibility signal to indicate when chat requires user action. This is opt-in as we fine tune the sound. You can configure this behavior with `setting(accessibility.signals.chatUserActionRequired)`.

### New code action sounds

We’ve introduced distinct sounds for:

* when a code action is triggered: `setting(accessibility.signals.codeActionTriggered)`
* when a code action is applied: `setting(accessibility.signals.codeActionApplied)`

### Agent mode accessibility improvements

We now include rich information about confirmation dialogs in the accessible view, covering past tool runs, the current tool run, and any pending confirmations. This includes the inputs that will be used.

When a confirmation dialog appears in a response, the action’s title is now included in the ARIA label of the corresponding code block, the response’s ARIA label, and the live alert to provide better context for screen reader users.

## Editor Experience

### Find as you type

**Setting**: `setting(editor.find.findOnType:true)`

Find-as-you-type has been the default behavior of the Find control, but now you can control whether to keep it that way or disable it so that it will only perform the search after hitting enter.

### Custom menus with native window title bar

**Setting**: `setting(window.menuStyle)`

You can now specify the menu style that is used for the menu bar and context menus on Windows and Linux, and for context menus on macOS by using the `setting(window.menuStyle)` setting:

* `native`: rendered by the OS
* `custom`: rendered by VS Code
* `inherit`: matches the style of the title bar as set by `setting(window.titleBarStyle)` (lets you use a native title bar with a custom menu bar and context menus).

### Linux native window context menu

We now support the native window context menu when you right-click on the application icon in the custom title bar.

![Screenshot of the native window context menu over the custom title bar.](images/1_101/linux-os-title-menu.png)

### Process explorer web support

The process explorer was converted to use the floating window infrastructure that we have in the workbench for editor windows. As a result, this also means that we now support the process explorer in web when connected to a remote (for example in Codespaces).

![Screenshot of the VS Code process explorer in a floating window.](images/1_101/process-explorer.png)

### Windows shell environment discovery

We have now implemented shell environment discovery for PowerShell on Windows. This means that VS Code inherits any environment configured in the PowerShell profiles, such as the PATH updates that Node.js configures through various version managers.

### Unpublished extension warning

Installed extensions now show a warning indicator when they're no longer available in the Marketplace, helping you identify potentially problematic extensions that were unpublished or removed.

![Screenshot of an extension with a warning indicator and a message indicating it's no longer available in the Marketplace.](images/1_101/pulled-extension.png)

### Settings search suggestions (Preview)

**Setting**: `setting(workbench.settings.showAISearchToggle:true)`

This milestone, we added a toggle to the Settings editor that starts an AI search to find semantically similar results instead of results that are based on string matching. For example, the AI search finds the `editor.fontSize` setting when you search for "increase text size".

To see the toggle, enable the setting and reload VS Code. We are also in the process of identifying and fixing some of the less accurate settings search results, and we welcome feedback on when a natural language query did not find an expected setting.

For the next milestone, we are also considering removing the toggle and changing the experimental setting to one that controls when to directly append the slower AI search results to the end of the list.

<video src="images/1_101/settings-editor-ai-search.mp4" title="Video showing AI search in the Settings editor that finds the `editor.fontSize` setting when you search 'increase text size'." autoplay loop controls muted></video>

### Search keyword suggestions (Preview)

**Setting**: `setting(search.searchView.keywordSuggestions)`

Last milestone, we introduced [keyword suggestions](https://code.visualstudio.com/updates/v1_100#_semantic-text-search-with-keyword-suggestions-experimental) in the Search view to help you find relevant results faster. We have now significantly improved the performance of the suggestions, so you will see the results ~5x faster than before.

We have also moved the setting from the Chat extension into VS Code core, and renamed it from `github.copilot.chat.search.keywordSuggestions` to `setting(search.searchView.keywordSuggestions)`.

### Semantic search behavior options (Preview)

**Setting**: `setting(search.searchView.semanticSearchBehavior)`

With semantic search in the Search view, you can get results based on the meaning of your query rather than just matching text. This is particularly useful if you don't know the exact terms to search for.

By default, semantic search is only run when you explicitly request it. We have now added a setting to control when you want semantic search to be triggered:

* `manual` (default): only run semantic search when triggered manually from the UI (`kb(search.action.searchWithAI)`)
* `runOnEmpty`: run semantic search automatically when the text search returns no results
* `auto`: always run semantic search in parallel with text search for every search query

### Edit Context

**Setting**: `setting(editor.editContext)`

We have enabled the `setting(editor.editContext)` setting by default on Stable. This means that the input of the editor is now powered by the EditContext API. This fixes numerous bugs, especially in relation to the IME experience, and going forward will pave the way for a more versatile and robust input experience within the editor.

See the [MDN docs](https://developer.mozilla.org/en-US/docs/Web/API/EditContext_API) for more detail on the EditContext API.

## Code Editing

### NES import suggestions

**Setting**: `setting(github.copilot.nextEditSuggestions.fixes)`

Last month, we introduced support for next edit suggestions to automatically suggest adding missing import statements for TypeScript and JavaScript. In this release, we've improved the accuracy and reliability of these suggestions and expanded support to Python files as well.

![Screenshot showing NES suggesting an import statement.](images/1_100/nes-import.png)

NES is enabled for all VS Code Insiders users, and it will progressively be enabled by default for Stable users during June. You can enable NES yourself via its setting at any time.

### NES acceptance flow

Accepting next edit suggestions is now more seamless with improved keyboard navigation. Once you accept a suggestion, you can continue accepting subsequent suggestions with a single `kbstyle(Tab)` press, as long as you haven't started typing again. Once you start typing, press `kbstyle(Tab)` to first move the cursor to the next suggestion before you can accept it.

## Notebooks

### Follow mode for agent cell execution

**Setting**: `setting(github.copilot.chat.notebook.followCellExecution.enabled)`

With follow mode, the Notebook view will automatically scroll to the cell that is currently being executed by the agent. Use the `setting(github.copilot.chat.notebook.followCellExecution.enabled)` setting to enable or disable follow mode for agent cell execution in Jupyter Notebooks.

Once the agent has used the run cell tool, the Notebook toolbar is updated with a pin icon, indicating the state of follow mode. You can toggle the behavior mid agent response without changing the base setting value, allowing you to follow the work of the agent in real-time, and toggle it off when you want to review a specific portion of code while the agent continues to iterate. When you wish to follow again, simply toggle the mode, and join at the next execution.

<video src="images/1_101/notebook-follow-mode.mp4" title="Video that shows the AI executing cells in a notebook with follow mode enabled. When the cell is run, the notebook scrolls to reveal it." autoplay loop controls muted></video>

### Notebook tools for agent mode

#### Configure notebook

The [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) contributes tools for configuring the Kernel of a Jupyter Notebook. This tool ensures that a Kernel is selected and is ready for use in the Notebook.
This involves walking you through the process of creating a Virtual Environment if required (the recommended approach), or prompting you to select an existing Python environment.

This tool ensures the LLM can perform operations on the Notebook such as running cells with minimal user interaction, thereby improving the overall user experience in agent mode.

<video src="images/1_101/notebook-tools.mp4" title="Video that shows the AI configuring the Python environment, installing dependencies and finally running notebook cells." autoplay loop controls muted></video>

#### Long running agent workflows

The agent has access to an internal Notebook Summary tool to help keep it on track with an accurate context. That summary is also included when summarizing the conversation history when the context gets too large to keep the agent going through complex operations.

#### Cell preview in run confirmation

A snippet of the code is shown from a notebook cell when the agent requests confirmation to run that cell. The cell links in the Chat view now also enable you to directly navigate to cells in the notebook.

<video src="images/1_101/run-cell-confirmation.mp4" title="Video showing the AI asking to run a cell including a link to the cell and a preview of its content." autoplay loop controls muted></video>

## Source Control

### Copilot coding agent integration

With Copilot coding agent, GitHub Copilot can work independently in the background to complete tasks, just like a human developer. We have expanded the GitHub Pull Requests extension to make it easier to assign and track tasks for the agent from within VS Code.

We have added the following features to the extension:

* **Assign to Copilot**: assign a pull request or issue to Copilot from the issue or PR view in VS Code
* **Copilot on My Behalf** PR query: quickly see all pull requests that Copilot is working on for you.
* **PR view**: see the status of the Copilot coding agent and open the session details in the browser.

![Screenshot showing the GitHub Pull Requests view, highlighting the assign to Copilot action, and the PR query for work assigned to Copilot.](images/1_101/github-pull-request-coding-agent.png)

### Source control history item details

Upon popular demand, selecting an item in the Source Control Graph view now reveals the resources of that history item. You can choose between a tree view or list view representation from the `...` menu.

<video src="images/1_101/source-control-graph-view-resources.mp4" title="Video showing the Source Control Graph view, displaying the files for a commit and showing a diff editor of its changes." autoplay loop controls muted></video>

To open all resources of a history item in the multi-file diff editor, use the **Open Changes** action on hover. Selecting a particular resource from the Graph view opens a diff editor only for that resource. Select the **Open File** action to open the file for that particular version.

### Add history item to chat context

You can now add a source control history item as context to a chat request. This can be useful when you want to provide the contents of a specific commit or pull request as context for your chat prompt.

![Screenshot of the Chat view input box that has a history item added as context.](images/1_101/chat-context-source-control-commit.png)

To add a history item to chat, use **Add Context** > **Source Control** from the Chat view and then choose a particular history item. Alternatively, right-click the history item in the source control graph and then select **Copilot** > **Add History Item to Chat** from the context menu.

## Tasks

### Instance policy

Task `runOptions` now has an `instancePolicy` property, which determines what happens when a task has reached its `instanceLimit`.

Options include `prompt` (default), `silent`, `terminateNewest`, `terminateOldest`, and `warn`.

![Screenshot showing an `instancePolicy` being configured in a `tasks.json` file and displays the options with prompt as the default value.](images/1_101/instancePolicy.png)

## Terminal

### Language server based terminal suggest

Language server completions are now available in the terminal for interactive Python REPL sessions.
This brings the same language completions you receive in the editor now inside the terminal.
We are starting with support for Python via Pylance, with plans to expand to more languages in the future.

<video src="images/1_101/lsp_completions.mp4" title="Video that shows completions from LSP in REPL in the terminal." autoplay loop controls muted></video>

To try it out, ensure the following settings are enabled:

* `setting(terminal.integrated.shellIntegration.enabled:true)`
* `setting(python.terminal.shellIntegration.enabled:true)`
* `setting(terminal.integrated.suggest.enabled:true)`
* `setting(python.analysis.supportAllPythonDocuments:true)`

## Remote Development

The [Remote Development extensions](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack), allow you to use a [Dev Container](https://code.visualstudio.com/docs/devcontainers/containers), remote machine via SSH or [Remote Tunnels](https://code.visualstudio.com/docs/remote/tunnels), or the [Windows Subsystem for Linux](https://learn.microsoft.com/windows/wsl) (WSL) as a full-featured development environment.

Highlights include:

* SSH pre-connection script
* Remote Explorer improvements

You can learn more about these features in the [Remote Development release notes](https://github.com/microsoft/vscode-docs/blob/main/remote-release-notes/v1_101.md).

## Contributions to extensions

### Python

#### Python chat tools

The [Python Extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) now includes the following chat tools: “Get information for a Python Environment”, “Get executable information for a Python Environment”, “Install Python Package” and “Configure Python Environment”. You can either directly reference them in your prompt by adding `#getPythonEnvironmentInfo` `#installPythonPackage`, or agent mode will automatically call the tool as applicable. These tools seamlessly detect appropriate environment information, based on file or workspace context, and handle package installation with accurate environment resolution.

The “Configure Python Environment” tool ensures that the Python Environment is set up correctly for the workspace. This includes creating a Virtual Environment if needed, and selecting that as the active Python Environment for the workspace.

Tools that were previously introduced in the [Python Environments](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs) extension (preview) have been migrated to the Python extension, thereby making these tools available to all users with the Python extension installed.

<video src="images/1_101/python-tools.mp4" title="Video demoing the Python tools called implicitly by the model in agent mode." autoplay loop controls muted></video>

#### Create a project from a template

The [Python Environments extension](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs) now supports project creation for Python packages and basic scripts, allowing you to bypass scaffolding and get coding more quickly. Use the command **Python Envs: Create Project from Template** to select whether you want to create a package or a script.

For package creation, you are able to name the package, create a virtual environment, and receive a scaffolded project which includes a tests subfolder, `pyproject.toml`, `dev-requirements.txt`, and boilerplate `__main__.py` and `__init__.py` files.

For scripts, it creates a new python file with the name of your choice and include boilerplate code.

#### PyEnv and Poetry support

We added support for `pyenv` for environment management, and `poetry` for both package and environment management in the [Python Environments](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs) extension.

### GitHub Pull Requests

There has been more progress on the [GitHub Pull Requests](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) extension, which enables you to work on, create, and manage pull requests and issues. New features include:

* Images in comments from private repositories are now shown in pull request file comments.
* The "Notifications" view is now shown by default, collapsed.
-- Issue and pull request links in the timeline an in the issue/pull request body are now opened in VS Code, rather than going to the browser.
* The "Assigned to Me" query in the "Pull Requests" view has been removed, and the "Local Pull Request Branches" and "All Open" queries can be removed using the setting `githubPullRequests.queries`. For repositories with Copilot, a "Copilot on My Behalf" query is added when the setting is unconfigured.
* Copilot "start working", "stop working", and "View Session" are now shown in the timeline.

Review the [changelog for the 0.112.0](https://github.com/microsoft/vscode-pull-request-github/blob/main/CHANGELOG.md#01120) release of the extension to learn about the other highlights.

## Extension Authoring

### MCP extension APIs

Extensions can now publish collections of MCP servers. This enables you to bundle MCP servers with your extension or build extensions that dynamically discover MCP servers from other sources. Learn more in our [MCP extension development guide](https://code.visualstudio.com/api/extension-guides/mcp) or by checking out the [MCP extension sample](https://github.com/microsoft/vscode-extension-samples/blob/main/mcp-extension-sample).

### Secret scanning when packaging extensions

VSCE now scans for secrets when packaging your extension. If any potential secrets (for example, API keys, tokens, credentials, or environment variable files like `.env`) are detected in your source files, VSCE displays an error during the packaging process. This helps you avoid accidentally publishing sensitive information to the Marketplace. Make sure to review and address any error before publishing your extension.

If you need to bypass specific checks, you can use the `--allow-package-secrets <secret_type>` or `--allow-package-env-file` flags when running VSCE. These flags let you configure which secret or environment file checks should be skipped during packaging.

### Web environment detection

⚠️ Breaking change ⚠️

**Setting**: `setting(extensions.supportNodeGlobalNavigator)`

The Node.js extension host is now updated to v22 from v20, as part of our [Electron 35 runtime update](#electron-35-update). This update brings in support for the [`navigator` global object](https://github.com/nodejs/node/commit/b40f0c30743aaecd57071f7be305df43e1083817) in the desktop and remote extension hosts.

This change could introduce a breaking change for extensions that rely on the presence of the `navigator` object to detect the web environment.

To help extension authors migrate, we have created a polyfill for `globalThis.navigator` that is initialized to `undefined`, so your extension continues to work correctly. The polyfill is behind the `setting(extensions.supportNodeGlobalNavigator)` VS Code setting. By default, this setting is disabled and the polyfill is in place. We capture telemetry and log an error (in extension development mode) when your extension tries to access the `navigator` in this way.

In the future, this setting might be enabled by default, so we urge extension authors to migrate their code to be compatible with the new `navigator` global object. Follow these steps to migrate your code:

* Check the extension host log for a `PendingMigrationError` that has error stack originating your extension.
* Ensure checks like `typeof navigator === 'object'` are migrated to `typeof process === 'object' && process.versions.node` as needed.
* Enable `setting(extensions.supportNodeGlobalNavigator)`.
* Verify extension behavior remains unchanged.

## Proposed APIs

### Authentication Providers: Supported Authorization Servers for MCP

Currently only leveraged in [MCP authentication](#mcp-support-for-auth), this API proposal enables your `AuthenticationProvider` to declare the authorization servers that are associated with it.

For example, if you look at the GitHub Authentication Provider, it includes the typical GitHub authorization URL in the authorizationServerGlobs property of [the auth provider contribution](https://github.com/microsoft/vscode/blob/c9f19f8ad20aa88b1d924c8f7ff8d6b9f6269be8/extensions/github-authentication/package.json#L35-L41):

```json
{
  "label": "GitHub",
  "id": "github",
  "authorizationServerGlobs": [
    "https://github.com/login/oauth"
  ]
}
```

This property is used for activation of your extension - if the requested authorization server matches, your extension will be activated.

Additionally, when registering the authentication provider, you MUST include the finalized authorization server URL globs. Just like [what GitHub Authentication does here](https://github.com/microsoft/vscode/blob/c9f19f8ad20aa88b1d924c8f7ff8d6b9f6269be8/extensions/github-authentication/src/github.ts#L144-L149):

```ts
vscode.authentication.registerAuthenticationProvider(
 type,
 this._githubServer.friendlyName,
 this,
 {
  supportsMultipleAccounts: true,
  supportedAuthorizationServers: [
   ghesUri ?? vscode.Uri.parse('https://github.com/login/oauth')
  ]
 }
);
```

For a more complex example, look to Microsoft Authentication. The authorization server depends on the tenant being placed in the path. So for this, we use a wildcard [in the contribution](https://github.com/microsoft/vscode/blob/c9f19f8ad20aa88b1d924c8f7ff8d6b9f6269be8/extensions/microsoft-authentication/package.json#L33-L39):

```json
{
  "label": "Microsoft",
  "id": "microsoft",
  "authorizationServerGlobs": [
    "https://login.microsoftonline.com/*/v2.0"
  ]
},
```

and [in the registration](https://github.com/microsoft/vscode/blob/c9f19f8ad20aa88b1d924c8f7ff8d6b9f6269be8/extensions/microsoft-authentication/src/extensionV2.ts#L78-L88):

```ts
authentication.registerAuthenticationProvider(
 'microsoft',
 'Microsoft',
 authProvider,
 {
  supportsMultipleAccounts: true,
  supportedAuthorizationServers: [
   Uri.parse('https://login.microsoftonline.com/*/v2.0')
  ]
 }
)
```

Then, when a caller passes in an authorization server URL when it asks for auth, it is passed down to both the `getSessions` and `createSession` functions via the `AuthenticationProviderSessionOptions` that are already present.

As mentioned, this functionality is currently used in MCP support, where we receive the authorization server URL to authenticate with from the MCP server. That URL is then mapped to an auth provider, or if none exists, an auth provider is dynamically created for that auth server.

The full API proposal can be found [in the vscode repo](https://github.com/microsoft/vscode/blob/c9f19f8ad20aa88b1d924c8f7ff8d6b9f6269be8/src/vscode-dts/vscode.proposed.authIssuers.d.ts) and we'd love to hear your feedback in the [GitHub issue](https://github.com/microsoft/vscode/issues/248775)!

## Engineering

### Electron 35 update

In this milestone, we are promoting the Electron 35 update to users on our Stable release. This update comes with Chromium 134.0.6998.205 and Node.js 22.15.1. We want to thank everyone who self-hosted on Insiders builds and provided early feedback.

### Adopting ESM in a real-world extension

Last milestone, we have announced support for JavaScript-modules (ESM). This enables extensions to use `import` and `export` statements, but currently only when targeting the NodeJS extension host.

This month, we have done a real-world adoption with [GitHub Issue Notebooks](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-github-issue-notebooks). It is not trivial because this extension can be run in the NodeJS extension host (which supports ESM extensions) and the web worker extension host, which currently does not support ESM extensions. This required a more complex bundler configuration and you might want to take inspiration from its [esbuild-config](https://github.com/microsoft/vscode-github-issue-notebooks/blob/main/esbuild.mjs).

## Notable fixes

* [250077](https://github.com/microsoft/vscode/issues/250077) - Tree-Sitter based syntax highlighting depends on the model service

## Thank you

Last but certainly not least, a big _**Thank You**_ to the contributors of VS Code.

### Issue tracking

Contributions to our issue tracking:

* [@gjsjohnmurray (John Murray)](https://github.com/gjsjohnmurray)
* [@albertosantini (Alberto Santini)](https://github.com/albertosantini)
* [@RedCMD (RedCMD)](https://github.com/RedCMD)
* [@IllusionMH (Andrii Dieiev)](https://github.com/IllusionMH)

### Pull requests

Contributions to `vscode`:

* [@alpalla (Alessio Palladino)](https://github.com/alpalla): Add a task instancePolicy to task runOptions  [PR ##117129](https://github.com/microsoft/vscode/pull/117129)
* [@0xEbrahim (Ebrahim El-Sayed)](https://github.com/0xEbrahim): Fix Typo and Grammar [PR #248814](https://github.com/microsoft/vscode/pull/248814)
* [@a-stewart (Anthony Stewart)](https://github.com/a-stewart): For editor font choice, if OS is not detected assume Linux [PR #248133](https://github.com/microsoft/vscode/pull/248133)
* [@adnval (kevin)](https://github.com/adnval): Add installed filter [PR #248055](https://github.com/microsoft/vscode/pull/248055)
* [@bhack](https://github.com/bhack): Add to new source format and the mandatory signed-by [PR #239390](https://github.com/microsoft/vscode/pull/239390)
* [@dylanchu](https://github.com/dylanchu): TerminalTaskSystem: Add support for nushell [PR #238440](https://github.com/microsoft/vscode/pull/238440)
* [@eronnen (Ely Ronnen)](https://github.com/eronnen)
  * make maximum number of lines in debug console configurable [PR #245915](https://github.com/microsoft/vscode/pull/245915)
  * Update log tmLanguage from vscode-logfile-highlighter 3.4.1 [PR #249046](https://github.com/microsoft/vscode/pull/249046)
  * Disassembly View: don't display invalid memory instructions [PR #249779](https://github.com/microsoft/vscode/pull/249779)
  * disasembly view: handle negative line height returned by debug adapter [PR #250081](https://github.com/microsoft/vscode/pull/250081)
* [@gabritto (Gabriela Araujo Britto)](https://github.com/gabritto): [typescript-language-features] Add configuration for maximum hover length [PR #248181](https://github.com/microsoft/vscode/pull/248181)
* [@hickford (M Hickford)](https://github.com/hickford): Highlight active line number correctly regardless of word wrap [PR #240029](https://github.com/microsoft/vscode/pull/240029)
* [@imfing (Xin)](https://github.com/imfing): fix: conditionally append scope parameter in authorization URL for DynamicAuthProvider [PR #250084](https://github.com/microsoft/vscode/pull/250084)
* [@jeanp413 (Jean Pierre)](https://github.com/jeanp413)
  * Fix timeline git requests are not cancelled when switching editors too fast [PR #244335](https://github.com/microsoft/vscode/pull/244335)
  * Fix vscode.env.onDidChangeShell not firing in the webworker extension host [PR #249824](https://github.com/microsoft/vscode/pull/249824)
* [@joyceerhl (Joyce Er)](https://github.com/joyceerhl)
  * refactor: reuse chat attachment widgets in chat list renderer [PR #248163](https://github.com/microsoft/vscode/pull/248163)
  * fix: register widgets in chat attachments content part [PR #249054](https://github.com/microsoft/vscode/pull/249054)
  * fix: set content reference description on historical chat attachments [PR #249112](https://github.com/microsoft/vscode/pull/249112)
  * fix: use markdown string for MCP tool confirmation [PR #249497](https://github.com/microsoft/vscode/pull/249497)
  * fix: allow Continue On if edit session identity provider mutates edit session payload [PR #250057](https://github.com/microsoft/vscode/pull/250057)
* [@JoyceGu (Joyce Gu)](https://github.com/JoyceGu): Joycegu/add genai packages 05222025 [PR #249589](https://github.com/microsoft/vscode/pull/249589)
* [@mawosoft (Matthias Wolf)](https://github.com/mawosoft): Fix PowerShell shell integration when strict mode is enabled. [PR #248625](https://github.com/microsoft/vscode/pull/248625)
* [@mortalYoung (野迂迂)](https://github.com/mortalYoung): fix(search): fix expand all not working [PR #248207](https://github.com/microsoft/vscode/pull/248207)
* [@nojaf (Florian Verdonck)](https://github.com/nojaf): Close all unused ports command [PR #244245](https://github.com/microsoft/vscode/pull/244245)
* [@nomike (nomike)](https://github.com/nomike): Enhance GithHub publishing logic to handle renamed repositories [PR #245024](https://github.com/microsoft/vscode/pull/245024)
* [@Parasaran-Python (Parasaran)](https://github.com/Parasaran-Python): Fix #248222 | Regex changes to allow multiple leading dots in relative paths [PR #248340](https://github.com/microsoft/vscode/pull/248340)
* [@pelmers-db (Peter Elmers)](https://github.com/pelmers-db): Fix cancellation logic in Picker onDidChangeValue handler (fixes #247945) [PR #247946](https://github.com/microsoft/vscode/pull/247946)
* [@randy3k (Randy Lai)](https://github.com/randy3k): Update upstream repo for R syntax [PR #248880](https://github.com/microsoft/vscode/pull/248880)
* [@rbuckton (Ron Buckton)](https://github.com/rbuckton): Add casts to silence breaks due to updated DOM types [PR #248346](https://github.com/microsoft/vscode/pull/248346)
* [@RedCMD (RedCMD)](https://github.com/RedCMD): Support `@builtin @disabled` [PR #235885](https://github.com/microsoft/vscode/pull/235885)
* [@xzakharov (Oleksandr Zakharov)](https://github.com/xzakharov): fix(devcontainer): bump rust feature to fix container build [PR #250430](https://github.com/microsoft/vscode/pull/250430)
* [@y0sh1ne (y0sh1ne)](https://github.com/y0sh1ne): Fix Copy Message with multiple selections (#247927) [PR #248172](https://github.com/microsoft/vscode/pull/248172)

Contributions to `vscode-copilot-release`:

* [@joyceerhl (Joyce Er)](https://github.com/joyceerhl): chore: update bug report template [PR #9702](https://github.com/microsoft/vscode-copilot-release/pull/9702)

Contributions to `vscode-css-languageservice`:

* [@Legend-Master (Tony)](https://github.com/Legend-Master): Add basic media query auto complete support [PR #443](https://github.com/microsoft/vscode-css-languageservice/pull/443)
* [@rgant (J Rob Gant)](https://github.com/rgant)
  * feature:(#305) Add support for `oklab` and `oklch` color functions [PR #436](https://github.com/microsoft/vscode-css-languageservice/pull/436)
  * Remove extra characters [PR #437](https://github.com/microsoft/vscode-css-languageservice/pull/437)
  * refactor: Extend the base tsconfig.json [PR #438](https://github.com/microsoft/vscode-css-languageservice/pull/438)

Contributions to `vscode-custom-data`:

* [@Legend-Master (Tony)](https://github.com/Legend-Master): Add media query support [PR #118](https://github.com/microsoft/vscode-custom-data/pull/118)

Contributions to `vscode-eslint`:

* [@MariaSolOs (Maria José Solano)](https://github.com/MariaSolOs)
  * Add `eslint.codeActionsOnSave.options` [PR #1999](https://github.com/microsoft/vscode-eslint/pull/1999)
  * Add all possible flat configuration extensions [PR #2017](https://github.com/microsoft/vscode-eslint/pull/2017)

Contributions to `vscode-generator-code`:

* [@SamB (Samuel Bronson)](https://github.com/SamB): Do not link to top of vscode docs [PR #518](https://github.com/microsoft/vscode-generator-code/pull/518)

Contributions to `vscode-js-debug`:

* [@kdy1 (Donny/강동윤)](https://github.com/kdy1): chore: Fix default url for turbopack [PR #2223](https://github.com/microsoft/vscode-js-debug/pull/2223)
* [@mikaelwaltersson (Mikael Waltersson)](https://github.com/mikaelwaltersson): Fix bug where the WasmWorker instance is disposed but never re-spawned on page reloads + writeMemory when WASM memory is SharedArrayBuffer [PR #2211](https://github.com/microsoft/vscode-js-debug/pull/2211)

Contributions to `vscode-jupyter`:

* [@WillHirsch](https://github.com/WillHirsch): Downgrade diagnostic severity for use of bang instead of percent for package installs [PR #16601](https://github.com/microsoft/vscode-jupyter/pull/16601)

Contributions to `vscode-languageserver-node`:

* [@martijnwalraven (Martijn Walraven)](https://github.com/martijnwalraven): Fix `workspace/textDocumentContent/refresh` request [PR #1637](https://github.com/microsoft/vscode-languageserver-node/pull/1637)

Contributions to `vscode-markdown-tm-grammar`:

* [@Barros1902 (Tomás Barros )](https://github.com/Barros1902): Fix strikethrough with underscores in Markdown syntax (Fixes microsoft#173) [PR #174](https://github.com/microsoft/vscode-markdown-tm-grammar/pull/174)

Contributions to `vscode-prompt-tsx`:

* [@joyceerhl (Joyce Er)](https://github.com/joyceerhl): chore: npm audit fix [PR #175](https://github.com/microsoft/vscode-prompt-tsx/pull/175)

Contributions to `vscode-pull-request-github`:

* [@kabel (Kevin Abel)](https://github.com/kabel): Allow verified GitHub emails when none are private [PR #6921](https://github.com/microsoft/vscode-pull-request-github/pull/6921)

Contributions to `vscode-python-debugger`:

* [@kycutler (Kyle Cutler)](https://github.com/kycutler): Fix `TypeError` from trying to read directory [PR #692](https://github.com/microsoft/vscode-python-debugger/pull/692)

Contributions to `debug-adapter-protocol`:

* [@DrSergei](https://github.com/DrSergei): Fix some typos [PR #543](https://github.com/microsoft/debug-adapter-protocol/pull/543)
* [@robertoaloi (Roberto Aloi)](https://github.com/robertoaloi): Add Erlang EDB Debugger [PR #544](https://github.com/microsoft/debug-adapter-protocol/pull/544)

Contributions to `language-server-protocol`:

* [@asukaminato0721 (Asuka Minato)](https://github.com/asukaminato0721)
  * add caddy [PR #2131](https://github.com/microsoft/language-server-protocol/pull/2131)
  * add kdl [PR #2139](https://github.com/microsoft/language-server-protocol/pull/2139)
* [@brynne8 (Brynne Taylor)](https://github.com/brynne8): fix typo in glob pattern spec [PR #2132](https://github.com/microsoft/language-server-protocol/pull/2132)
* [@leon-bckl (Leon)](https://github.com/leon-bckl): Added c++20 lsp-framework [PR #2144](https://github.com/microsoft/language-server-protocol/pull/2144)
* [@nieomylnieja (Mateusz Hawrus)](https://github.com/nieomylnieja): chore: Add Nobl9 VSCode extension to servers.md [PR #2136](https://github.com/microsoft/language-server-protocol/pull/2136)
* [@zonuexe (USAMI Kenta)](https://github.com/zonuexe): Add LSP clients for Emacs [PR #2145](https://github.com/microsoft/language-server-protocol/pull/2145)

Contributions to `lsprotocol`:

* [@debonte (Erik De Bonte)](https://github.com/debonte)
  * Update to latest LSP spec [PR #420](https://github.com/microsoft/lsprotocol/pull/420)
  * Rewrite release pipeline to use MicroBuild rather than vscode's templates [PR #421](https://github.com/microsoft/lsprotocol/pull/421)
  * Change `pyproject.toml` version to `2025.0.0rc1` [PR #422](https://github.com/microsoft/lsprotocol/pull/422)
* [@myleshyson (Myles Hyson)](https://github.com/myleshyson): Add golang to plugin table [PR #418](https://github.com/microsoft/lsprotocol/pull/418)

<a id="scroll-to-top" role="button" title="Scroll to top" aria-label="scroll to top" href="#"><span class="icon"></span></a>
<link rel="stylesheet" type="text/css" href="css/inproduct_releasenotes.css"/>
