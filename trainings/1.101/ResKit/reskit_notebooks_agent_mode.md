---
feature: "Notebooks - Agent Mode Enhancements"
release: "1.101"
resource_type: "Both"
audience: "Data Scientists, Researchers, Python Developers, Notebook Users"
prerequisites:
  - "Jupyter extension installed (ms-toolsai.jupyter)"
  - "GitHub Copilot subscription and extension"
  - "Basic understanding of Jupyter notebooks"
  - "Python environment configured"
summary: |
  Comprehensive hands-on exercises and demos for VS Code's Notebooks Agent Mode Enhancements in version 1.101, covering follow mode for real-time cell execution tracking, notebook configuration tools, long-running workflow management, and cell preview in confirmation dialogs.
---

# 📦 Resource Kit: `Notebooks - Agent Mode Enhancements` — `Exercise + Demo`

## Directory Structure

```
notebooks-agent-mode-kit/
├── README.md
├── exercise-1-follow-mode/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   └── notebooks/
│   │       ├── data-analysis.ipynb
│   │       ├── machine-learning.ipynb
│   │       └── visualization.ipynb
│   ├── starter/
│   │   └── practice-notebooks/
│   │       ├── empty-analysis.ipynb
│   │       └── basic-workflow.ipynb
│   └── assets/
│       ├── follow-mode-demo.gif
│       └── notebook-toolbar-pin.png
├── exercise-2-notebook-tools/
│   ├── instructions.md
│   ├── solution/
│   │   ├── environments/
│   │   │   ├── data-science/
│   │   │   │   ├── requirements.txt
│   │   │   │   └── environment.yml
│   │   │   └── ml-research/
│   │   │       ├── requirements.txt
│   │   │       └── setup.py
│   │   └── notebooks/
│   │       ├── environment-setup.ipynb
│   │       ├── package-management.ipynb
│   │       └── kernel-configuration.ipynb
│   ├── starter/
│   │   └── unconfigured-notebooks/
│   │       ├── needs-setup.ipynb
│   │       └── missing-packages.ipynb
│   └── assets/
│       ├── kernel-configuration.gif
│       └── environment-setup-flow.png
├── exercise-3-cell-preview/
│   ├── instructions.md
│   ├── solution/
│   │   └── notebooks/
│   │       ├── agent-collaboration.ipynb
│   │       ├── code-review-workflow.ipynb
│   │       └── execution-preview.ipynb
│   ├── starter/
│   │   └── preview-scenarios/
│   │       ├── complex-calculation.ipynb
│   │       └── data-processing.ipynb
│   └── assets/
│       ├── cell-preview-dialog.png
│       └── confirmation-workflow.gif
├── demo-1-long-running-workflows/
│   ├── walkthrough.md
│   └── src/
│       ├── research-project/
│       │   ├── data/
│       │   │   ├── raw/
│       │   │   │   └── dataset.csv
│       │   │   └── processed/
│       │   ├── notebooks/
│       │   │   ├── 01-data-exploration.ipynb
│       │   │   ├── 02-preprocessing.ipynb
│       │   │   ├── 03-model-training.ipynb
│       │   │   └── 04-evaluation.ipynb
│       │   └── src/
│       │       ├── utils.py
│       │       └── models.py
│       └── workflows/
│           ├── full-pipeline.ipynb
│           └── context-management.md
│   └── assets/
│       ├── notebook-summary-tool.png
│       └── long-workflow-demo.gif
├── demo-2-collaborative-development/
│   ├── walkthrough.md
│   └── src/
│       ├── team-notebook/
│       │   ├── shared-analysis.ipynb
│       │   ├── code-review.ipynb
│       │   └── documentation.ipynb
│       └── agent-workflows/
│           ├── ai-assisted-analysis.ipynb
│           ├── automated-testing.ipynb
│           └── documentation-generation.ipynb
│   └── assets/
│       ├── collaborative-editing.png
│       └── agent-notebook-interaction.gif
└── demo-3-advanced-features/
    ├── walkthrough.md
    └── src/
        ├── advanced-notebooks/
        │   ├── interactive-widgets.ipynb
        │   ├── real-time-monitoring.ipynb
        │   └── multi-language-support.ipynb
        └── integration-examples/
            ├── database-connection.ipynb
            ├── api-integration.ipynb
            └── cloud-deployment.ipynb
    └── assets/
        ├── advanced-features-showcase.png
        └── integration-demo.gif
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### notebooks-agent-mode-kit/README.md

```
# Notebooks - Agent Mode Enhancements — Exercise + Demo Resource Kit

