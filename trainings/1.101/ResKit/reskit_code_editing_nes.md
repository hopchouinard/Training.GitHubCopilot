---
feature: "Code Editing - NES (Next Edit Suggestions)"
release: "1.101"
resource_type: "Both"
audience: "Developers, Programmers working with TypeScript/JavaScript/Python"
prerequisites:
  - "GitHub Copilot subscription and extension installed"
  - "Basic understanding of TypeScript, JavaScript, or Python"
  - "Familiarity with import statements and code refactoring"
summary: |
  Comprehensive hands-on exercises and demos for VS Code's Next Edit Suggestions (NES) improvements in version 1.101, covering AI-powered import suggestions, seamless keyboard navigation, enhanced accuracy for TypeScript/JavaScript/Python, and optimized refactoring workflows.
---

# 📦 Resource Kit: `Code Editing - NES (Next Edit Suggestions)` — `Exercise + Demo`

## Directory Structure

```
code-editing-nes-kit/
├── README.md
├── exercise-1-import-suggestions/
│   ├── instructions.md
│   ├── solution/
│   │   ├── typescript-project/
│   │   │   ├── src/
│   │   │   │   ├── main.ts
│   │   │   │   ├── utils/
│   │   │   │   │   ├── helpers.ts
│   │   │   │   │   └── validators.ts
│   │   │   │   └── components/
│   │   │   │       ├── Button.tsx
│   │   │   │       └── Modal.tsx
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   ├── javascript-project/
│   │   │   ├── src/
│   │   │   │   ├── index.js
│   │   │   │   ├── lib/
│   │   │   │   │   ├── api.js
│   │   │   │   │   └── utils.js
│   │   │   │   └── modules/
│   │   │   │       ├── auth.js
│   │   │   │       └── storage.js
│   │   │   └── package.json
│   │   └── python-project/
│   │       ├── src/
│   │       │   ├── main.py
│   │       │   ├── utils/
│   │       │   │   ├── __init__.py
│   │       │   │   ├── helpers.py
│   │       │   │   └── validators.py
│   │       │   └── models/
│   │       │       ├── __init__.py
│   │       │       ├── user.py
│   │       │       └── product.py
│   │       └── requirements.txt
│   ├── starter/
│   │   ├── incomplete-ts-file.ts
│   │   ├── incomplete-js-file.js
│   │   └── incomplete-py-file.py
│   └── assets/
│       ├── nes-import-suggestion.gif
│       └── import-gutter-indicator.png
├── exercise-2-acceptance-flow/
│   ├── instructions.md
│   ├── solution/
│   │   ├── keyboard-navigation/
│   │   │   ├── workflow-examples.md
│   │   │   └── keyboard-shortcuts.md
│   │   └── scenarios/
│   │       ├── multiple-imports.ts
│   │       ├── refactoring-workflow.js
│   │       └── dependency-updates.py
│   ├── starter/
│   │   └── practice-scenarios/
│   │       ├── scenario-1.ts
│   │       ├── scenario-2.js
│   │       └── scenario-3.py
│   └── assets/
│       ├── tab-navigation-flow.gif
│       └── acceptance-workflow.png
├── exercise-3-multi-language-support/
│   ├── instructions.md
│   ├── solution/
│   │   ├── .vscode/
│   │   │   └── settings.json
│   │   └── cross-language-examples/
│   │       ├── ts-react-component.tsx
│   │       ├── js-node-service.js
│   │       └── python-api-client.py
│   ├── starter/
│   │   └── language-templates/
│   │       ├── basic-ts.ts
│   │       ├── basic-js.js
│   │       └── basic-py.py
│   └── assets/
│       ├── language-support-comparison.png
│       └── python-imports-demo.gif
├── demo-1-refactoring-workflow/
│   ├── walkthrough.md
│   └── src/
│       ├── legacy-codebase/
│       │   ├── old-auth.js
│       │   ├── old-utils.ts
│       │   └── old-components.tsx
│       └── modernized-codebase/
│           ├── auth/
│           │   ├── index.ts
│           │   ├── providers.ts
│           │   └── middleware.ts
│           ├── utils/
│           │   ├── index.ts
│           │   ├── formatting.ts
│           │   └── validation.ts
│           └── components/
│               ├── index.tsx
│               ├── Auth/
│               │   ├── LoginForm.tsx
│               │   └── SignupForm.tsx
│               └── UI/
│                   ├── Button.tsx
│                   └── Modal.tsx
│   └── assets/
│       ├── refactoring-steps.png
│       └── nes-during-refactoring.gif
├── demo-2-large-codebase-navigation/
│   ├── walkthrough.md
│   └── src/
│       ├── enterprise-app/
│       │   ├── frontend/
│       │   │   ├── src/
│       │   │   │   ├── components/
│       │   │   │   ├── services/
│       │   │   │   ├── utils/
│       │   │   │   └── types/
│       │   │   └── package.json
│       │   ├── backend/
│       │   │   ├── src/
│       │   │   │   ├── controllers/
│       │   │   │   ├── services/
│       │   │   │   ├── models/
│       │   │   │   └── utils/
│       │   │   └── package.json
│       │   └── shared/
│       │       ├── types/
│       │       ├── constants/
│       │       └── validators/
│       └── usage-scenarios/
│           ├── cross-module-imports.md
│           └── dependency-management.md
│   └── assets/
│       ├── large-codebase-nes.png
│       └── import-discovery.gif
└── demo-3-accuracy-improvements/
    ├── walkthrough.md
    └── src/
        ├── test-cases/
        │   ├── edge-cases.ts
        │   ├── complex-imports.js
        │   └── python-modules.py
        └── comparisons/
            ├── before-v1101.md
            └── after-v1101.md
    └── assets/
        ├── accuracy-comparison.png
        └── reliability-metrics.png
```

