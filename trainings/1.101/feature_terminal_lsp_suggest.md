---
feature: "Terminal - Language Server Based Suggestions"
release: "1.101"
prerequisites:
  - "Python extension installed (ms-python.python)"
  - "Pylance language server active"
  - "Basic understanding of Python REPL and terminal usage"
  - "Knowledge of VS Code settings configuration"
audience: "Python Developers, Data Scientists, Terminal Power Users, All Developers"
---

# 🚀 Feature Training: `Terminal - Language Server Based Suggestions` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Terminal - Language Server Based Suggestions`
- **Release Version:** `1.101`
- **Feature Type:** `Terminal Enhancement, Language Server Integration, Developer Productivity`
- **Summary:**  
  Language server completions are now available in the terminal for interactive Python REPL sessions, bringing the same intelligent autocompletion and documentation that you get in the editor directly into the terminal. This feature starts with Python via Pylance and plans to expand to more languages in the future.

## 2. Why It Matters

- **Core Problem Solved:** Eliminates the need to switch between terminal and editor for code completion and documentation lookup during interactive Python sessions. Provides context-aware suggestions with documentation directly in the terminal environment.
- **Target Users:** Python developers using REPL for testing and experimentation, data scientists working with interactive sessions, developers who prefer terminal-based workflows, and anyone using VS Code's integrated terminal for Python development.
- **Context:** Requires specific settings to be enabled and works with Python REPL sessions. Future expansion to other languages planned.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- Python extension: `ms-python.python`
- Pylance language server (included with Python extension)
- Python environment configured and accessible
- Shell integration capabilities

### 3.2 How to Enable/Access

**Required Settings (all must be enabled):**

- `terminal.integrated.shellIntegration.enabled`: `true`
- `python.terminal.shellIntegration.enabled`: `true`
- `terminal.integrated.suggest.enabled`: `true`
- `python.analysis.supportAllPythonDocuments`: `true`

**Access Methods:**

- Open integrated terminal: `Ctrl+`` ` or `Cmd+`` `
- Start Python REPL: Type `python` or `python3` in terminal
- Trigger suggestions: Start typing and use `Tab` or `Ctrl+Space`

### 3.3 Step-by-Step Usage

#### 3.3.1 Enable Language Server Terminal Suggestions

1. **Open Settings:** `Ctrl+,` or `Cmd+,`
2. **Enable Required Settings:** Search for and enable each required setting:
   - `terminal.integrated.shellIntegration.enabled` → `true`
   - `python.terminal.shellIntegration.enabled` → `true`
   - `terminal.integrated.suggest.enabled` → `true`
   - `python.analysis.supportAllPythonDocuments` → `true`
3. **Restart VS Code:** Ensure all settings take effect
4. **Verify Python Extension:** Ensure Python extension and Pylance are active

#### 3.3.2 Using Suggestions in Python REPL

1. **Open Terminal:** Use keyboard shortcut or View menu
2. **Start Python REPL:** Type `python` and press Enter
3. **Import Modules:** Import libraries you want to work with
4. **Trigger Completions:** Start typing and press `Tab` or `Ctrl+Space`
5. **View Documentation:** Completions include docstrings and type information
6. **Navigate Suggestions:** Use arrow keys to select from completion list

#### 3.3.3 Advanced Usage Scenarios

**Interactive Data Analysis:**

```python
>>> import pandas as pd
>>> df = pd.read_csv('data.csv')
>>> df.gr[TAB]  # Shows completions: groupby, drop, etc. with documentation
```

**API Exploration:**

```python
>>> import requests
>>> response = requests.g[TAB]  # Shows get, post, etc. with method signatures
>>> response.json()[TAB]  # Shows available methods on response object
```

**Library Discovery:**

```python
>>> import numpy as np
>>> np.arr[TAB]  # Shows array, arange, etc. with detailed docstrings
```

### 3.4 Example(s)

#### Simple Example: Basic Python REPL Usage

