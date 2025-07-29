---
feature: "Terminal - Language Server Based Suggestions"
release: "1.101"
resource_type: "Both"
audience: "Python Developers, Data Scientists, Terminal Power Users, All Developers"
prerequisites:
  - "Python extension installed (ms-python.python)"
  - "Pylance language server active"
  - "Basic understanding of Python REPL and terminal usage"
  - "Knowledge of VS Code settings configuration"
summary: |
  Comprehensive hands-on exercises and demos for VS Code's Terminal Language Server Based Suggestions in version 1.101, covering LSP completions in Python REPL sessions, shell integration settings, and advanced terminal workflows with intelligent autocompletion.
---

# 📦 Resource Kit: `Terminal - Language Server Based Suggestions` — `Exercise + Demo`

## Directory Structure

```
terminal-lsp-suggest-kit/
├── README.md
├── exercise-1-basic-lsp-setup/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   ├── python-environments/
│   │   │   ├── basic-env/
│   │   │   │   ├── requirements.txt
│   │   │   │   └── main.py
│   │   │   ├── data-science/
│   │   │   │   ├── requirements.txt
│   │   │   │   └── analysis.py
│   │   │   └── web-dev/
│   │   │       ├── requirements.txt
│   │   │       └── app.py
│   │   └── terminal-scripts/
│   │       ├── setup-python.sh
│   │       ├── test-completions.py
│   │       └── demo-session.py
│   ├── starter/
│   │   ├── basic-setup/
│   │   │   ├── sample.py
│   │   │   └── README.md
│   │   └── practice-files/
│   │       ├── utils.py
│   │       └── models.py
│   └── assets/
│       ├── lsp-completions-demo.gif
│       ├── terminal-suggestions.png
│       └── shell-integration-setup.png
├── exercise-2-advanced-completions/
│   ├── instructions.md
│   ├── solution/
│   │   ├── complex-projects/
│   │   │   ├── machine-learning/
│   │   │   │   ├── src/
│   │   │   │   │   ├── models/
│   │   │   │   │   ├── data/
│   │   │   │   │   └── utils/
│   │   │   │   ├── notebooks/
│   │   │   │   └── requirements.txt
│   │   │   ├── web-framework/
│   │   │   │   ├── app/
│   │   │   │   │   ├── routes/
│   │   │   │   │   ├── models/
│   │   │   │   │   └── templates/
│   │   │   │   └── requirements.txt
│   │   │   └── data-analysis/
│   │   │       ├── datasets/
│   │   │       ├── scripts/
│   │   │       └── visualizations/
│   │   └── completion-scenarios/
│   │       ├── import-completions.py
│   │       ├── method-chaining.py
│   │       ├── type-annotations.py
│   │       └── documentation-lookup.py
│   ├── starter/
│   │   └── practice-scenarios/
│   │       ├── incomplete-imports.py
│   │       └── partial-methods.py
│   └── assets/
│       ├── advanced-completions.gif
│       ├── context-aware-suggestions.png
│       └── documentation-integration.png
├── exercise-3-workflow-integration/
│   ├── instructions.md
│   ├── solution/
│   │   ├── workflow-examples/
│   │   │   ├── debugging-workflow/
│   │   │   │   ├── debug_session.py
│   │   │   │   └── breakpoint_analysis.py
│   │   │   ├── testing-workflow/
│   │   │   │   ├── test_runner.py
│   │   │   │   └── interactive_tests.py
│   │   │   └── data-exploration/
│   │   │       ├── exploratory_analysis.py
│   │   │       └── visualization_workflow.py
│   │   └── automation-scripts/
│   │       ├── repl-automation.py
│   │       ├── batch-processing.py
│   │       └── terminal-helpers.py
│   ├── starter/
│   │   └── workflow-templates/
│   │       ├── basic-workflow.py
│   │       └── automation-template.py
│   └── assets/
│       ├── workflow-integration.gif
│       ├── terminal-automation.png
│       └── repl-productivity.png
├── demo-1-data-science-workflow/
│   ├── walkthrough.md
│   └── src/
│       ├── data-science-project/
│       │   ├── .vscode/
│       │   │   └── settings.json
│       │   ├── data/
│       │   │   ├── raw/
│       │   │   │   └── sample_dataset.csv
│       │   │   └── processed/
│       │   ├── src/
│       │   │   ├── data_preprocessing.py
│       │   │   ├── analysis.py
│       │   │   ├── visualization.py
│       │   │   └── models.py
│       │   ├── notebooks/
│       │   │   ├── exploration.ipynb
│       │   │   └── modeling.ipynb
│       │   └── requirements.txt
│       └── terminal-sessions/
│           ├── interactive-analysis.py
│           ├── model-training.py
│           └── results-validation.py
│   └── assets/
│       ├── data-science-terminal.gif
│       └── interactive-analysis.png
├── demo-2-web-development-workflow/
│   ├── walkthrough.md
│   └── src/
│       ├── flask-api-project/
│       │   ├── .vscode/
│       │   │   └── settings.json
│       │   ├── app/
│       │   │   ├── __init__.py
│       │   │   ├── routes/
│       │   │   │   ├── __init__.py
│       │   │   │   ├── auth.py
│       │   │   │   └── api.py
│       │   │   ├── models/
│       │   │   │   ├── __init__.py
│       │   │   │   ├── user.py
│       │   │   │   └── product.py
│       │   │   └── utils/
│       │   │       ├── __init__.py
│       │   │       ├── database.py
│       │   │       └── helpers.py
│       │   ├── tests/
│       │   │   ├── test_routes.py
│       │   │   └── test_models.py
│       │   └── requirements.txt
│       └── development-workflow/
│           ├── api-testing.py
│           ├── database-operations.py
│           └── debugging-session.py
│   └── assets/
│       ├── web-dev-terminal.gif
│       └── api-testing-workflow.png
└── demo-3-machine-learning-workflow/
    ├── walkthrough.md
    └── src/
        ├── ml-project/
        │   ├── .vscode/
        │   │   └── settings.json
        │   ├── data/
        │   │   ├── train/
        │   │   ├── test/
        │   │   └── validation/
        │   ├── src/
        │   │   ├── data_loader.py
        │   │   ├── feature_engineering.py
        │   │   ├── model_training.py
        │   │   ├── evaluation.py
        │   │   └── prediction.py
        │   ├── models/
        │   │   ├── saved_models/
        │   │   └── checkpoints/
        │   └── requirements.txt
        └── ml-workflows/
            ├── model-experimentation.py
            ├── hyperparameter-tuning.py
            └── model-evaluation.py
    └── assets/
        ├── ml-terminal-workflow.gif
        └── model-training-terminal.png
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### terminal-lsp-suggest-kit/README.md

```
# Terminal - Language Server Based Suggestions — Exercise + Demo Resource Kit