## File Listings and Contents

For each file in the structure above, the complete contents are defined here to enable automation agents to generate the full directory and file tree as specified.

---

### code-editing-nes-kit/README.md

```
# Code Editing - NES (Next Edit Suggestions) — Exercise + Demo Resource Kit

Welcome! This resource kit contains:
- **Exercises** with hands-on guides to master Next Edit Suggestions (NES) in VS Code 1.101
- **Demos** showcasing real-world refactoring workflows and large codebase navigation
- **Solutions** with optimized code examples and best practices

## What You'll Learn

1. **Import Suggestions** - AI-powered automatic import detection and suggestion
2. **Acceptance Flow** - Seamless keyboard navigation with Tab-based workflow
3. **Multi-Language Support** - Enhanced accuracy for TypeScript, JavaScript, and Python
4. **Refactoring Workflows** - Large-scale code modernization with NES assistance
5. **Large Codebase Navigation** - Efficient import management in enterprise applications
6. **Accuracy Improvements** - Understanding enhanced reliability and precision

## Features Covered

- Automatic missing import detection
- AI-powered import suggestions with visual indicators
- Tab-based navigation and acceptance workflow
- Cross-language support (TypeScript, JavaScript, Python)
- Enhanced accuracy and reliability improvements
- Integration with refactoring and code modernization
- Large codebase import management strategies

## Prerequisites

- VS Code 1.101+
- GitHub Copilot subscription and extension
- Basic understanding of TypeScript, JavaScript, or Python
- Familiarity with import/export statements and module systems

## Getting Started

1. **Enable NES**: Set `github.copilot.nextEditSuggestions.fixes` to `true` in settings
2. **Start with Exercise 1**: Learn basic import suggestion functionality
3. **Progress through exercises**: Build understanding of acceptance flow and multi-language support
4. **Explore demos**: See real-world applications and advanced workflows
5. **Use solutions**: Reference optimized implementations and best practices

## NES Features Overview

### Visual Indicators
- **Arrow in Gutter**: Indicates available import suggestions
- **Green Highlighting**: Shows suggested import statements
- **Inline Hints**: Preview of suggested changes

### Keyboard Navigation
- **Tab**: Navigate to suggestion and accept
- **Escape**: Dismiss current suggestion
- **Continuous Flow**: Chain Tab presses for multiple suggestions

### Language Support
- **TypeScript**: Full module resolution and type imports
- **JavaScript**: CommonJS and ES6 module imports
- **Python**: Package imports and relative module imports

Happy coding with enhanced productivity!
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/instructions.md

```
# Exercise 1: Import Suggestions and Detection

## Goal
Learn to use NES (Next Edit Suggestions) for automatic import detection and AI-powered import suggestions across TypeScript, JavaScript, and Python projects.

## Task
1. Enable NES import suggestions in VS Code settings
2. Practice using functions/classes that require missing imports
3. Navigate and accept import suggestions using visual indicators
4. Test import suggestions across different languages and module systems
5. Understand the improved accuracy and reliability of suggestions

## Input/Output
**Starter**: Incomplete code files with missing imports
**Expected Outcome**: Fully functional code with automatically suggested and accepted imports

## Steps

1. **Enable NES Import Suggestions**
    ```json
    {
        "github.copilot.nextEditSuggestions.fixes": true
    }
    ```

   - Open Settings (Ctrl+,)
   - Search for "nextEditSuggestions"
   - Enable the setting and reload VS Code