```python
# Open terminal and start Python REPL
>>> import math
>>> math.s[TAB]  # Triggers completion
# Suggestions appear: sin, sqrt, sinh, etc.
# Each suggestion shows documentation inline

>>> math.sqrt(
# Function signature and documentation appear
# math.sqrt(x, /) -> float
# Return the square root of x.
```

#### Advanced Example: Data Science Workflow

```python
>>> import pandas as pd
>>> import numpy as np

>>> df = pd.DataFrame({'a': [1, 2, 3], 'b': [4, 5, 6]})
>>> df.gr[TAB]
# Completions: groupby, drop_duplicates, etc.
# Documentation shows parameters and return types

>>> df.groupby('a').me[TAB]
# Shows: mean, median, etc. with aggregation documentation

>>> np.lin[TAB]
# Shows: linspace, linalg, etc. with mathematical function docs
```

#### Interactive Web Development Example

```python
>>> import requests
>>> from flask import Flask

>>> response = requests.g[TAB]
# Shows HTTP methods with full documentation
# get(url, params=None, **kwargs) -> Response

>>> app = Flask(__name__)
>>> app.r[TAB]
# Shows Flask methods: route, run, register_blueprint, etc.
# Each with complete Flask documentation
```

### 3.5 Benefits and Features

#### Language Server Integration Benefits

- **Context-Aware Completions:** Suggestions based on actual imported modules and available symbols
- **Documentation Access:** Inline docstrings and type information without leaving terminal
- **Error Prevention:** Type hints and parameter information reduce coding errors
- **Library Discovery:** Explore unknown APIs and methods with integrated help

#### Terminal Workflow Enhancement

- **Seamless Development:** No context switching between editor and terminal for reference
- **Interactive Learning:** Discover and learn APIs through intelligent suggestions
- **Rapid Prototyping:** Faster experimentation with immediate documentation access
- **Debugging Support:** Better understanding of available methods during troubleshooting

## 4. Troubleshooting & FAQ

### Common Issues

- **No Completions Appearing:** Verify all four required settings are enabled and restart VS Code
- **Limited Suggestions:** Ensure Pylance is active and Python environment is properly configured
- **Slow Performance:** Large workspaces may affect suggestion speed; consider workspace-specific settings
- **REPL Not Recognized:** Check that Python is properly installed and accessible in PATH

### How to Disable

- **Disable Terminal Suggestions:** Set `terminal.integrated.suggest.enabled` to `false`
- **Disable Python Integration:** Set `python.terminal.shellIntegration.enabled` to `false`
- **Disable Shell Integration:** Set `terminal.integrated.shellIntegration.enabled` to `false`
- **Selective Disabling:** Disable only specific settings while keeping others active

### Edge Cases

- **Virtual Environments:** Ensure virtual environment is activated before starting REPL
- **Multiple Python Versions:** Suggestions reflect the active Python interpreter
- **Large Libraries:** Initial loading of large libraries (like TensorFlow) may cause brief delays
- **Custom Modules:** Local modules may require proper PYTHONPATH configuration

### FAQ

**Q: Does this work with other shells besides Python?**
A: Currently limited to Python REPL, but expansion to other languages is planned.

**Q: Can I use this with Jupyter notebooks?**
A: This feature is specific to terminal REPL; notebooks have their own completion system.

**Q: Does it work with virtual environments?**
A: Yes, activate your virtual environment before starting the REPL for environment-specific completions.

**Q: Are there performance impacts?**
A: Minimal impact for most use cases; large workspaces may experience slight delays during initial loading.

## 5. Additional Resources

- **Terminal Documentation:** [VS Code Integrated Terminal](https://code.visualstudio.com/docs/terminal/basics)
- **Shell Integration:** [Shell Integration Features](https://code.visualstudio.com/docs/terminal/shell-integration)
- **Python Extension:** [Python in VS Code](https://code.visualstudio.com/docs/python/python-tutorial)
- **Pylance Language Server:** [Pylance Features](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
- **Related Features:** Python Chat Tools, Code Editing, Language Server Protocol

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Terminal Language Server Suggestions |