Welcome! This resource kit contains:
- **Exercises** with hands-on guides to master Terminal LSP Suggestions in VS Code 1.101
- **Demos** showcasing advanced terminal workflows with intelligent completions
- **Solutions** with optimized configurations and best practices

## What You'll Learn

1. **Basic LSP Setup** - Configure terminal language server suggestions for Python REPL
2. **Advanced Completions** - Context-aware suggestions, documentation lookup, and method chaining
3. **Workflow Integration** - Seamless terminal workflows with LSP-powered productivity
4. **Data Science Workflow** - Interactive analysis with intelligent terminal completions
5. **Web Development Workflow** - API testing and debugging with LSP suggestions
6. **Machine Learning Workflow** - Model development and experimentation with terminal assistance

## Features Covered

- Language server completions in Python REPL sessions
- Shell integration with LSP for intelligent suggestions
- Context-aware autocompletion in terminal environments
- Documentation lookup directly in terminal
- Import statement completions and method chaining
- Type annotations and parameter hints in REPL
- Advanced terminal workflows with LSP integration

## Prerequisites

- VS Code 1.101+
- Python extension (ms-python.python)
- Pylance language server (included with Python extension)
- Python environment configured and accessible
- Basic understanding of Python REPL and terminal usage

## Getting Started

1. **Configure Settings**: Enable required terminal and Python settings
2. **Verify Setup**: Test basic completions in Python REPL
3. **Start with Exercise 1**: Learn basic LSP setup and configuration
4. **Progress through exercises**: Build advanced terminal workflow skills
5. **Explore demos**: See real-world applications in different development contexts

