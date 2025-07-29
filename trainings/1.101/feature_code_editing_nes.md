---
feature: "Code Editing - NES (Next Edit Suggestions)"
release: "1.101"
prerequisites:
  - "GitHub Copilot subscription and extension installed"
  - "Basic understanding of TypeScript, JavaScript, or Python"
  - "Familiarity with import statements and code refactoring"
audience: "Developers, Programmers working with TypeScript/JavaScript/Python"
---

# 🚀 Feature Training: `Code Editing - NES (Next Edit Suggestions)` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Code Editing - NES (Next Edit Suggestions)`
- **Release Version:** `1.101`
- **Feature Type:** `AI-Assisted Code Editing, Productivity Enhancement`
- **Summary:**  
  Next Edit Suggestions (NES) provide AI-powered assistance for editing existing code by proactively suggesting missing import statements, related code updates, and seamless keyboard-driven acceptance flow. Enhanced in 1.101 with improved accuracy, reliability, and expanded Python support alongside existing TypeScript/JavaScript support.

## 2. Why It Matters

- **Core Problem Solved:** Eliminates manual hunting for missing imports and related code changes during refactoring. Reduces context switching and coding errors by proactively suggesting necessary edits across the codebase.
- **Target Users:** Developers working with TypeScript, JavaScript, and Python who frequently refactor code, add new dependencies, or work with large codebases requiring import management.
- **Context:** NES is enabled by default for VS Code Insiders users and progressively rolling out to Stable users. Can be manually enabled via settings.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- GitHub Copilot extension with active subscription
- Supported languages: TypeScript, JavaScript, Python
- Understanding of import/export syntax in target languages

### 3.2 How to Enable/Access

- **Enable NES:** Settings → `github.copilot.nextEditSuggestions.fixes` → `true`
- **Automatic Activation:** NES runs automatically while editing supported files
- **Visual Indicators:** Look for arrow icons in editor gutter when suggestions are available
- **Keyboard Navigation:** Use `Tab` key to navigate and accept suggestions

### 3.3 Step-by-Step Usage

#### 3.3.1 NES Import Suggestions

1. **Trigger Context:** Start using a function, class, or module that requires an import
2. **Visual Indicator:** NES displays arrow in gutter indicating missing import suggestion
3. **Navigate to Suggestion:** Press `Tab` to jump to the suggested import location
4. **Preview Suggestion:** View the suggested import statement (highlighted in green)
5. **Accept/Reject:** Press `Tab` again to accept, or ignore to reject

**Example Workflow:**

```typescript
// You type this in your code:
const result = axios.get('/api/data');

// NES detects missing import and shows arrow in gutter
// Pressing Tab shows suggestion:
import axios from 'axios'; // ← NES suggests this import
```

#### 3.3.2 Enhanced Acceptance Flow

1. **Chain Acceptance:** After accepting one suggestion, continue pressing `Tab` to accept subsequent related suggestions
2. **Seamless Navigation:** NES automatically moves cursor between related suggestions
3. **Typing Interruption:** If you start typing, press `Tab` once to move to next suggestion, then `Tab` again to accept
4. **Multiple File Support:** NES can suggest changes across multiple files in your project

**Keyboard Shortcuts:**

- `Tab`: Navigate to next suggestion or accept current suggestion
- `Esc`: Dismiss current suggestion
- Continue typing: Temporarily pause suggestion flow

#### 3.3.3 Language-Specific Support

**TypeScript/JavaScript:**

```typescript
// Using a new utility function
const formatted = formatDate(new Date());
// NES suggests: import { formatDate } from './utils/dateUtils';

// Using a new React component
<UserProfile user={currentUser} />
// NES suggests: import { UserProfile } from './components/UserProfile';
```

**Python:**

```python
# Using pandas functionality
df = pd.read_csv('data.csv')
# NES suggests: import pandas as pd

# Using specific functions
result = requests.get('https://api.example.com')
# NES suggests: import requests
```

### 3.4 Example(s)

#### Simple Example: Adding Missing Import

```typescript
// 1. You write code using a new function:
const users = await fetchUsers();

// 2. NES shows arrow in gutter suggesting import
// 3. Press Tab to navigate to suggestion location
// 4. See suggested import:
import { fetchUsers } from './api/userService';

// 5. Press Tab again to accept, or ignore to reject
```

#### Advanced Example: Refactoring with Multiple Suggestions

```typescript
// Initial code:
function processData(data: any[]) {
  return data.map(item => transformItem(item));
}

// You add new imports and utilities:
import { validateInput } from './validators';
import { logOperation } from './logging';

// NES suggests related updates throughout your code:
function processData(data: unknown[]) { // ← Type improvement suggestion
  logOperation('Processing data', data.length); // ← Logging suggestion
  const validData = validateInput(data); // ← Validation suggestion
  return validData.map(item => transformItem(item));
}
```

#### Python Example: Scientific Computing

```python
# You start using numpy functions:
array = np.array([1, 2, 3, 4, 5])
result = np.mean(array)

# NES suggests at top of file:
import numpy as np

# And for matplotlib:
plt.plot(array, result)
# NES suggests:
import matplotlib.pyplot as plt
```

## 4. Troubleshooting & FAQ

### Common Issues

- **Suggestions Not Appearing:** Ensure `github.copilot.nextEditSuggestions.fixes` is enabled and Copilot is active
- **Wrong Import Suggestions:** NES learns from your codebase; ensure consistent import patterns
- **Performance Impact:** Large codebases may experience slight delays; suggestions appear as analysis completes
- **Language Not Supported:** Currently limited to TypeScript, JavaScript, and Python

### How to Disable

- **Disable NES:** Settings → `github.copilot.nextEditSuggestions.fixes` → `false`
- **Temporary Dismissal:** Press `Esc` to dismiss current suggestions
- **Per-File Disabling:** Use `// @ts-ignore` or similar language-specific comments

### Edge Cases

- **Ambiguous Imports:** When multiple import sources exist, NES may suggest the most commonly used
- **Custom Module Paths:** May require TypeScript path mapping or Python path configuration
- **Conflicting Suggestions:** If multiple tools suggest different imports, prioritize based on your project patterns
- **Performance Considerations:** Very large files may have delayed suggestion appearance

### FAQ

**Q: Can NES suggest imports from new packages not yet installed?**
A: NES primarily suggests from existing code patterns and installed packages. Install packages first for best results.

**Q: Does NES work with custom import aliases?**
A: Yes, NES learns from your existing import patterns and suggests consistent aliases.

**Q: Can I customize which imports NES suggests?**
A: NES learns from your codebase patterns. Maintain consistent import styles for better suggestions.

## 5. Additional Resources

- **Official Blog Post:** [Next Edit Suggestions in VS Code](https://code.visualstudio.com/blogs/2025/02/12/next-edit-suggestions)
- **Copilot Documentation:** [AI-Powered Suggestions](https://code.visualstudio.com/docs/copilot/ai-powered-suggestions)
- **GitHub Next Research:** [Copilot Next Edit Suggestions Project](https://githubnext.com/projects/copilot-next-edit-suggestions/)
- **Import Best Practices:** Language-specific documentation for TypeScript, JavaScript, and Python imports
- **Related Features:** GitHub Copilot Completions, Code Actions, Refactoring Tools

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for NES Code Editing features |