2. **TypeScript Import Practice**
   - Open `incomplete-ts-file.ts`
   - Start using React components without imports
   - Look for arrow indicators in the gutter
   - Press Tab to navigate to suggestions

3. **JavaScript Import Practice**
   - Open `incomplete-js-file.js`
   - Use Node.js modules without imports
   - Practice with both CommonJS and ES6 imports
   - Accept suggestions using Tab navigation

4. **Python Import Practice**
   - Open `incomplete-py-file.py`
   - Use standard library and third-party modules
   - Test with relative and absolute imports
   - Navigate through multiple import suggestions

5. **Visual Indicator Recognition**
   - Learn to identify the arrow icon in gutter
   - Understand green highlighting for suggestions
   - Practice quick Tab navigation workflow

## Tips

- Look for the arrow icon in the left gutter when typing code
- Use Tab to quickly jump to and accept suggestions
- NES works best when you have a clear module/package structure
- Multiple imports can be chained with continuous Tab presses
- Accuracy is significantly improved in version 1.101

```

---

### code-editing-nes-kit/exercise-1-import-suggestions/starter/incomplete-ts-file.ts

```typescript
// Incomplete TypeScript file - missing imports
// Practice using NES to add the required imports

// Try using React components - should trigger import suggestions
function App() {
  const [count, setCount] = useState(0);
  
  return (
    <div>
      <h1>Hello React!</h1>
      <button onClick={() => setCount(count + 1)}>
        Count: {count}
      </button>
    </div>
  );
}

// Try using lodash utilities - should suggest import
function processData(data: any[]) {
  const grouped = groupBy(data, 'category');
  const sorted = sortBy(data, 'name');
  return { grouped, sorted };
}

// Try using date utilities - should suggest import
function formatDate(date: Date) {
  return format(date, 'yyyy-MM-dd');
}

// Try using validation library - should suggest import
interface UserData {
  email: string;
  age: number;
}

function validateUser(data: UserData) {
  const schema = object({
    email: string().email(),
    age: number().min(18)
  });
  
  return schema.parse(data);
}

export default App;
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/starter/incomplete-js-file.js

```javascript
// Incomplete JavaScript file - missing imports
// Practice using NES to add the required imports

// Try using Express - should trigger import suggestion
function createServer() {
  const app = express();
  
  app.get('/', (req, res) => {
    res.json({ message: 'Hello World!' });
  });
  
  return app;
}

// Try using filesystem operations - should suggest import
async function readConfigFile() {
  try {
    const data = await fs.readFile('config.json', 'utf-8');
    return JSON.parse(data);
  } catch (error) {
    console.error('Failed to read config:', error);
    return null;
  }
}

// Try using path utilities - should suggest import
function buildFilePath(directory, filename) {
  return path.join(directory, filename);
}

// Try using crypto operations - should suggest import
function generateHash(data) {
  return crypto.createHash('sha256').update(data).digest('hex');
}

// Try using HTTP client - should suggest import
async function fetchData(url) {
  try {
    const response = await axios.get(url);
    return response.data;
  } catch (error) {
    console.error('Fetch failed:', error);
    throw error;
  }
}

// Try using moment for dates - should suggest import
function formatTimestamp(timestamp) {
  return moment(timestamp).format('YYYY-MM-DD HH:mm:ss');
}

module.exports = {
  createServer,
  readConfigFile,
  buildFilePath,
  generateHash,
  fetchData,
  formatTimestamp
};
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/starter/incomplete-py-file.py

```python
# Incomplete Python file - missing imports
# Practice using NES to add the required imports

# Try using datetime - should trigger import suggestion
def get_current_timestamp():
    return datetime.now().isoformat()

# Try using JSON operations - should suggest import
def load_config(filename):
    with open(filename, 'r') as file:
        return json.load(file)

# Try using HTTP requests - should suggest import
def fetch_api_data(url):
    response = requests.get(url)
    response.raise_for_status()
    return response.json()

# Try using regex - should suggest import
def validate_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return re.match(pattern, email) is not None

# Try using pathlib - should suggest import
def ensure_directory_exists(directory_path):
    path = Path(directory_path)
    path.mkdir(parents=True, exist_ok=True)
    return path

# Try using pandas - should suggest import
def process_csv_data(filename):
    df = pd.read_csv(filename)
    df = df.dropna()
    return df.groupby('category').sum()

