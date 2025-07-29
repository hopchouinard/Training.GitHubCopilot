---
feature: "Notebooks - Agent Mode Enhancements"
release: "1.101"
prerequisites:
  - "Jupyter extension installed (ms-toolsai.jupyter)"
  - "GitHub Copilot subscription and extension"
  - "Basic understanding of Jupyter notebooks"
  - "Python environment configured"
audience: "Data Scientists, Researchers, Python Developers, Notebook Users"
---

# 🚀 Feature Training: `Notebooks - Agent Mode Enhancements` in VS Code `1.101`

## 1. Overview

- **Feature Name:** `Notebooks - Agent Mode Enhancements`
- **Release Version:** `1.101`
- **Feature Type:** `AI-Assisted Notebook Development, Productivity Enhancement`
- **Summary:**  
  Comprehensive notebook enhancements including follow mode for real-time tracking of agent cell execution, intelligent notebook configuration tools, long-running workflow support with context management, and cell preview in confirmation dialogs. These features transform Jupyter notebooks into AI-collaborative environments for data science and research workflows.

## 2. Why It Matters

- **Core Problem Solved:** Eliminates friction in notebook setup and execution by providing AI-powered assistance for environment configuration, kernel management, and autonomous cell execution with full transparency and control.
- **Target Users:** Data scientists, researchers, Python developers, educators, and students working with Jupyter notebooks for analysis, visualization, and experimentation.
- **Context:** Features require Jupyter extension and GitHub Copilot. Follow mode is configurable and can be toggled during agent sessions.

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.101+`
- Jupyter extension: `ms-toolsai.jupyter`
- GitHub Copilot extension with active subscription
- Python environment with kernel support
- Basic understanding of notebook cell types and execution

### 3.2 How to Enable/Access

- **Follow Mode:** Settings → `github.copilot.chat.notebook.followCellExecution.enabled` → `true`
- **Agent Mode:** Open Chat → Select "Agent" mode → Work with notebook files
- **Notebook Tools:** Automatic in agent mode when working with `.ipynb` files
- **Toggle Follow Mode:** Use pin icon in notebook toolbar during agent execution

### 3.3 Step-by-Step Usage

#### 3.3.1 Follow Mode for Agent Cell Execution

1. **Enable Follow Mode:** Settings → Enable `github.copilot.chat.notebook.followCellExecution.enabled`
2. **Start Agent Session:** Open Chat → Select Agent mode → Reference your notebook
3. **Observe Pin Icon:** When agent runs cells, pin icon appears in notebook toolbar
4. **Real-time Following:** Notebook automatically scrolls to currently executing cell
5. **Toggle During Session:** Click pin icon to enable/disable follow mode without changing settings
6. **Manual Control:** Disable follow mode to review specific sections while agent continues

**Example Workflow:**

```
User: "Analyze this dataset and create visualizations"
→ Agent starts executing cells
→ Follow mode scrolls to show each cell as it runs
→ You can toggle pin icon to stop/resume following
→ Review completed work while agent continues with remaining tasks
```

#### 3.3.2 Notebook Configuration Tools

1. **Automatic Kernel Setup:** Agent detects notebook requirements and suggests kernel configuration
2. **Environment Creation:** Tool guides through virtual environment creation when needed
3. **Dependency Installation:** Agent installs required packages automatically with confirmation
4. **Python Environment Selection:** Prompts for existing environment selection if multiple available

**Configuration Process:**

```
Agent detects notebook → Checks kernel status → Suggests environment setup
→ Creates virtual environment (if needed) → Installs dependencies
→ Configures notebook kernel → Ready for cell execution
```

#### 3.3.3 Long-Running Workflow Support

1. **Context Preservation:** Internal Notebook Summary tool maintains context across long sessions
2. **History Management:** Agent summarizes conversation history when context becomes large
3. **Continuous Operation:** Agent maintains progress through complex multi-step analyses
4. **Error Recovery:** Agent handles errors and continues with alternative approaches

#### 3.3.4 Cell Preview in Confirmations

1. **Execution Confirmation:** Agent shows code snippet before running cells
2. **Cell Navigation:** Click cell links in Chat view to jump to specific cells
3. **Preview Content:** See exactly what code will be executed before approval
4. **Direct Navigation:** Links provide immediate access to referenced cells

### 3.4 Example(s)

#### Simple Example: Data Analysis with Follow Mode

```python
# User prompt: "Load and analyze sales data from sales.csv"

