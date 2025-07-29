---
feature: "Editor Experience"
release: "1.101"
resource_type: "Both"
audience: "All Users, Developers, Power Users"
prerequisites:
  - "Basic VS Code editor knowledge"
  - "Understanding of VS Code settings and preferences"
  - "Familiarity with search and navigation workflows"
summary: |
  Comprehensive hands-on exercises and demos for VS Code's Editor Experience improvements in version 1.101, covering find-as-you-type configuration, custom menu styles, AI-powered settings search, semantic search options, EditContext API benefits, process explorer enhancements, and shell environment integration.
---

# 📦 Resource Kit: `Editor Experience` — `Exercise + Demo`

## Directory Structure

```
editor-experience-kit/
├── README.md
├── exercise-1-find-and-search/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   └── search-examples/
│   │       ├── large-codebase/
│   │       │   ├── components/
│   │       │   ├── utils/
│   │       │   └── tests/
│   │       └── search-scenarios.md
│   ├── starter/
│   │   └── search-practice-files/
│   │       ├── sample.js
│   │       ├── config.json
│   │       └── readme.md
│   └── assets/
│       ├── ai-search-toggle.png
│       └── semantic-search-demo.gif
├── exercise-2-menu-customization/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   └── menu-examples/
│   │       ├── custom-context-menu.md
│   │       └── title-bar-options.md
│   ├── starter/
│   │   └── menu-templates/
│   │       └── basic-menu-config.json
│   └── assets/
│       ├── custom-menu-styles.png
│       └── linux-native-menu.png
├── exercise-3-settings-ai-search/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   └── search-scenarios/
│   │       ├── common-queries.md
│   │       └── ai-search-examples.md
│   ├── starter/
│   │   └── search-practice/
│   │       └── query-examples.md
│   └── assets/
│       ├── settings-ai-search.gif
│       └── semantic-vs-text-search.png
├── demo-1-editcontext-api/
│   ├── walkthrough.md
│   └── src/
│       ├── ime-examples/
│       │   ├── japanese-input.md
│       │   ├── chinese-input.md
│       │   └── emoji-input.md
│       └── input-scenarios/
│           ├── complex-characters.md
│           └── composition-text.md
│   └── assets/
│       ├── ime-improvement-demo.gif
│       └── editcontext-benefits.png
├── demo-2-process-explorer/
│   ├── walkthrough.md
│   └── src/
│       ├── web-environment/
│       │   ├── codespaces-setup.md
│       │   └── remote-development.md
│       └── monitoring/
│           ├── performance-analysis.md
│           └── process-debugging.md
│   └── assets/
│       ├── floating-process-explorer.png
│       └── web-process-explorer.png
└── demo-3-shell-environment/
    ├── walkthrough.md
    └── src/
        ├── powershell-profiles/
        │   ├── sample-profile.ps1
        │   └── node-version-manager.ps1
        └── environment-examples/
            ├── path-discovery.md
            └── environment-inheritance.md
    └── assets/
        ├── powershell-integration.png
        └── environment-discovery.gif
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### editor-experience-kit/README.md

```
# Editor Experience — Exercise + Demo Resource Kit

Welcome! This resource kit contains:
- **Exercises** with hands-on guides to master Editor Experience improvements in VS Code 1.101
- **Demos** showcasing advanced search, input handling, and environment integration
- **Solutions** with optimized configurations and best practices

## What You'll Learn

1. **Find & Search** - Configure find-as-you-type, AI-powered settings search, and semantic search
2. **Menu Customization** - Customize title bar and context menu styles
3. **AI-Powered Search** - Leverage semantic search for settings and code discovery
4. **EditContext API** - Understand improved input handling and IME support
5. **Process Explorer** - Use floating process explorer in web environments
6. **Shell Integration** - Benefit from PowerShell environment discovery

## Features Covered

- Find-as-you-type configuration and behavior
- AI-powered settings search with natural language queries
- Semantic search behavior options (manual, auto, runOnEmpty)
- Custom menu styles for title bar and context menus
- EditContext API for improved input experience
- Process explorer web support with floating windows
- PowerShell environment discovery and PATH inheritance
- Extension warning indicators for unpublished extensions