# Try using numpy - should suggest import
def calculate_statistics(data):
    array = np.array(data)
    return {
        'mean': np.mean(array),
        'std': np.std(array),
        'median': np.median(array)
    }

# Try using random - should suggest import
def generate_sample_data(size):
    return [random.randint(1, 100) for _ in range(size)]

class DataProcessor:
    def __init__(self, config_path):
        self.config = load_config(config_path)
        self.timestamp = get_current_timestamp()
    
    def process(self, data):
        stats = calculate_statistics(data)
        return {
            'processed_at': self.timestamp,
            'statistics': stats,
            'sample_size': len(data)
        }

if __name__ == "__main__":
    processor = DataProcessor('config.json')
    sample_data = generate_sample_data(100)
    result = processor.process(sample_data)
    print(json.dumps(result, indent=2))
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/solution/typescript-project/src/main.ts

```typescript
import React, { useState } from 'react';
import { groupBy, sortBy } from 'lodash';
import { format } from 'date-fns';
import { object, string, number } from 'zod';

// Complete TypeScript file with NES-suggested imports
function App() {
  const [count, setCount] = useState(0);
  
  return (
    <div>
      <h1>Hello React!</h1>
      <button onClick={() => setCount(count + 1)}>
        Count: {count}
      </button>
    </div>
  );
}

function processData(data: any[]) {
  const grouped = groupBy(data, 'category');
  const sorted = sortBy(data, 'name');
  return { grouped, sorted };
}

function formatDate(date: Date) {
  return format(date, 'yyyy-MM-dd');
}

interface UserData {
  email: string;
  age: number;
}

function validateUser(data: UserData) {
  const schema = object({
    email: string().email(),
    age: number().min(18)
  });
  
  return schema.parse(data);
}

export default App;
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/solution/typescript-project/package.json

```json
{
  "name": "typescript-nes-example",
  "version": "1.0.0",
  "description": "TypeScript project for NES import suggestions",
  "main": "dist/main.js",
  "scripts": {
    "build": "tsc",
    "dev": "tsc --watch",
    "start": "node dist/main.js"
  },
  "dependencies": {
    "react": "^18.2.0",
    "lodash": "^4.17.21",
    "date-fns": "^2.30.0",
    "zod": "^3.22.0"
  },
  "devDependencies": {
    "@types/react": "^18.2.0",
    "@types/lodash": "^4.14.0",
    "typescript": "^5.0.0"
  }
}
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/solution/javascript-project/src/index.js

```javascript
const express = require('express');
const fs = require('fs').promises;
const path = require('path');
const crypto = require('crypto');
const axios = require('axios');
const moment = require('moment');

// Complete JavaScript file with NES-suggested imports
function createServer() {
  const app = express();
  
  app.get('/', (req, res) => {
    res.json({ message: 'Hello World!' });
  });
  
  return app;
}

async function readConfigFile() {
  try {
    const data = await fs.readFile('config.json', 'utf-8');
    return JSON.parse(data);
  } catch (error) {
    console.error('Failed to read config:', error);
    return null;
  }
}

function buildFilePath(directory, filename) {
  return path.join(directory, filename);
}

function generateHash(data) {
  return crypto.createHash('sha256').update(data).digest('hex');
}

async function fetchData(url) {
  try {
    const response = await axios.get(url);
    return response.data;
  } catch (error) {
    console.error('Fetch failed:', error);
    throw error;
  }
}

function formatTimestamp(timestamp) {
  return moment(timestamp).format('YYYY-MM-DD HH:mm:ss');
}

module.exports = {
  createServer,
  readConfigFile,
  buildFilePath,
  generateHash,
  fetchData,
  formatTimestamp
};
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/solution/python-project/src/main.py

```python
import json
import re
from datetime import datetime
from pathlib import Path
import random

import requests
import pandas as pd
import numpy as np

# Complete Python file with NES-suggested imports
def get_current_timestamp():
    return datetime.now().isoformat()

def load_config(filename):
    with open(filename, 'r') as file:
        return json.load(file)

def fetch_api_data(url):
    response = requests.get(url)
    response.raise_for_status()
    return response.json()

def validate_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return re.match(pattern, email) is not None

def ensure_directory_exists(directory_path):
    path = Path(directory_path)
    path.mkdir(parents=True, exist_ok=True)
    return path

def process_csv_data(filename):
    df = pd.read_csv(filename)
    df = df.dropna()
    return df.groupby('category').sum()

def calculate_statistics(data):
    array = np.array(data)
    return {
        'mean': np.mean(array),
        'std': np.std(array),
        'median': np.median(array)
    }