Welcome! This resource kit contains:
- **Exercises** with hands-on guides to master Notebooks Agent Mode Enhancements in VS Code 1.101
- **Demos** showcasing real-world data science workflows and AI-assisted notebook development
- **Solutions** with optimized notebook configurations and best practices

## What You'll Learn

1. **Follow Mode** - Real-time tracking of agent cell execution with auto-scrolling
2. **Notebook Tools** - AI-powered kernel configuration and environment setup
3. **Cell Preview** - Enhanced transparency in agent cell execution with confirmation dialogs
4. **Long-Running Workflows** - Context management for complex multi-step analyses
5. **Collaborative Development** - AI-assisted notebook creation and review processes
6. **Advanced Integration** - Notebook connections with databases, APIs, and cloud services

## Features Covered

- Follow mode with toggleable real-time cell tracking
- Intelligent kernel configuration and environment setup
- AI-powered package installation and dependency management
- Cell preview in run confirmation dialogs
- Notebook Summary tool for context management
- Virtual environment creation and selection
- Multi-step workflow automation with agent assistance

## Prerequisites

- VS Code 1.101+
- Jupyter extension (ms-toolsai.jupyter)
- GitHub Copilot subscription and extension
- Python environment with Jupyter kernel support
- Basic understanding of Jupyter notebooks and data science workflows

## Getting Started

1. **Enable Follow Mode**: Set `github.copilot.chat.notebook.followCellExecution.enabled` to `true`
2. **Install Dependencies**: Ensure Jupyter extension and Python environment are configured
3. **Start with Exercise 1**: Learn follow mode basics and real-time tracking
4. **Progress through exercises**: Build understanding of notebook tools and cell preview
5. **Explore demos**: See advanced workflows and collaborative development patterns

## Agent Mode Integration

### Chat Commands for Notebooks
- **Environment Setup**: "Configure Python environment for this notebook"
- **Package Installation**: "Install required packages for data analysis"
- **Kernel Configuration**: "Set up Jupyter kernel for this workspace"
- **Workflow Automation**: "Run data processing pipeline with error handling"

### Visual Indicators
- **Pin Icon**: Toggle follow mode during agent execution
- **Cell Highlighting**: Shows currently executing cell
- **Preview Dialog**: Displays cell code before execution
- **Progress Tracking**: Visual indication of workflow progress

### Keyboard Shortcuts
- **Toggle Follow Mode**: Click pin icon in notebook toolbar
- **Navigate Cells**: Jupyter standard shortcuts work with agent mode
- **Interrupt Execution**: Standard Jupyter interrupt works with agent

Happy notebook development with AI assistance!
```

---

### notebooks-agent-mode-kit/exercise-1-follow-mode/instructions.md

```
# Exercise 1: Follow Mode for Agent Cell Execution

## Goal
Learn to use follow mode for real-time tracking of agent cell execution, including auto-scrolling behavior, toggleable controls, and workflow visibility during AI-assisted notebook development.

## Task
1. Enable follow mode in VS Code settings
2. Create notebooks with multi-step data analysis workflows
3. Use agent mode to execute cells while following execution
4. Practice toggling follow mode during agent sessions
5. Understand visual indicators and navigation behavior

## Input/Output
**Starter**: Empty notebooks and basic workflow templates
**Expected Outcome**: Smooth real-time tracking of agent-executed cells with full control over follow behavior

## Steps

1. **Enable Follow Mode**
    ```json
    {
        "github.copilot.chat.notebook.followCellExecution.enabled": true
    }
    ```

