---
feature: "Import Chat Modes, Prompts, and Instructions via Link"
release: "1.102"
prerequisites:
  - "GitHub Copilot subscription with Chat"
  - "Basic understanding of chat modes and custom instructions"
audience: "Teams and individuals wanting to share and reuse chat configurations"
---

# 🚀 Feature Training: `Import Chat Modes, Prompts, and Instructions via Link` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Import Chat Modes, Prompts, and Instructions via Link`
- **Release Version:** `1.102`
- **Feature Type:** `Chat Enhancement`
- **Summary:**  
  Ability to import custom chat modes, prompts, and instruction files directly from external links using vscode:// protocol, enabling easy sharing and distribution of chat configurations.

## 2. Why It Matters

- **Easy Sharing:** Share custom chat configurations with team members or community via simple links
- **Quick Setup:** Import pre-configured modes without manual file creation
- **Community Access:** Access 100+ community-contributed modes from repositories like awesome-copilot
- **Team Collaboration:** Standardize chat behaviors across team members with shared configurations
- **Target Users:** Teams, community contributors, and users wanting to leverage shared chat configurations
- **Status:** Available in VS Code 1.102+ for supported file types

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- GitHub Copilot subscription with Chat enabled
- Understanding of chat modes and custom instructions concepts
- Access to vscode:// protocol links from external sources

### 3.2 How to Enable/Access

- **Protocol Support:** Uses `vscode://` URL scheme for imports
- **Link Format:** `vscode:chat-mode/install?url=<external-file-url>`
- **Supported Sources:** Gists, GitHub repositories, and other web-accessible markdown files
- **Import Destinations:** Workspace or user settings (choice during import)

### 3.3 Step-by-Step Usage

1. **Obtain Import Link:**
   - Find a vscode:// import link from team documentation, community repositories, or shared resources
   - Example: `vscode:chat-mode/install?url=https://raw.githubusercontent.com/example/repo/main/mode.chatmode.md`

2. **Click the Import Link:**
   - Click the link in your browser or documentation
   - VS Code automatically opens if not already running

3. **Choose Import Destination:**
   - VS Code prompts for destination choice:
     - **Workspace:** Available only in current project
     - **User Settings:** Available across all projects

4. **Confirm Import:**
   - Review the mode/prompt name and description
   - Confirm the import to add to your VS Code

5. **Use Imported Configuration:**
   - Access via Configure Chat menu (gear icon in Chat view)
   - Select imported mode from Chat mode picker
   - Edit or delete via Configure Chat if needed

### 3.4 Example(s)

- **Simple example:**  
  Import a code review mode from a team repository:

  ```
  vscode:chat-mode/install?url=https://raw.githubusercontent.com/myteam/vscode-configs/main/code-review.chatmode.md
  ```

- **Advanced/tip:**  
  Import from the awesome-copilot community repository:

  ```
  vscode:chat-mode/install?url=https://raw.githubusercontent.com/github/awesome-copilot/main/chatmodes/4.1-Beast.chatmode.md
  ```

**Import workflow:**

```
1. Click vscode:// link → 📥 VS Code opens import dialog
2. Choose destination → 📁 Workspace or User settings
3. Confirm import → ✅ Mode/prompt added to VS Code
4. Access via Chat → 🎯 Mode appears in mode picker
```

**Example imported file structure:**

```markdown
---
description: "Security-focused code review"
tools: ["codebase", "search", "problems"]
model: "gpt-4"
---

# Security Review Mode

Focus on security vulnerabilities, authentication issues, 
and secure coding practices when reviewing code.
```

## 4. Troubleshooting & FAQ

- **Q: What file types can be imported via links?**
  - A: Chat mode files (`.chatmode.md`), instruction files (`.instructions.md`), and prompt files (`.prompt.md`).

- **Q: Where can I find community-contributed modes?**
  - A: Check the [awesome-copilot](https://github.com/github/awesome-copilot) repository for 100+ community modes, prompts, and instructions.

- **Q: Can I modify imported modes?**
  - A: Yes, imported modes become regular files in your VS Code that you can edit, rename, or delete.

- **Q: What happens if an import link is broken?**
  - A: VS Code will show an error message if the linked file cannot be accessed or has invalid format.

- **Q: Can I create my own import links?**
  - A: Yes, host your `.chatmode.md` files on any web-accessible location and create vscode:// links pointing to them.

**Common Issues:**

- **Link doesn't work:** Ensure the URL is accessible and points to a valid markdown file
- **Import fails:** Check that the file has proper front matter and follows chat mode format
- **Mode doesn't appear:** Verify import completed successfully via Configure Chat menu
- **File format errors:** Ensure imported file has correct metadata structure

## 5. Additional Resources

- Community repository: [Awesome Copilot](https://github.com/github/awesome-copilot)
- Official documentation: [Custom Chat Modes](https://code.visualstudio.com/docs/copilot/chat/chat-modes)
- VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related features: Custom Chat Modes, Improved Editing Support

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Import via Link |