def generate_sample_data(size):
    return [random.randint(1, 100) for _ in range(size)]

class DataProcessor:
    def __init__(self, config_path):
        self.config = load_config(config_path)
        self.timestamp = get_current_timestamp()
    
    def process(self, data):
        stats = calculate_statistics(data)
        return {
            'processed_at': self.timestamp,
            'statistics': stats,
            'sample_size': len(data)
        }

if __name__ == "__main__":
    processor = DataProcessor('config.json')
    sample_data = generate_sample_data(100)
    result = processor.process(sample_data)
    print(json.dumps(result, indent=2))
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/solution/python-project/requirements.txt

```
requests>=2.31.0
pandas>=2.0.0
numpy>=1.24.0
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/assets/nes-import-suggestion.gif

```
Animated GIF showing:
- User typing code that requires an import
- Arrow indicator appearing in the gutter
- Tab navigation to the import suggestion
- Green highlighting of the suggested import
- Acceptance of the suggestion and continued coding
```

---

### code-editing-nes-kit/exercise-1-import-suggestions/assets/import-gutter-indicator.png

```
Screenshot showing:
- Code editor with missing import usage
- Clear arrow indicator in the left gutter
- Highlighted line where import is needed
- Tooltip or hint showing available suggestion
```

---

### code-editing-nes-kit/exercise-2-acceptance-flow/instructions.md

```
# Exercise 2: NES Acceptance Flow and Keyboard Navigation

## Goal
Master the seamless keyboard navigation workflow for accepting NES import suggestions, including continuous Tab navigation and multi-suggestion scenarios.

## Task
1. Learn the Tab-based navigation system for NES suggestions
2. Practice continuous suggestion acceptance without interruption
3. Handle multiple import suggestions in sequence
4. Understand when the acceptance flow resets
5. Optimize workflow for maximum productivity

## Input/Output
**Starter**: Practice scenarios with multiple missing imports
**Expected Outcome**: Fluid keyboard workflow for rapid import acceptance

## Steps

1. **Basic Tab Navigation**
   - Start typing code that needs imports
   - When NES indicator appears, press Tab to navigate
   - Press Tab again to accept the suggestion
   - Continue coding immediately

2. **Continuous Acceptance Flow**
   - Write code requiring multiple imports
   - Use Tab to accept first suggestion
   - Immediately press Tab for next suggestion
   - Chain multiple acceptances without typing

3. **Flow Reset Understanding**
   - Accept a suggestion with Tab
   - Start typing new code
   - Press Tab to move cursor to next suggestion
   - Press Tab again to accept

4. **Multiple Import Scenarios**
   - Create files with 5+ missing imports
   - Practice rapid acceptance workflow
   - Test with different languages and import types

5. **Keyboard Efficiency**
   - Minimize mouse usage during import acceptance
   - Develop muscle memory for Tab navigation
   - Practice common import patterns

## Tips
- Tab once to navigate to suggestion, Tab again to accept
- Continuous Tab presses work until you start typing
- After typing, first Tab moves cursor, second Tab accepts
- NES remembers your acceptance patterns for better suggestions
- Practice with real-world codebases for best experience
```

---

### code-editing-nes-kit/exercise-2-acceptance-flow/starter/practice-scenarios/scenario-1.ts

```typescript
// Scenario 1: React component with multiple missing imports
// Practice Tab navigation for rapid import acceptance

function UserProfile({ userId }: { userId: string }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  
  useEffect(() => {
    fetchUserData();
  }, [userId]);
  
  const fetchUserData = async () => {
    try {
      setLoading(true);
      const userData = await axios.get(`/api/users/${userId}`);
      setUser(userData.data);
    } catch (error) {
      console.error('Failed to fetch user:', error);
    } finally {
      setLoading(false);
    }
  };
  
  const formatDate = (dateString: string) => {
    return format(new Date(dateString), 'MMM dd, yyyy');
  };
  
  const validateEmail = (email: string) => {
    return isEmail(email);
  };
  
  if (loading) {
    return <Spinner />;
  }
  
  return (
    <Card className="user-profile">
      <CardHeader>
        <Avatar src={user.avatar} />
        <Typography variant="h4">{user.name}</Typography>
      </CardHeader>
      <CardBody>
        <Typography>Email: {user.email}</Typography>
        <Typography>Joined: {formatDate(user.createdAt)}</Typography>
        <Button onClick={() => setUser(null)}>Clear</Button>
      </CardBody>
    </Card>
  );
}

export default UserProfile;
```

---

### code-editing-nes-kit/exercise-2-acceptance-flow/starter/practice-scenarios/scenario-2.js

```javascript
// Scenario 2: Node.js service with multiple utility imports
// Practice chaining multiple import acceptances