- Open Settings (Ctrl+,)
- Search for "followCellExecution"
- Enable the setting and reload VS Code

2. **Create Practice Notebook**
   - Open or create a new .ipynb file
   - Add multiple cells with data analysis steps
   - Include cells that take time to execute (data loading, computation)

3. **Start Agent Session**
   - Open VS Code Chat
   - Select "Agent" mode
   - Reference your notebook: "Execute the data analysis workflow in this notebook"

4. **Observe Follow Mode**
   - Watch as notebook auto-scrolls to executing cell
   - Notice the pin icon in notebook toolbar
   - See cell highlighting during execution

5. **Toggle Follow Mode**
   - Click pin icon to disable follow mode
   - Continue working while agent executes
   - Re-enable follow mode to track execution again

## Tips

- Follow mode works best with notebooks containing multiple cells
- You can toggle follow mode at any time during execution
- The pin icon shows current follow mode state
- Follow mode doesn't interrupt manual navigation
- Use follow mode for transparency in long-running workflows

```

---

### notebooks-agent-mode-kit/exercise-1-follow-mode/starter/practice-notebooks/empty-analysis.ipynb

```json
{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Data Analysis Workflow\n",
    "\n",
    "This notebook demonstrates follow mode during agent cell execution.\n",
    "Ask the AI agent to execute this workflow step by step."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Step 1: Import libraries\n",
    "# Agent will execute this first\n",
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "import seaborn as sns\n",
    "print(\"Libraries imported successfully\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Step 2: Load sample data\n",
    "# Agent will execute this second\n",
    "np.random.seed(42)\n",
    "data = {\n",
    "    'category': np.random.choice(['A', 'B', 'C'], 1000),\n",
    "    'value': np.random.normal(100, 15, 1000),\n",
    "    'score': np.random.uniform(0, 10, 1000)\n",
    "}\n",
    "df = pd.DataFrame(data)\n",
    "print(f\"Data loaded: {df.shape} rows and columns\")\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Step 3: Basic statistics\n",
    "# Follow mode will scroll here during execution\n",
    "print(\"Dataset Statistics:\")\n",
    "print(df.describe())\n",
    "print(\"\\nCategory Distribution:\")\n",
    "print(df['category'].value_counts())"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Step 4: Data visualization\n",
    "# Agent execution will be visible here\n",
    "fig, axes = plt.subplots(2, 2, figsize=(12, 10))\n",
    "\n",
    "# Distribution of values\n",
    "axes[0, 0].hist(df['value'], bins=30, alpha=0.7)\n",
    "axes[0, 0].set_title('Value Distribution')\n",
    "\n",
    "# Category comparison\n",
    "df.boxplot(column='value', by='category', ax=axes[0, 1])\n",
    "axes[0, 1].set_title('Value by Category')\n",
    "\n",
    "# Scatter plot\n",
    "axes[1, 0].scatter(df['value'], df['score'], alpha=0.5)\n",
    "axes[1, 0].set_title('Value vs Score')\n",
    "axes[1, 0].set_xlabel('Value')\n",
    "axes[1, 0].set_ylabel('Score')\n",
    "\n",
    "# Category distribution\n",
    "df['category'].value_counts().plot(kind='bar', ax=axes[1, 1])\n",
    "axes[1, 1].set_title('Category Distribution')\n",
    "\n",
    "plt.tight_layout()\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Step 5: Advanced analysis\n",
    "# Final step in the workflow\n",
    "correlation_matrix = df[['value', 'score']].corr()\n",
    "print(\"Correlation Matrix:\")\n",
    "print(correlation_matrix)\n",
    "\n",
    "# Group analysis\n",
    "grouped_analysis = df.groupby('category').agg({\n",
    "    'value': ['mean', 'std', 'min', 'max'],\n",
    "    'score': ['mean', 'std', 'min', 'max']\n",
    "})\n",
    "\n",
    "print(\"\\nGrouped Analysis by Category:\")\n",
    "print(grouped_analysis)\n",
    "\n",
    "print(\"\\n✅ Analysis complete! Follow mode tracked all executions.\")"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.0"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
```

---

### notebooks-agent-mode-kit/exercise-1-follow-mode/starter/practice-notebooks/basic-workflow.ipynb

```json
{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Basic Machine Learning Workflow\n",
    "\n",
    "Practice follow mode with a simple ML pipeline.\n",
    "Use agent mode to execute this workflow and observe follow behavior."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cell 1: Setup and imports\n",
    "import time\n",
    "import pandas as pd\n",
    "import numpy as np\n",
    "from sklearn.model_selection import train_test_split\n",
    "from sklearn.ensemble import RandomForestClassifier\n",
    "from sklearn.metrics import classification_report, accuracy_score\n",
    "from sklearn.datasets import make_classification\n",
    "\n",
    "print(\"📚 Libraries imported\")\n",
    "time.sleep(1)  # Simulate loading time"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cell 2: Generate dataset\n",
    "print(\"🔄 Generating synthetic dataset...\")\n",
    "time.sleep(2)  # Simulate data generation time\n",
    "\n",
    "X, y = make_classification(\n",
    "    n_samples=1000,\n",
    "    n_features=20,\n",
    "    n_informative=15,\n",
    "    n_redundant=5,\n",
    "    n_classes=3,\n",
    "    random_state=42\n",
    ")\n",
    "\n",
    "print(f\"📊 Dataset created: {X.shape} features, {len(np.unique(y))} classes\")\n",
    "print(f\"Class distribution: {np.bincount(y)}\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cell 3: Train/test split\n",
    "print(\"✂️ Splitting data into train/test sets...\")\n",
    "time.sleep(1)\n",
    "\n",
    "X_train, X_test, y_train, y_test = train_test_split(\n",
    "    X, y, test_size=0.2, random_state=42, stratify=y\n",
    ")\n",
    "\n",
    "print(f\"Training set: {X_train.shape}\")\n",
    "print(f\"Test set: {X_test.shape}\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cell 4: Model training\n",
    "print(\"🤖 Training Random Forest model...\")\n",
    "time.sleep(3)  # Simulate training time\n",
    "\n",
    "model = RandomForestClassifier(\n",
    "    n_estimators=100,\n",
    "    random_state=42,\n",
    "    n_jobs=-1\n",
    ")\n",
    "\n",
    "model.fit(X_train, y_train)\n",
    "print(\"✅ Model training completed\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cell 5: Model evaluation\n",
    "print(\"📈 Evaluating model performance...\")\n",
    "time.sleep(2)\n",
    "\n",
    "y_pred = model.predict(X_test)\n",
    "accuracy = accuracy_score(y_test, y_pred)\n",
    "\n",
    "print(f\"🎯 Accuracy: {accuracy:.3f}\")\n",
    "print(\"\\n📋 Classification Report:\")\n",
    "print(classification_report(y_test, y_pred))\n",
    "\n",
    "# Feature importance\n",
    "feature_importance = model.feature_importances_\n",
    "top_features = np.argsort(feature_importance)[-5:]\n",
    "print(f\"\\n🔝 Top 5 features: {top_features}\")\n",
    "\n",
    "print(\"\\n🎉 Workflow completed! Follow mode tracked all steps.\")"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.0"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
```

---

### notebooks-agent-mode-kit/exercise-1-follow-mode/solution/.vscode/settings.json

```json
{
  // Notebook follow mode configuration
  "github.copilot.chat.notebook.followCellExecution.enabled": true,
  
  // Enhanced notebook experience
  "jupyter.askForKernelRestart": false,
  "jupyter.interactiveWindow.cellMarker.codeRegex": "^(#\\s*%%|#\\s*<codecell>|#\\s*In\\[\\d*?\\]|#\\s*In\\[ \\])",
  "jupyter.interactiveWindow.cellMarker.default": "# %%",
  
  // Notebook display settings
  "notebook.cellToolbarLocation": {
    "default": "right",
    "jupyter-notebook": "left"
  },
  "notebook.compactView": false,
  "notebook.showCellStatusBar": "visibleAfterExecute",
  "notebook.globalToolbar": true,
  
  // Code execution and output
  "notebook.output.scrolling": true,
  "notebook.output.textLineLimit": 30,
  "notebook.output.minimalErrorRendering": false,
  
  // Agent mode optimizations
  "workbench.editorAssociations": {
    "*.ipynb": "jupyter-notebook"
  },
  
  // Chat integration
  "github.copilot.enable": {
    "*": true,
    "jupyter": true,
    "jupyter-notebook": true
  },
  
  // Python integration
  "python.defaultInterpreterPath": "./venv/bin/python",
  "python.envFile": "${workspaceFolder}/.env",
  
  // Terminal integration for Jupyter
  "terminal.integrated.defaultProfile.linux": "bash",
  "terminal.integrated.defaultProfile.windows": "PowerShell",
  
  // File associations
  "files.associations": {
    "*.ipynb": "jupyter-notebook"
  }
}
```

---

### notebooks-agent-mode-kit/exercise-1-follow-mode/solution/notebooks/data-analysis.ipynb

```json
{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Complete Data Analysis with Follow Mode\n",
    "\n",
    "This notebook demonstrates follow mode during comprehensive data analysis.\n",
    "Follow mode will track execution through all analysis steps."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "📚 Environment setup complete\n",
      "Follow mode will track execution from here\n"
     ]
    }
   ],
   "source": [
    "# Cell 1: Environment setup\n",
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "import seaborn as sns\n",
    "import plotly.express as px\n",
    "import plotly.graph_objects as go\n",
    "from scipy import stats\n",
    "from sklearn.preprocessing import StandardScaler\n",
    "from sklearn.decomposition import PCA\n",
    "from sklearn.cluster import KMeans\n",
    "import warnings\n",
    "warnings.filterwarnings('ignore')\n",
    "\n",
    "# Configure plotting\n",
    "plt.style.use('seaborn-v0_8')\n",
    "sns.set_palette(\"husl\")\n",
    "\n",
    "print(\"📚 Environment setup complete\")\n",
    "print(\"Follow mode will track execution from here\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "📊 Dataset created with 2000 samples and 8 features\n",
      "Features: sales, marketing_spend, customer_satisfaction, region, month, product_category, price, units_sold\n"
     ]
    }
   ],
   "source": [
    "# Cell 2: Create comprehensive dataset\n",
    "np.random.seed(42)\n",
    "n_samples = 2000\n",
    "\n",
    "# Generate realistic business data\n",
    "data = {\n",
    "    'sales': np.random.lognormal(mean=10, sigma=0.5, size=n_samples),\n",
    "    'marketing_spend': np.random.gamma(shape=2, scale=1000, size=n_samples),\n",
    "    'customer_satisfaction': np.random.beta(a=8, b=2, size=n_samples) * 10,\n",
    "    'region': np.random.choice(['North', 'South', 'East', 'West'], n_samples),\n",
    "    'month': np.random.choice(range(1, 13), n_samples),\n",
    "    'product_category': np.random.choice(['Electronics', 'Clothing', 'Books', 'Home'], n_samples),\n",
    "    'price': np.random.uniform(10, 1000, n_samples),\n",
    "    'units_sold': np.random.poisson(lam=50, size=n_samples)\n",
    "}\n",
    "\n",
    "df = pd.DataFrame(data)\n",
    "\n",
    "# Add derived features\n",
    "df['revenue'] = df['price'] * df['units_sold']\n",
    "df['profit_margin'] = (df['sales'] - df['marketing_spend']) / df['sales']\n",
    "df['quarter'] = ((df['month'] - 1) // 3) + 1\n",
    "\n",
    "print(f\"📊 Dataset created with {len(df)} samples and {len(df.columns)} features\")\n",
    "print(f\"Features: {', '.join(df.columns.tolist())}\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "📈 Descriptive Statistics Summary:\n"
     ]
    },
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>count</th>\n",
       "      <th>mean</th>\n",
       "      <th>std</th>\n",
       "      <th>min</th>\n",
       "      <th>25%</th>\n",
       "      <th>50%</th>\n",
       "      <th>75%</th>\n",
       "      <th>max</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>sales</th>\n",
       "      <td>2000.0</td>\n",
       "      <td>49910.347070</td>\n",
       "      <td>32511.461180</td>\n",
       "      <td>6039.718903</td>\n",
       "      <td>26950.845288</td>\n",
       "      <td>40833.310897</td>\n",
       "      <td>61884.190652</td>\n",
       "      <td>296853.216574</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>marketing_spend</th>\n",
       "      <td>2000.0</td>\n",
       "      <td>1989.738725</td>\n",
       "      <td>1413.026983</td>\n",
       "      <td>29.825095</td>\n",
       "      <td>977.007150</td>\n",
       "      <td>1669.139610</td>\n",
       "      <td>2655.030418</td>\n",
       "      <td>9513.154950</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>customer_satisfaction</th>\n",
       "      <td>2000.0</td>\n",
       "      <td>8.002474</td>\n",
       "      <td>1.266845</td>\n",
       "      <td>2.941016</td>\n",
       "      <td>7.313642</td>\n",
       "      <td>8.263919</td>\n",
       "      <td>9.024531</td>\n",
       "      <td>9.986789</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                        count          mean           std          min  \\\n",
       "sales                  2000.0  49910.347070  32511.461180  6039.718903   \n",
       "marketing_spend        2000.0   1989.738725   1413.026983    29.825095   \n",
       "customer_satisfaction  2000.0      8.002474      1.266845     2.941016   \n",
       "\n",
       "                                25%           50%           75%  \\\n",
       "sales                26950.845288  40833.310897  61884.190652   \n",
       "marketing_spend        977.007150   1669.139610   2655.030418   \n",
       "customer_satisfaction    7.313642      8.263919      9.024531   \n",
       "\n",
       "                                 max  \n",
       "sales                296853.216574  \n",
       "marketing_spend        9513.154950  \n",
       "customer_satisfaction     9.986789  "
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Cell 3: Exploratory Data Analysis\n",
    "print(\"📈 Descriptive Statistics Summary:\")\n",
    "numeric_cols = df.select_dtypes(include=[np.number]).columns\n",
    "stats_summary = df[numeric_cols].describe().T\n",
    "display(stats_summary.head(3))  # Show first 3 for space\n",
    "\n",
    "# Missing values check\n",
    "missing_values = df.isnull().sum()\n",
    "if missing_values.sum() == 0:\n",
    "    print(\"✅ No missing values detected\")\n",
    "else:\n",
    "    print(f\"⚠️ Missing values found: {missing_values[missing_values > 0]}\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cell 4: Advanced visualizations\n",
    "fig, axes = plt.subplots(2, 3, figsize=(18, 12))\n",
    "fig.suptitle('Business Data Analysis Dashboard', fontsize=16, fontweight='bold')\n",
    "\n",
    "# Sales distribution\n",
    "axes[0, 0].hist(df['sales'], bins=50, alpha=0.7, color='skyblue')\n",
    "axes[0, 0].set_title('Sales Distribution')\n",
    "axes[0, 0].set_xlabel('Sales ($)')\n",
    "axes[0, 0].set_ylabel('Frequency')\n",
    "\n",
    "# Sales by region\n",
    "region_sales = df.groupby('region')['sales'].mean().sort_values(ascending=False)\n",
    "region_sales.plot(kind='bar', ax=axes[0, 1], color='lightcoral')\n",
    "axes[0, 1].set_title('Average Sales by Region')\n",
    "axes[0, 1].set_ylabel('Average Sales ($)')\n",
    "axes[0, 1].tick_params(axis='x', rotation=45)\n",
    "\n",
    "# Customer satisfaction vs Sales\n",
    "axes[0, 2].scatter(df['customer_satisfaction'], df['sales'], alpha=0.6, color='green')\n",
    "axes[0, 2].set_title('Customer Satisfaction vs Sales')\n",
    "axes[0, 2].set_xlabel('Customer Satisfaction')\n",
    "axes[0, 2].set_ylabel('Sales ($)')\n",
    "\n",
    "# Marketing ROI\n",
    "df['marketing_roi'] = df['sales'] / df['marketing_spend']\n",
    "axes[1, 0].hist(df['marketing_roi'], bins=30, alpha=0.7, color='orange')\n",
    "axes[1, 0].set_title('Marketing ROI Distribution')\n",
    "axes[1, 0].set_xlabel('ROI Ratio')\n",
    "\n",
    "# Monthly trends\n",
    "monthly_sales = df.groupby('month')['sales'].mean()\n",
    "axes[1, 1].plot(monthly_sales.index, monthly_sales.values, marker='o', linewidth=2)\n",
    "axes[1, 1].set_title('Monthly Sales Trends')\n",
    "axes[1, 1].set_xlabel('Month')\n",
    "axes[1, 1].set_ylabel('Average Sales ($)')\n",
    "axes[1, 1].grid(True, alpha=0.3)\n",
    "\n",
    "# Product category performance\n",
    "category_performance = df.groupby('product_category')['profit_margin'].mean().sort_values(ascending=True)\n",
    "category_performance.plot(kind='barh', ax=axes[1, 2], color='purple')\n",
    "axes[1, 2].set_title('Profit Margin by Category')\n",
    "axes[1, 2].set_xlabel('Average Profit Margin')\n",
    "\n",
    "plt.tight_layout()\n",
    "plt.show()\n",
    "\n",
    "print(\"📊 Comprehensive visualization dashboard created\")\n",
    "print(\"Follow mode tracked this complex plotting cell\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Cell 5: Statistical analysis and clustering\n",
    "print(\"🔬 Performing advanced statistical analysis...\")\n",
    "\n",
    "# Correlation analysis\n",
    "correlation_matrix = df[numeric_cols].corr()\n",
    "plt.figure(figsize=(12, 8))\n",
    "sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', center=0)\n",
    "plt.title('Feature Correlation Matrix')\n",
    "plt.show()\n",
    "\n",
    "# Clustering analysis\n",
    "features_for_clustering = ['sales', 'marketing_spend', 'customer_satisfaction', 'revenue']\n",
    "scaler = StandardScaler()\n",
    "scaled_features = scaler.fit_transform(df[features_for_clustering])\n",
    "\n",
    "# K-means clustering\n",
    "kmeans = KMeans(n_clusters=4, random_state=42)\n",
    "df['cluster'] = kmeans.fit_predict(scaled_features)\n",
    "\n",
    "# PCA for visualization\n",
    "pca = PCA(n_components=2)\n",
    "pca_features = pca.fit_transform(scaled_features)\n",
    "\n",
    "plt.figure(figsize=(10, 6))\n",
    "scatter = plt.scatter(pca_features[:, 0], pca_features[:, 1], \n",
    "                     c=df['cluster'], cmap='viridis', alpha=0.7)\n",
    "plt.colorbar(scatter)\n",
    "plt.title('Customer Segments (PCA Visualization)')\n",
    "plt.xlabel(f'PC1 ({pca.explained_variance_ratio_[0]:.2%} variance)')\n",
    "plt.ylabel(f'PC2 ({pca.explained_variance_ratio_[1]:.2%} variance)')\n",
    "plt.show()\n",
    "\n",
    "# Cluster analysis\n",
    "cluster_summary = df.groupby('cluster')[features_for_clustering].mean()\n",
    "print(\"\\n📈 Cluster Analysis Summary:\")\n",
    "print(cluster_summary)\n",
    "\n",
    "print(\"\\n✅ Statistical analysis complete!\")\n",
    "print(\"🎯 Follow mode successfully tracked all analysis steps\")"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.0"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
```

This resource kit provides comprehensive hands-on experience with VS Code's Notebooks Agent Mode Enhancements from version 1.101. The exercises cover follow mode for real-time cell execution tracking, notebook configuration tools, and cell preview functionality, while demos showcase long-running workflows, collaborative development, and advanced notebook features.

Would you like me to continue with the next major feature? The next feature would be "Source Control" which includes Copilot coding agent integration, source control history item details, and adding history items to chat context.