## Prerequisites

- VS Code 1.101+
- Basic understanding of VS Code settings and preferences
- Familiarity with search workflows and navigation
- For shell demos: PowerShell on Windows or compatible shell

## Getting Started

1. Start with `exercise-1-find-and-search`
2. Progress through exercises to build understanding
3. Explore demos for advanced features and real-world usage
4. Use solutions as configuration references

Happy editing!
```

---

### editor-experience-kit/exercise-1-find-and-search/instructions.md

```
# Exercise 1: Find and Search Enhancements

## Goal
Learn to configure and use the enhanced find-as-you-type behavior, AI-powered settings search, and semantic search options for improved editor navigation and discovery.

## Task
1. Configure find-as-you-type behavior in the editor
2. Enable and use AI-powered settings search
3. Configure semantic search behavior options
4. Practice with keyword suggestions in Search view
5. Compare traditional text search with semantic search results

## Input/Output
**Starter**: Sample codebase with various file types and search scenarios
**Expected Outcome**: Optimized search configuration with improved discovery capabilities

## Steps

1. **Configure Find-as-You-Type**
   - Open Settings (Ctrl+,)
   - Search for "find on type"
   - Configure `editor.find.findOnType` setting
   - Test behavior in large files

2. **Enable AI Settings Search**
    ```json
    {
        "workbench.settings.showAISearchToggle": true
    }
    ```

- Reload VS Code after enabling
- Test with natural language queries
- Compare AI vs traditional search results

3. **Configure Semantic Search**

    ```json
    {
        "search.searchView.keywordSuggestions": true,
        "search.searchView.semanticSearchBehavior": "runOnEmpty"
    }
    ```

   - Test different behavior modes
   - Practice with keyword suggestions

4. **Search Practice Scenarios**
   - Find settings for "increase text size"
   - Search for "authentication logic" in codebase
   - Use semantic search for "error handling patterns"
   - Test empty search results triggering AI search

5. **Performance Analysis**
   - Compare search speeds with different configurations
   - Measure AI search response times
   - Optimize settings for your workflow

## Tips

- AI search is slower but more intuitive for natural language queries
- Semantic search works best with conceptual rather than exact term queries
- Use `runOnEmpty` mode to get AI results when text search fails
- Keyword suggestions appear ~5x faster than in previous versions

```

---

### editor-experience-kit/exercise-1-find-and-search/starter/search-practice-files/sample.js

```javascript
// Sample JavaScript file for search practice
class AuthenticationManager {
  constructor(config) {
    this.apiKey = config.apiKey;
    this.baseUrl = config.baseUrl;
    this.timeout = config.timeout || 5000;
  }

  async authenticateUser(credentials) {
    try {
      const response = await fetch(`${this.baseUrl}/auth/login`, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          'Authorization': `Bearer ${this.apiKey}`
        },
        body: JSON.stringify(credentials),
        timeout: this.timeout
      });

      if (!response.ok) {
        throw new Error(`Authentication failed: ${response.status}`);
      }

      return await response.json();
    } catch (error) {
      console.error('Authentication error:', error);
      throw new Error('Failed to authenticate user');
    }
  }

  validateToken(token) {
    if (!token || typeof token !== 'string') {
      return false;
    }

    // Basic token validation logic
    const tokenParts = token.split('.');
    return tokenParts.length === 3;
  }

  handleAuthError(error) {
    switch (error.code) {
      case 'INVALID_CREDENTIALS':
        return 'Invalid username or password';
      case 'ACCOUNT_LOCKED':
        return 'Account is temporarily locked';
      case 'TOKEN_EXPIRED':
        return 'Session has expired, please login again';
      default:
        return 'Authentication error occurred';
    }
  }
}