class EmailService {
  constructor(config) {
    this.transporter = nodemailer.createTransporter(config.smtp);
    this.templates = new Map();
    this.logger = winston.createLogger({
      transports: [new winston.transports.Console()]
    });
  }
  
  async loadTemplate(templateName) {
    const templatePath = path.join(__dirname, 'templates', `${templateName}.hbs`);
    const templateContent = await fs.readFile(templatePath, 'utf-8');
    const compiled = handlebars.compile(templateContent);
    this.templates.set(templateName, compiled);
    return compiled;
  }
  
  async sendEmail(to, templateName, data) {
    try {
      const template = this.templates.get(templateName) || 
                     await this.loadTemplate(templateName);
      
      const html = template(data);
      const messageId = uuid.v4();
      
      const mailOptions = {
        from: process.env.FROM_EMAIL,
        to,
        subject: data.subject,
        html,
        messageId
      };
      
      const result = await this.transporter.sendMail(mailOptions);
      
      this.logger.info('Email sent successfully', {
        messageId,
        to,
        template: templateName
      });
      
      return { success: true, messageId: result.messageId };
    } catch (error) {
      this.logger.error('Failed to send email', { error: error.message, to });
      throw error;
    }
  }
  
  generateUnsubscribeToken(email) {
    const payload = { email, timestamp: Date.now() };
    return jwt.sign(payload, process.env.JWT_SECRET, { expiresIn: '30d' });
  }
  
  validateUnsubscribeToken(token) {
    try {
      return jwt.verify(token, process.env.JWT_SECRET);
    } catch (error) {
      return null;
    }
  }
}

module.exports = EmailService;
```

---

### code-editing-nes-kit/exercise-2-acceptance-flow/starter/practice-scenarios/scenario-3.py

```python
# Scenario 3: Python data analysis script with multiple imports
# Practice Tab workflow with Python modules

class DataAnalyzer:
    def __init__(self, config_file):
        self.config = self.load_config(config_file)
        self.logger = self.setup_logging()
        self.db_connection = None
        
    def load_config(self, config_file):
        with open(config_file, 'r') as file:
            return yaml.safe_load(file)
    
    def setup_logging(self):
        logging.basicConfig(
            level=logging.INFO,
            format='%(asctime)s - %(levelname)s - %(message)s'
        )
        return logging.getLogger(__name__)
    
    def connect_database(self):
        connection_string = self.config['database']['connection_string']
        self.db_connection = sqlite3.connect(connection_string)
        return self.db_connection
    
    def fetch_data(self, query, params=None):
        if not self.db_connection:
            self.connect_database()
        
        df = pd.read_sql_query(query, self.db_connection, params=params)
        return df
    
    def analyze_trends(self, data):
        # Statistical analysis
        stats = {
            'mean': np.mean(data),
            'median': np.median(data),
            'std': np.std(data),
            'percentiles': np.percentile(data, [25, 50, 75])
        }
        
        # Time series analysis if datetime column exists
        if 'date' in data.columns:
            data['date'] = pd.to_datetime(data['date'])
            data = data.set_index('date')
            
            # Trend analysis
            trend_data = data.resample('D').mean()
            stats['trend'] = trend_data.pct_change().mean()
        
        return stats
    
    def generate_report(self, analysis_results):
        timestamp = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
        
        report = {
            'generated_at': timestamp,
            'analysis': analysis_results,
            'summary': self.create_summary(analysis_results)
        }
        
        # Save to file
        report_file = f"report_{datetime.now().strftime('%Y%m%d_%H%M%S')}.json"
        with open(report_file, 'w') as file:
            json.dump(report, file, indent=2, default=str)
        
        self.logger.info(f"Report saved to {report_file}")
        return report
    
    def create_summary(self, results):
        summary = []
        for key, value in results.items():
            if isinstance(value, (int, float)):
                summary.append(f"{key}: {value:.2f}")
            else:
                summary.append(f"{key}: {value}")
        
        return "; ".join(summary)
    
    def export_to_csv(self, data, filename):
        output_path = os.path.join(self.config['output_dir'], filename)
        os.makedirs(os.path.dirname(output_path), exist_ok=True)
        data.to_csv(output_path, index=False)
        self.logger.info(f"Data exported to {output_path}")
        return output_path