## Required Settings

### Essential Configuration
```json
{
  "terminal.integrated.shellIntegration.enabled": true,
  "python.terminal.shellIntegration.enabled": true,
  "terminal.integrated.suggest.enabled": true,
  "python.analysis.supportAllPythonDocuments": true
}
```

### Optional Enhancements

```json
{
  "terminal.integrated.suggest.quickSuggestions": true,
  "terminal.integrated.suggest.boldLabel": true,
  "terminal.integrated.commandsToSkipShell": ["workbench.action.terminal.clear"],
  "python.terminal.activateEnvironment": true
}
```

## Terminal LSP Features

### Completion Types

- **Import Completions**: Intelligent module and package suggestions
- **Method/Attribute Completions**: Context-aware method and property suggestions
- **Function Parameter Hints**: Parameter information and type hints
- **Documentation Lookup**: Inline documentation and help text
- **Type Annotations**: Type information and inference

### Shell Integration

- **Command Recognition**: LSP knows about Python commands and context
- **Environment Awareness**: Completions based on active Python environment
- **Project Context**: Suggestions based on current workspace and imports
- **REPL State**: Maintains context across interactive sessions

## Keyboard Shortcuts

### Terminal Navigation

- **Open Terminal**: `Ctrl+`` (backtick)
- **New Terminal**: `Ctrl+Shift+``
- **Split Terminal**: `Ctrl+Shift+5`
- **Switch Terminal**: `Ctrl+PageUp/PageDown`

### Completion Controls

- **Trigger Suggestions**: `Ctrl+Space` (in terminal)
- **Accept Suggestion**: `Tab` or `Enter`
- **Navigate Suggestions**: `Arrow keys`
- **Dismiss Suggestions**: `Escape`

## Common Use Cases

### Data Science

- **Interactive Analysis**: Real-time data exploration with completions
- **Library Exploration**: Discover methods and properties of data libraries
- **Visualization**: Quick plotting and chart creation with suggestions

### Web Development

- **API Testing**: Interactive testing with framework completions
- **Database Operations**: ORM and database library suggestions
- **Debugging**: Step-by-step debugging with intelligent completions

### Machine Learning

- **Model Experimentation**: Interactive model building and testing
- **Library Discovery**: Explore ML libraries and their capabilities
- **Data Processing**: Intelligent suggestions for data manipulation

Happy terminal development with intelligent LSP completions!

```

---

### terminal-lsp-suggest-kit/exercise-1-basic-lsp-setup/instructions.md

```

# Exercise 1: Basic LSP Setup for Terminal Suggestions

## Goal

Learn to configure and use language server completions in VS Code's integrated terminal, specifically for Python REPL sessions, with proper shell integration and suggestion settings.

## Task

1. Configure required settings for terminal LSP suggestions
2. Set up Python environment with proper shell integration
3. Test basic completions in Python REPL
4. Understand completion types and behavior
5. Troubleshoot common configuration issues

## Input/Output

**Starter**: Basic Python project with sample modules
**Expected Outcome**: Fully functional LSP completions in terminal Python REPL with context-aware suggestions

## Steps

1. **Configure Essential Settings**

   ```json
   {
     "terminal.integrated.shellIntegration.enabled": true,
     "python.terminal.shellIntegration.enabled": true,
     "terminal.integrated.suggest.enabled": true,
     "python.analysis.supportAllPythonDocuments": true
   }
   ```

   - Open Settings (Ctrl+,)
   - Search for each setting and enable them
   - Reload VS Code to ensure settings take effect

2. **Verify Python Extension Setup**
   - Ensure Python extension is installed and active
   - Check that Pylance language server is running
   - Verify Python interpreter is correctly selected
   - Open Command Palette → "Python: Select Interpreter"