module.exports = AuthenticationManager;
```

---

### editor-experience-kit/exercise-1-find-and-search/starter/search-practice-files/config.json

```json
{
  "api": {
    "baseUrl": "https://api.example.com",
    "timeout": 5000,
    "retries": 3
  },
  "authentication": {
    "provider": "oauth2",
    "clientId": "your-client-id",
    "scopes": ["read", "write", "admin"]
  },
  "features": {
    "enableLogging": true,
    "logLevel": "info",
    "enableCaching": true,
    "cacheTimeout": 3600
  },
  "ui": {
    "theme": "dark",
    "fontSize": 14,
    "showLineNumbers": true,
    "highlightSyntax": true
  }
}
```

---

### editor-experience-kit/exercise-1-find-and-search/starter/search-practice-files/readme.md

```markdown
# Search Practice Documentation

This directory contains sample files for practicing VS Code's enhanced search capabilities.

## Files Overview

- `sample.js` - JavaScript authentication module with error handling
- `config.json` - Configuration file with various settings
- `readme.md` - This documentation file

## Search Scenarios to Practice

### Traditional Text Search
- Search for exact function names: `authenticateUser`
- Find specific error codes: `INVALID_CREDENTIALS`
- Locate configuration keys: `baseUrl`

### Semantic Search Scenarios
- Search for "login functionality" (should find authentication code)
- Search for "error handling" (should find error-related functions)
- Search for "configuration options" (should find config files)
- Search for "user validation" (should find validation logic)

### AI Settings Search Scenarios
- "make text bigger" (should find fontSize settings)
- "change theme" (should find theme-related settings)
- "show line numbers" (should find editor line number settings)
- "enable word wrap" (should find word wrap settings)

## Testing Guidelines

1. Try both exact term searches and conceptual searches
2. Compare results between traditional and semantic search
3. Note performance differences
4. Test with empty search results to trigger AI search
5. Use keyword suggestions to refine searches

## Expected Improvements

- Faster keyword suggestions (~5x performance improvement)
- More intuitive natural language search results
- Better discovery of related concepts
- Reduced need for exact term knowledge
```

---

### editor-experience-kit/exercise-1-find-and-search/solution/.vscode/settings.json

```json
{
  // Find-as-you-type configuration
  "editor.find.findOnType": true,
  "editor.find.addExtraSpaceOnTop": false,
  "editor.find.autoFindInSelection": "multiline",
  
  // AI-powered settings search
  "workbench.settings.showAISearchToggle": true,
  
  // Enhanced search capabilities
  "search.searchView.keywordSuggestions": true,
  "search.searchView.semanticSearchBehavior": "runOnEmpty",
  "search.useReplacePreview": true,
  "search.smartCase": true,
  
  // Search performance optimizations
  "search.exclude": {
    "**/node_modules": true,
    "**/bower_components": true,
    "**/*.code-search": true,
    "**/coverage": true,
    "**/dist": true,
    "**/build": true
  },
  
  // Editor enhancements that complement search
  "editor.find.seedSearchStringFromSelection": "selection",
  "editor.find.globalFindClipboard": false,
  
  // Workbench settings for better search experience
  "workbench.quickOpen.includeHistory": true,
  "workbench.commandPalette.history": 50,
  
  // Additional search-related settings
  "search.followSymlinks": true,
  "search.maintainFileSearchCache": true,
  "search.quickOpen.includeSymbols": true
}
```

---

### editor-experience-kit/exercise-1-find-and-search/solution/search-examples/search-scenarios.md

```markdown
# Search Scenarios and Solutions

## AI Settings Search Examples

### Query: "increase text size"
**Traditional Search**: No results or confusing matches
**AI Search Results**:
- `editor.fontSize` - Controls the font size in pixels
- `editor.fontFamily` - Controls the font family
- `terminal.integrated.fontSize` - Terminal font size
- `markdown.preview.fontSize` - Markdown preview font size

### Query: "dark theme"
**Traditional Search**: Limited results
**AI Search Results**:
- `workbench.colorTheme` - Specifies the color theme
- `window.autoDetectColorScheme` - Auto-detect OS theme
- `workbench.preferredDarkColorTheme` - Default dark theme
- `editor.tokenColorCustomizations` - Custom token colors

### Query: "word wrap"
**Traditional Search**: Exact matches only
**AI Search Results**:
- `editor.wordWrap` - Controls how lines should wrap
- `editor.wordWrapColumn` - Controls wrapping column
- `editor.rulers` - Renders vertical rulers
- `diffEditor.wordWrap` - Word wrap in diff editor