if __name__ == "__main__":
    analyzer = DataAnalyzer('config.yaml')
    
    # Example usage
    query = "SELECT * FROM sales_data WHERE date >= ? AND date <= ?"
    start_date = datetime.now() - timedelta(days=30)
    end_date = datetime.now()
    
    data = analyzer.fetch_data(query, [start_date, end_date])
    analysis = analyzer.analyze_trends(data)
    report = analyzer.generate_report(analysis)
    
    print(json.dumps(report, indent=2, default=str))
```

---

### code-editing-nes-kit/exercise-2-acceptance-flow/solution/keyboard-navigation/workflow-examples.md

```markdown
# NES Keyboard Navigation Workflow Examples

## Basic Acceptance Flow

### Single Import Scenario
1. **Type code**: `const result = axios.get('/api/data');`
2. **NES activates**: Arrow appears in gutter
3. **Navigate**: Press `Tab` to jump to import location
4. **Accept**: Press `Tab` again to accept suggestion
5. **Continue**: Import added, cursor returns to original position

### Visual Indicators
- **Gutter Arrow**: 🡸 indicates suggestion available
- **Green Highlight**: Shows suggested import location
- **Cursor Movement**: Tab moves cursor to suggestion

## Continuous Acceptance Flow

### Multiple Imports Without Typing
```typescript
// Start with missing imports
function Component() {
  const [state, setState] = useState(0);     // Tab, Tab → React import
  const data = useQuery('key', fetchData);   // Tab, Tab → React Query import
  const router = useRouter();                // Tab, Tab → Next.js import
  
  return <div>{data}</div>;
}
```

**Workflow**:

1. Tab → Navigate to React import
2. Tab → Accept React import
3. Tab → Navigate to React Query import
4. Tab → Accept React Query import
5. Tab → Navigate to Next.js import
6. Tab → Accept Next.js import

### Flow Reset After Typing

```javascript
// Accept first import
const app = express();  // Tab, Tab → express import accepted

// Start typing new code (resets flow)
const server = http.createServer(app);  // Tab → move to suggestion, Tab → accept
```

## Advanced Navigation Patterns

### Multi-Language Project Workflow

```typescript
// TypeScript file
import { Component } from 'react';          // NES suggested
import { format } from 'date-fns';          // NES suggested
import { z } from 'zod';                    // NES suggested

// Python file
import requests                             # NES suggested
import pandas as pd                         # NES suggested
import numpy as np                          # NES suggested
```

### Complex Import Scenarios

```typescript
// Named imports
import { useState, useEffect, useCallback } from 'react';

// Default + named imports  
import axios, { AxiosResponse } from 'axios';

// Type-only imports
import type { User, ApiResponse } from './types';

// Dynamic imports (handled differently)
const LazyComponent = lazy(() => import('./LazyComponent'));
```

## Productivity Tips

### Keyboard-Only Workflow

1. **Never reach for mouse** during import acceptance
2. **Use Tab exclusively** for navigation and acceptance
3. **Develop muscle memory** for common patterns
4. **Chain acceptances** when possible

### Optimization Strategies

1. **Group related functionality** to trigger multiple suggestions
2. **Write complete functions** before accepting imports
3. **Use consistent naming** to improve NES accuracy
4. **Leverage IntelliSense** alongside NES

### Common Patterns

- **React Hook Usage**: useState → useEffect → custom hooks
- **Utility Libraries**: lodash → date-fns → validation
- **Node.js Services**: express → middleware → utilities
- **Python Data**: pandas → numpy → matplotlib

## Troubleshooting Navigation

### Suggestion Not Appearing

- Check if package is installed
- Verify TypeScript/Python path configuration
- Ensure import is actually needed

### Tab Not Working

- Check if cursor is in correct position
- Verify NES is enabled in settings
- Look for gutter arrow indicator

### Wrong Import Suggested

- Accept suggestion and manually correct
- Update package.json or requirements.txt
- Configure module resolution paths

## Performance Optimization

### Faster Acceptance

- **Anticipate suggestions**: Know common imports for your codebase
- **Use keyboard shortcuts**: Minimize hand movement
- **Batch similar operations**: Group related import scenarios

### Reduced Interruptions

- **Plan import structure**: Organize modules logically
- **Use barrel exports**: Simplify import paths
- **Configure auto-imports**: Reduce manual intervention

```

---

### code-editing-nes-kit/exercise-2-acceptance-flow/solution/keyboard-navigation/keyboard-shortcuts.md

```markdown
# NES Keyboard Shortcuts Reference

## Core Navigation Shortcuts