# Agent creates and executes cells (with follow mode tracking):

# Cell 1: Import libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Cell 2: Load data
df = pd.read_csv('sales.csv')
df.head()

# Cell 3: Basic analysis
df.describe()

# Follow mode scrolls to show each cell execution in real-time
```

#### Advanced Example: Complete Data Science Workflow

```python
# User prompt: "Perform complete EDA and build a prediction model"

# Agent workflow with configuration tools:
# 1. Configure environment (creates venv, installs scikit-learn, pandas, etc.)
# 2. Load and explore data
# 3. Data cleaning and preprocessing
# 4. Feature engineering
# 5. Model training and evaluation
# 6. Visualization of results

# Long-running workflow maintains context throughout
# Cell preview shows each step before execution
# Follow mode tracks progress across dozens of cells
```

#### Interactive Example: Error Handling and Recovery

```python
# Agent encounters error in cell:
try:
    result = df.groupby('invalid_column').sum()
except KeyError as e:
    print(f"Column not found: {e}")
    # Agent analyzes available columns
    print("Available columns:", df.columns.tolist())
    # Agent suggests correction and continues
```

## 4. Troubleshooting & FAQ

### Common Issues

- **Follow Mode Not Working:** Ensure `github.copilot.chat.notebook.followCellExecution.enabled` is true and restart VS Code
- **Kernel Configuration Fails:** Check Python environment and ensure Jupyter extension is active
- **Agent Can't Execute Cells:** Verify notebook kernel is running and Copilot has necessary permissions
- **Cell Preview Missing:** Ensure you're in agent mode and working with `.ipynb` files

### How to Disable

- **Disable Follow Mode:** Settings → `github.copilot.chat.notebook.followCellExecution.enabled` → `false`
- **Temporary Toggle:** Click pin icon in notebook toolbar during agent session
- **Disable Notebook Tools:** Switch to different chat modes (Ask/Edit instead of Agent)
- **Manual Kernel Control:** Configure kernel manually without agent assistance

### Edge Cases

- **Large Notebooks:** Follow mode may impact performance with very large notebooks (>100 cells)
- **Multiple Kernels:** Agent may need guidance when multiple Python environments are available
- **Network Dependencies:** Package installation may fail in restricted network environments
- **Kernel Crashes:** Agent will attempt to restart kernel and resume operations

### FAQ

**Q: Can I use follow mode with non-Python notebooks?**
A: Follow mode works with any Jupyter kernel, but notebook tools are optimized for Python environments.

**Q: Does the agent save notebook changes automatically?**
A: Yes, changes are saved automatically, but you can undo specific cell executions if needed.

**Q: Can I interrupt long-running agent operations?**
A: Yes, use the stop button in chat or interrupt kernel execution in the notebook.

**Q: How does context management work with very long sessions?**
A: The agent uses internal summarization to maintain relevant context while discarding older, less relevant information.

## 5. Additional Resources

- **Jupyter Extension:** [VS Code Jupyter Documentation](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
- **Notebooks with AI Guide:** [AI-Powered Notebook Workflows](https://code.visualstudio.com/docs/copilot/guides/notebooks-with-ai)
- **Copilot Chat:** [Working with Chat in Notebooks](https://code.visualstudio.com/docs/copilot/chat/copilot-chat)
- **Python Environments:** [Python Environment Management](https://code.visualstudio.com/docs/python/environments)
- **Related Features:** Agent Mode, Chat Improvements, Python Extension Tools

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-28  | Assistant | Initial micro-training for Notebook Agent Mode features |