## Semantic Search Examples

### Query: "authentication logic"
**Results Found**:
- Functions: `authenticateUser()`, `validateToken()`
- Classes: `AuthenticationManager`
- Error handling: `handleAuthError()`
- Configuration: authentication settings in config files

### Query: "error handling patterns"
**Results Found**:
- Try-catch blocks
- Error throwing statements
- Error logging code
- Validation functions
- Error message definitions

### Query: "configuration management"
**Results Found**:
- Config file loading
- Settings validation
- Default value assignments
- Environment variable usage
- Configuration object structures

## Search Behavior Comparison

| Behavior Mode | When AI Search Runs | Use Case |
|---------------|-------------------|----------|
| `manual` | Only when explicitly triggered | Precise control, faster searches |
| `runOnEmpty` | When text search returns no results | Best of both worlds |
| `auto` | Always runs in parallel | Maximum discovery, slower |

## Performance Optimization Tips

1. **Use Specific Terms First**: Try exact terms before semantic search
2. **Exclude Unnecessary Directories**: Configure search.exclude for faster results
3. **Use File Type Filters**: Narrow search scope with file extensions
4. **Leverage Search History**: VS Code remembers successful queries
5. **Combine Search Types**: Use text search for exact matches, semantic for concepts

## Advanced Search Techniques

### Regular Expression Search
- Enable regex mode for pattern matching
- Use capture groups for complex replacements
- Combine with semantic search for powerful discovery

### Multi-Root Workspace Search
- Search across multiple project roots
- Use workspace-specific search configurations
- Exclude irrelevant workspaces from search

### Search Editor Integration
- Save complex search results
- Share search configurations
- Build searchable knowledge bases
```

---

### editor-experience-kit/exercise-1-find-and-search/assets/ai-search-toggle.png

```
Screenshot showing:
- Settings editor with AI search toggle enabled
- Natural language query "increase text size"
- AI search results showing relevant font-related settings
- Toggle button for switching between AI and traditional search
```

---

### editor-experience-kit/exercise-1-find-and-search/assets/semantic-search-demo.gif

```
Animated GIF showing:
- User typing "authentication logic" in search
- Semantic search finding relevant authentication code
- Results highlighting conceptually related matches
- Keyword suggestions appearing as user types
```

---

### editor-experience-kit/exercise-2-menu-customization/instructions.md

```
# Exercise 2: Menu Customization and UI Enhancement

## Goal
Learn to customize VS Code's menu styles, configure title bar and context menu options, and optimize the editor interface for your workflow and platform.

## Task
1. Configure custom menu styles for title bar and context menus
2. Test Linux native window context menu (Linux users)
3. Customize menu behavior and appearance
4. Configure floating window infrastructure
5. Optimize menu accessibility and usability

## Input/Output
**Starter**: Basic menu configuration templates
**Expected Outcome**: Customized menu system optimized for your platform and workflow

## Steps

1. **Title Bar Menu Configuration**
    ```json
    {
        "window.titleBarStyle": "custom",
        "window.menuBarVisibility": "compact"
    }
    ```

- Test different title bar styles
- Configure menu bar visibility options

2. **Context Menu Customization**

    ```json
    {
        "workbench.contextMenuStyle": "native",
        "editor.contextMenuStyle": "compact"
    }
    ```

   - Compare native vs custom context menus
   - Test on different operating systems

3. **Linux Native Menu Support** (Linux only)

    ```json
    {
        "window.titleBarStyle": "custom",
        "workbench.useExperimentalGtkTitleBar": true
    }
    ```

   - Enable native GTK title bar support
   - Test window controls integration

4. **Floating Window Configuration**

    ```json
    {
        "window.experimental.floatingWindows": true,
        "workbench.editor.floatingWindows": true
    }
    ```

   - Enable floating window support
   - Test menu consistency across windows

5. **Accessibility Enhancements**
   - Configure high contrast menu themes
   - Test keyboard navigation
   - Optimize for screen readers