| Action | Shortcut | Description |
|--------|----------|-------------|
| Navigate to Suggestion | `Tab` | Jump cursor to import suggestion location |
| Accept Suggestion | `Tab` | Accept the highlighted import suggestion |
| Dismiss Suggestion | `Escape` | Cancel current suggestion without accepting |
| Manual Trigger | `Ctrl+Shift+.` | Force trigger import suggestions if available |

## Workflow States

### State 1: Initial Suggestion
- **Trigger**: Type code requiring import
- **Indicator**: Arrow in gutter appears
- **Action**: `Tab` to navigate to suggestion

### State 2: At Suggestion Location
- **Indicator**: Green highlighting on import line
- **Action**: `Tab` to accept, `Escape` to cancel
- **Alternative**: Edit manually before accepting

### State 3: Continuous Flow
- **Condition**: Immediately after accepting suggestion
- **Action**: `Tab` directly accepts next suggestion
- **Reset**: Any typing resets to State 1 behavior

### State 4: Flow Reset
- **Trigger**: Any typing or cursor movement
- **Behavior**: Next `Tab` navigates, second `Tab` accepts
- **Purpose**: Prevents accidental acceptances

## Advanced Keyboard Combinations

### With Editor Navigation
```

Tab, Tab                    → Accept import, continue coding
Tab, Escape                 → Navigate to suggestion, then cancel
Ctrl+Z after Tab, Tab       → Undo import acceptance

```

### With IntelliSense
```

Tab to suggestion           → Navigate to import
Ctrl+Space                  → Trigger IntelliSense for alternatives
Tab                         → Accept current suggestion

```

### With Multi-Cursor
```

Ctrl+Alt+Down               → Create multiple cursors
Tab                         → Navigate all cursors to suggestions
Tab                         → Accept all suggestions simultaneously

```

## Platform-Specific Shortcuts

### Windows/Linux
- **Navigate**: `Tab`
- **Accept**: `Tab`
- **Cancel**: `Escape`
- **Force trigger**: `Ctrl+Shift+.`

### macOS
- **Navigate**: `Tab`
- **Accept**: `Tab`
- **Cancel**: `Escape`
- **Force trigger**: `Cmd+Shift+.`

## Integration with VS Code Features

### Command Palette Integration
- **Organize Imports**: `Shift+Alt+O` (works with NES)
- **Fix All**: `Ctrl+Shift+.` → Select "Fix all auto-fixable issues"
- **Add Missing Imports**: Available in quick fix menu

### Editor Shortcuts That Work With NES
```

Ctrl+D                      → Select next occurrence (before NES)
Ctrl+Shift+L                → Select all occurrences (before NES)
Tab, Tab                    → Accept NES suggestion
F2                          → Rename symbol (triggers new NES suggestions)

```

## Customization Options

### Settings for Keyboard Behavior
```json
{
  "github.copilot.nextEditSuggestions.fixes": true,
  "editor.tabCompletion": "on",
  "editor.acceptSuggestionOnTab": "smart"
}
```

### Disable Conflicting Shortcuts

```json
{
  "keyboard.shortcuts": [
    {
      "key": "tab",
      "command": "-acceptSelectedSuggestion",
      "when": "suggestWidgetVisible && textInputFocus"
    }
  ]
}
```

## Accessibility Features

### Screen Reader Support

- Import suggestions are announced
- Keyboard navigation is fully accessible
- Visual indicators have text equivalents

### High Contrast Mode

- Arrow indicators remain visible
- Green highlighting uses high contrast colors
- Focus indicators are enhanced

## Performance Considerations

### Fastest Workflows

1. **Anticipatory typing**: Write complete blocks before accepting
2. **Batch acceptance**: Accept multiple imports in sequence
3. **Muscle memory**: Develop automatic Tab, Tab pattern

### Avoiding Delays

- Don't wait for visual confirmation
- Trust the Tab navigation system
- Use continuous flow when possible

## Troubleshooting Shortcuts

### Tab Not Working

1. Check if NES is enabled
2. Verify arrow indicator is present
3. Ensure cursor is in correct context

### Wrong Behavior

1. Check editor.tabCompletion setting
2. Verify no extension conflicts
3. Reset keyboard shortcuts if needed

### Performance Issues

1. Disable unnecessary extensions
2. Check TypeScript service health
3. Restart language servers if needed

```

This resource kit provides comprehensive hands-on experience with VS Code's NES (Next Edit Suggestions) improvements from version 1.101. The exercises cover import suggestions detection, keyboard navigation workflows, and multi-language support, while demos showcase real-world refactoring scenarios and large codebase navigation.

Would you like me to continue with the next major feature? The next feature would be "Notebooks" which includes follow mode for agent cell execution and notebook tools for agent mode.