3. **Test Basic Terminal LSP**
   - Open integrated terminal (Ctrl+`)
   - Start Python REPL: `python` or `python3`
   - Test basic completions:

     ```python
     import os
     os.  # Press Ctrl+Space to see completions
     ```

4. **Test Import Completions**

   ```python
   # In Python REPL, type and use completions:
   import sys
   import json
   from collections import  # Should show completions
   ```

5. **Test Method Chaining**

   ```python
   # Test method completions:
   "hello world".  # Should show string methods
   [1, 2, 3].  # Should show list methods
   ```

6. **Test Documentation Lookup**

   ```python
   # Test parameter hints and documentation:
   len(  # Should show parameter hints
   help(print)  # Should work with completions
   ```

7. **Create Custom Module Test**
   - Create a Python file in your workspace
   - Import it in REPL and test completions
   - Verify LSP recognizes your custom code

8. **Troubleshoot Common Issues**
   - If completions don't work, check terminal type
   - Verify shell integration is active
   - Restart Python REPL if needed
   - Check Python extension output for errors

## Tips

- Shell integration must be enabled for LSP suggestions to work
- Python REPL needs to be active for Python-specific completions
- Use Ctrl+Space to manually trigger completions if they don't appear
- Check VS Code's Output panel (Python tab) for LSP status
- Some terminals may require specific configuration for shell integration
- Virtual environments should work automatically if properly activated
- Restart VS Code if settings changes don't take effect immediately

```

---

### terminal-lsp-suggest-kit/exercise-1-basic-lsp-setup/solution/.vscode/settings.json

```json
{
  // Terminal LSP Configuration - Essential Settings
  "terminal.integrated.shellIntegration.enabled": true,
  "python.terminal.shellIntegration.enabled": true,
  "terminal.integrated.suggest.enabled": true,
  "python.analysis.supportAllPythonDocuments": true,
  
  // Enhanced Terminal Experience
  "terminal.integrated.suggest.quickSuggestions": true,
  "terminal.integrated.suggest.boldLabel": true,
  "terminal.integrated.commandsToSkipShell": [
    "workbench.action.terminal.clear",
    "workbench.action.terminal.newWithCwd"
  ],
  
  // Python Configuration
  "python.terminal.activateEnvironment": true,
  "python.terminal.executeInFileDir": false,
  "python.terminal.launchArgs": ["-u"],
  "python.defaultInterpreterPath": "./venv/bin/python",
  
  // Pylance Language Server Settings
  "python.analysis.typeCheckingMode": "basic",
  "python.analysis.autoImportCompletions": true,
  "python.analysis.autoSearchPaths": true,
  "python.analysis.extraPaths": ["./src"],
  "python.analysis.completeFunctionParens": true,
  
  // Terminal Appearance and Behavior
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.fontFamily": "Consolas, 'Courier New', monospace",
  "terminal.integrated.cursorBlinking": true,
  "terminal.integrated.cursorStyle": "line",
  
  // Shell Integration Enhancements
  "terminal.integrated.shellIntegration.decorationsEnabled": "both",
  "terminal.integrated.shellIntegration.history": 100,
  "terminal.integrated.enableMultiLinePasteWarning": false,
  
  // Python Environment Management
  "python.envFile": "${workspaceFolder}/.env",
  "python.venvPath": "./venv",
  "python.condaPath": "",
  
  // Editor Integration with Terminal
  "python.terminal.focusAfterLaunch": false,
  "workbench.action.terminal.scrollToBottom": true,
  
  // LSP Performance Settings
  "python.analysis.memory.keepLibraryAst": true,
  "python.analysis.indexing": true,
  "python.analysis.packageIndexDepths": [
    {
      "name": "sklearn",
      "depth": 2
    },
    {
      "name": "matplotlib",
      "depth": 2
    },
    {
      "name": "pandas",
      "depth": 2
    },
    {
      "name": "numpy",
      "depth": 2
    }
  ],
  
  // Terminal Debugging
  "terminal.integrated.showExitAlert": false,
  "terminal.integrated.confirmOnExit": "never",
  "terminal.integrated.enableBell": false,
  
  // File Associations for Better LSP
  "files.associations": {
    "*.py": "python",
    "*.pyi": "python",
    "*.pyx": "python"
  },
  
  // Workspace Settings
  "python.analysis.useLibraryCodeForTypes": true,
  "python.analysis.diagnosticMode": "workspace",
  
  // Terminal Profiles (Platform Specific)
  "terminal.integrated.profiles.windows": {
    "PowerShell": {
      "source": "PowerShell",
      "icon": "terminal-powershell",
      "args": ["-NoExit", "-Command", "& {Write-Host 'Terminal LSP Ready!' -ForegroundColor Green}"]
    },
    "Command Prompt": {
      "path": ["C:\\Windows\\System32\\cmd.exe"],
      "args": ["/k", "echo Terminal LSP Ready!"],
      "icon": "terminal-cmd"
    }
  },
  
  "terminal.integrated.profiles.linux": {
    "bash": {
      "path": "bash",
      "icon": "terminal-bash",
      "args": ["--init-file", "<(echo 'echo Terminal LSP Ready!')"]
    },
    "zsh": {
      "path": "zsh",
      "icon": "terminal-tmux"
    }
  },
  
  "terminal.integrated.profiles.osx": {
    "bash": {
      "path": "bash",
      "icon": "terminal-bash",
      "args": ["--init-file", "<(echo 'echo Terminal LSP Ready!')"]
    },
    "zsh": {
      "path": "zsh",
      "icon": "terminal-tmux"
    }
  },
  
  // Default Profiles
  "terminal.integrated.defaultProfile.windows": "PowerShell",
  "terminal.integrated.defaultProfile.linux": "bash",
  "terminal.integrated.defaultProfile.osx": "zsh"
}
```

---

### terminal-lsp-suggest-kit/exercise-1-basic-lsp-setup/solution/python-environments/basic-env/requirements.txt

```
# Basic Python Environment for Terminal LSP Testing
# Core packages for demonstrating LSP completions

# Standard library enhancements
requests>=2.31.0
urllib3>=2.0.0

# Data manipulation
pandas>=2.0.0
numpy>=1.24.0

# Development tools
pytest>=7.4.0
black>=23.0.0
flake8>=6.0.0

# Documentation and type hints
mypy>=1.5.0
sphinx>=7.0.0

# Utility libraries for testing completions
click>=8.1.0
python-dotenv>=1.0.0
pydantic>=2.0.0

# Date and time utilities
python-dateutil>=2.8.0
pytz>=2023.3

# JSON and data serialization
ujson>=5.8.0
pyyaml>=6.0.1

# Logging and debugging
loguru>=0.7.0
rich>=13.5.0

# File system utilities
pathlib2>=2.3.0  # For older Python versions
watchdog>=3.0.0

# Network utilities
httpx>=0.24.0
aiohttp>=3.8.0

# Testing framework enhancements
pytest-cov>=4.1.0
pytest-mock>=3.11.0
```

---

### terminal-lsp-suggest-kit/exercise-1-basic-lsp-setup/solution/python-environments/basic-env/main.py

```python
"""
Main module for testing Terminal LSP suggestions.
This module provides various classes and functions to test autocompletion.
"""

import json
import os
import sys
from datetime import datetime, timedelta
from pathlib import Path
from typing import Dict, List, Optional, Union

import pandas as pd
import numpy as np
import requests
from rich.console import Console
from rich.table import Table

# Initialize rich console for beautiful output
console = Console()


class DataProcessor:
    """
    A class for processing various types of data.
    Great for testing method completions and documentation lookup.
    """
    
    def __init__(self, name: str, config: Optional[Dict] = None):
        """
        Initialize the DataProcessor.
        
        Args:
            name: Name of the processor
            config: Optional configuration dictionary
        """
        self.name = name
        self.config = config or {}
        self.processed_count = 0
        self.errors = []
        
    def load_data(self, source: Union[str, Path]) -> pd.DataFrame:
        """
        Load data from various sources.
        
        Args:
            source: Path to data file or URL
            
        Returns:
            DataFrame containing the loaded data
            
        Raises:
            FileNotFoundError: If source file doesn't exist
            ValueError: If data format is invalid
        """
        if isinstance(source, str) and source.startswith('http'):
            # Load from URL
            response = requests.get(source)
            response.raise_for_status()
            data = response.json()
            return pd.DataFrame(data)
        else:
            # Load from file
            source = Path(source)
            if not source.exists():
                raise FileNotFoundError(f"Data source not found: {source}")
                
            if source.suffix == '.csv':
                return pd.read_csv(source)
            elif source.suffix == '.json':
                return pd.read_json(source)
            elif source.suffix in ['.xlsx', '.xls']:
                return pd.read_excel(source)
            else:
                raise ValueError(f"Unsupported file format: {source.suffix}")
    
    def clean_data(self, df: pd.DataFrame) -> pd.DataFrame:
        """
        Clean the input dataframe.
        
        Args:
            df: Input dataframe to clean
            
        Returns:
            Cleaned dataframe
        """
        # Remove duplicates
        df = df.drop_duplicates()
        
        # Handle missing values
        numeric_columns = df.select_dtypes(include=[np.number]).columns
        df[numeric_columns] = df[numeric_columns].fillna(df[numeric_columns].mean())
        
        # Handle categorical columns
        categorical_columns = df.select_dtypes(include=['object']).columns
        df[categorical_columns] = df[categorical_columns].fillna('Unknown')
        
        return df
    
    def transform_data(self, df: pd.DataFrame, transformations: List[str]) -> pd.DataFrame:
        """
        Apply transformations to the dataframe.
        
        Args:
            df: Input dataframe
            transformations: List of transformation names
            
        Returns:
            Transformed dataframe
        """
        result_df = df.copy()
        
        for transformation in transformations:
            if transformation == 'normalize':
                numeric_columns = result_df.select_dtypes(include=[np.number]).columns
                result_df[numeric_columns] = (result_df[numeric_columns] - result_df[numeric_columns].mean()) / result_df[numeric_columns].std()
            elif transformation == 'log_transform':
                numeric_columns = result_df.select_dtypes(include=[np.number]).columns
                result_df[numeric_columns] = np.log1p(result_df[numeric_columns].abs())
            elif transformation == 'remove_outliers':
                numeric_columns = result_df.select_dtypes(include=[np.number]).columns
                for col in numeric_columns:
                    Q1 = result_df[col].quantile(0.25)
                    Q3 = result_df[col].quantile(0.75)
                    IQR = Q3 - Q1
                    lower_bound = Q1 - 1.5 * IQR
                    upper_bound = Q3 + 1.5 * IQR
                    result_df = result_df[(result_df[col] >= lower_bound) & (result_df[col] <= upper_bound)]
        
        return result_df
    
    def save_results(self, df: pd.DataFrame, output_path: Union[str, Path]) -> None:
        """
        Save processed data to file.
        
        Args:
            df: Dataframe to save
            output_path: Path where to save the file
        """
        output_path = Path(output_path)
        output_path.parent.mkdir(parents=True, exist_ok=True)
        
        if output_path.suffix == '.csv':
            df.to_csv(output_path, index=False)
        elif output_path.suffix == '.json':
            df.to_json(output_path, orient='records', indent=2)
        elif output_path.suffix in ['.xlsx', '.xls']:
            df.to_excel(output_path, index=False)
        
        self.processed_count += 1
        console.print(f"✅ Saved {len(df)} rows to {output_path}", style="green")
    
    def get_statistics(self) -> Dict:
        """
        Get processing statistics.
        
        Returns:
            Dictionary containing processing statistics
        """
        return {
            'processor_name': self.name,
            'processed_count': self.processed_count,
            'error_count': len(self.errors),
            'errors': self.errors,
            'last_processed': datetime.now().isoformat()
        }


class APIClient:
    """
    Simple API client for testing network-related completions.
    """
    
    def __init__(self, base_url: str, api_key: Optional[str] = None):
        """
        Initialize API client.
        
        Args:
            base_url: Base URL for the API
            api_key: Optional API key for authentication
        """
        self.base_url = base_url.rstrip('/')
        self.api_key = api_key
        self.session = requests.Session()
        
        if api_key:
            self.session.headers.update({'Authorization': f'Bearer {api_key}'})
    
    def get(self, endpoint: str, params: Optional[Dict] = None) -> Dict:
        """
        Make GET request to API.
        
        Args:
            endpoint: API endpoint
            params: Optional query parameters
            
        Returns:
            JSON response as dictionary
        """
        url = f"{self.base_url}/{endpoint.lstrip('/')}"
        response = self.session.get(url, params=params)
        response.raise_for_status()
        return response.json()
    
    def post(self, endpoint: str, data: Optional[Dict] = None) -> Dict:
        """
        Make POST request to API.
        
        Args:
            endpoint: API endpoint
            data: Optional request body data
            
        Returns:
            JSON response as dictionary
        """
        url = f"{self.base_url}/{endpoint.lstrip('/')}"
        response = self.session.post(url, json=data)
        response.raise_for_status()
        return response.json()


def create_sample_data(rows: int = 100) -> pd.DataFrame:
    """
    Create sample data for testing.
    
    Args:
        rows: Number of rows to generate
        
    Returns:
        DataFrame with sample data
    """
    np.random.seed(42)
    
    data = {
        'id': range(1, rows + 1),
        'name': [f'Item_{i}' for i in range(1, rows + 1)],
        'category': np.random.choice(['A', 'B', 'C', 'D'], rows),
        'value': np.random.uniform(10, 1000, rows),
        'score': np.random.normal(50, 15, rows),
        'is_active': np.random.choice([True, False], rows),
        'created_date': [
            (datetime.now() - timedelta(days=np.random.randint(0, 365))).date()
            for _ in range(rows)
        ]
    }
    
    return pd.DataFrame(data)


def demonstrate_completions():
    """
    Function to demonstrate various completion scenarios.
    Copy and paste these examples into the Python REPL to test completions.
    """
    examples = {
        'basic_imports': [
            'import os',
            'import sys',
            'import json',
            'from pathlib import Path',
            'from datetime import datetime, timedelta'
        ],
        'object_methods': [
            '"hello world".upper()',
            '[1, 2, 3].append(4)',
            '{"key": "value"}.get("key")',
            'datetime.now().strftime("%Y-%m-%d")'
        ],
        'pandas_operations': [
            'df = create_sample_data()',
            'df.head()',
            'df.describe()',
            'df.groupby("category").mean()',
            'df["value"].plot()'
        ],
        'numpy_operations': [
            'arr = np.array([1, 2, 3, 4, 5])',
            'arr.mean()',
            'arr.std()',
            'np.random.randint(1, 10, 5)'
        ]
    }
    
    return examples


if __name__ == "__main__":
    # Create sample processor for testing
    processor = DataProcessor("test_processor")
    sample_df = create_sample_data(50)
    
    console.print("📊 Sample data created!", style="bold green")
    console.print(f"Shape: {sample_df.shape}")
    
    # Display sample data
    table = Table(title="Sample Data Preview")
    for column in sample_df.columns:
        table.add_column(column)
    
    for _, row in sample_df.head().iterrows():
        table.add_row(*[str(value) for value in row])
    
    console.print(table)
    
    # Print completion examples
    console.print("\n🔍 Try these examples in Python REPL:", style="bold blue")
    examples = demonstrate_completions()
    
    for category, example_list in examples.items():
        console.print(f"\n{category.replace('_', ' ').title()}:", style="bold yellow")
        for example in example_list:
            console.print(f"  {example}", style="cyan")
```

This resource kit provides comprehensive hands-on experience with VS Code's Terminal Language Server Based Suggestions from version 1.101. The exercises cover basic LSP setup for Python REPL, advanced completions with context awareness, and workflow integration for productive terminal-based development.

Would you like me to continue with the next major feature? The next feature would be "Remote Development" which includes SSH pre-connection script and Remote Explorer improvements.