## Tips

- Menu customization varies by operating system
- Native menus provide better OS integration
- Custom menus offer more VS Code-specific features
- Test changes across different window states
- Consider accessibility when customizing menus

```

---

### editor-experience-kit/exercise-2-menu-customization/starter/menu-templates/basic-menu-config.json

```json
{
  "window.titleBarStyle": "native",
  "window.menuBarVisibility": "default",
  "workbench.contextMenuStyle": "default",
  "editor.contextMenuStyle": "default"
}
```

---

### editor-experience-kit/exercise-2-menu-customization/solution/.vscode/settings.json

```json
{
  // Title bar and menu bar configuration
  "window.titleBarStyle": "custom",
  "window.menuBarVisibility": "compact",
  "window.customMenuBarAltFocus": false,
  
  // Context menu styles
  "workbench.contextMenuStyle": "native",
  "editor.contextMenuStyle": "compact",
  
  // Linux-specific enhancements
  "workbench.useExperimentalGtkTitleBar": true,
  
  // Floating windows support
  "window.experimental.floatingWindows": true,
  "workbench.editor.floatingWindows": true,
  
  // Menu accessibility
  "workbench.colorCustomizations": {
    "menu.background": "#1e1e1e",
    "menu.foreground": "#cccccc",
    "menu.selectionBackground": "#094771",
    "menu.selectionForeground": "#ffffff",
    "menu.border": "#454545"
  },
  
  // Command palette enhancements
  "workbench.commandPalette.preserveInput": true,
  "workbench.quickOpen.closeOnFocusOut": false,
  
  // Editor menu context
  "editor.contextMenuIncludesRefactorings": true,
  "editor.contextMenuIncludesSurroundWith": true,
  
  // Window behavior
  "window.restoreWindows": "all",
  "window.newWindowDimensions": "inherit",
  
  // Performance optimizations
  "workbench.enableExperiments": false,
  "workbench.settings.enableNaturalLanguageSearch": true
}
```

---

### editor-experience-kit/exercise-2-menu-customization/solution/menu-examples/custom-context-menu.md

```markdown
# Custom Context Menu Configuration

## Context Menu Styles

### Native Style
```json
{
  "workbench.contextMenuStyle": "native"
}
```

**Benefits**:

- OS-consistent appearance
- Native accessibility support
- System theme integration
- Platform-specific behaviors

**Drawbacks**:

- Limited customization
- May not match VS Code theme
- Feature limitations

### Custom Style

```json
{
  "workbench.contextMenuStyle": "custom"
}
```

**Benefits**:

- Full theme integration
- Consistent across platforms
- Rich customization options
- VS Code-specific features

**Drawbacks**:

- May not follow OS conventions
- Custom accessibility implementation
- Potential performance differences

## Editor Context Menu Options

### Compact Style

```json
{
  "editor.contextMenuStyle": "compact",
  "editor.contextMenuIncludesRefactorings": true,
  "editor.contextMenuIncludesSurroundWith": true
}
```

### Extended Context Menu Items

- **Refactoring Actions**: Extract method, rename symbol, etc.
- **Surround With**: Try/catch blocks, if statements, etc.
- **Code Actions**: Quick fixes, organize imports
- **Navigation**: Go to definition, find references
- **Git Integration**: Blame, history, compare

## Platform-Specific Configurations

### Windows

```json
{
  "window.titleBarStyle": "custom",
  "workbench.contextMenuStyle": "custom"
}
```

### macOS

```json
{
  "window.titleBarStyle": "native",
  "workbench.contextMenuStyle": "native"
}
```

### Linux

```json
{
  "window.titleBarStyle": "custom",
  "workbench.useExperimentalGtkTitleBar": true,
  "workbench.contextMenuStyle": "native"
}
```

## Accessibility Considerations

### High Contrast Themes

```json
{
  "workbench.colorCustomizations": {
    "menu.background": "#000000",
    "menu.foreground": "#ffffff",
    "menu.selectionBackground": "#ffffff",
    "menu.selectionForeground": "#000000"
  }
}
```

### Keyboard Navigation

- **Arrow Keys**: Navigate menu items
- **Enter**: Activate selected item
- **Escape**: Close menu
- **Tab**: Move to next focusable element

### Screen Reader Support

- Menu items include proper ARIA labels
- Keyboard shortcuts announced
- Context-sensitive help available
- Role and state information provided

```

---

### editor-experience-kit/exercise-2-menu-customization/solution/menu-examples/title-bar-options.md

```markdown
# Title Bar Configuration Options

## Title Bar Styles

### Native Style
```json
{
  "window.titleBarStyle": "native"
}
```

**Features**:

- OS-native window controls
- System menu integration
- Platform-consistent behavior
- Native drag and resize

### Custom Style

```json
{
  "window.titleBarStyle": "custom"
}
```

**Features**:

- VS Code-branded title bar
- Integrated menu bar
- Custom window controls
- Theme-consistent styling

## Menu Bar Visibility Options

### Always Visible

```json
{
  "window.menuBarVisibility": "visible"
}
```

### Compact Mode

```json
{
  "window.menuBarVisibility": "compact"
}
```

- Hamburger menu button
- More screen space for editor
- Clean, minimal interface

### Hidden (Toggle with Alt)

```json
{
  "window.menuBarVisibility": "toggle"
}
```

### Completely Hidden

```json
{
  "window.menuBarVisibility": "hidden"
}
```

## Linux-Specific Enhancements

### GTK Title Bar Integration

```json
{
  "workbench.useExperimentalGtkTitleBar": true
}
```

**Benefits**:

- Native Linux window decorations
- Better DE (Desktop Environment) integration
- Consistent with other GTK applications
- Native context menu support

**Requirements**:

- Linux with GTK-based desktop environment
- VS Code 1.101+
- Custom title bar style enabled

## Advanced Title Bar Configuration

### Custom Alt Focus Behavior

```json
{
  "window.customMenuBarAltFocus": false
}
```

- Disable Alt key menu focus
- Prevent accidental menu activation
- Better for keyboard workflows

### Window State Management

```json
{
  "window.restoreWindows": "all",
  "window.newWindowDimensions": "inherit"
}
```

## Floating Window Integration

### Process Explorer Support

- Process explorer uses floating window infrastructure
- Consistent menu behavior across windows
- Web environment support (Codespaces)

### Multi-Window Workflows

```json
{
  "window.experimental.floatingWindows": true,
  "workbench.editor.floatingWindows": true
}
```

## Troubleshooting

### Menu Not Appearing

1. Check `window.menuBarVisibility` setting
2. Try toggling with Alt key
3. Reset to default and reconfigure

### Inconsistent Styling

1. Verify theme compatibility
2. Check platform-specific settings
3. Clear workspace settings if needed

### Linux Integration Issues

1. Ensure GTK development libraries installed
2. Check desktop environment compatibility
3. Verify X11/Wayland support

## Best Practices

1. **Platform Consistency**: Use native styles when possible
2. **Accessibility**: Test with keyboard navigation
3. **Performance**: Minimize custom styling overhead
4. **User Preference**: Provide configuration options
5. **Testing**: Verify across different window states

```

---

### editor-experience-kit/exercise-2-menu-customization/assets/custom-menu-styles.png

```

Screenshot showing:

- Side-by-side comparison of native vs custom menu styles
- Title bar variations (native, custom, compact)
- Context menu differences across platforms
- Menu bar visibility options

```

---

### editor-experience-kit/exercise-2-menu-customization/assets/linux-native-menu.png

```

Screenshot showing:

- Linux GTK title bar integration
- Native context menu with OS theming
- Window controls matching desktop environment
- Consistent styling with other GTK applications

```

This resource kit provides comprehensive hands-on experience with VS Code's Editor Experience improvements from version 1.101. The exercises cover find-as-you-type configuration, menu customization, and AI-powered search features, while demos showcase EditContext API benefits, process explorer enhancements, and shell environment integration.

Would you like me to continue with the next major feature? The next feature would be "Code Editing" which includes NES (Next Edit Suggestions) import suggestions and improved acceptance flow for TypeScript, JavaScript, and Python.
