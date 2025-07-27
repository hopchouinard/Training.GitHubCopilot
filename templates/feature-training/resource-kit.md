---
feature: "[Feature Name]"
release: "[Release Version]"     # e.g., 1.102
resource_type: "[Exercise | Demo | Both]"
audience: "[Target users/personas]"
prerequisites:
  - "[First prerequisite feature, if any]"
  - "[Second prerequisite feature, if any]"
summary: |
  "[Brief summary of what the resource kit covers—feature it demonstrates, learning goals, or target outcome.]"
---

# 📦 Resource Kit: `[Feature Name]` — `[Exercise|Demo]`

## Directory Structure

```
[RootDirectory]/
├── README.md
├── [Exercise1]/
│   ├── instructions.md
│   ├── solution/
│   │   └── [file1.ext]
│   ├── starter/
│   │   └── [file2.ext]
│   └── assets/
│       └── [any-supporting-files]
├── [Demo1]/
│   ├── walkthrough.md
│   └── src/
│       └── [demo-file.ext]
│   └── assets/
│       └── [any-supporting-files]
└── ...
```

## File Listings and Contents

For each `[file]` in the structure above, define the complete contents here. This section enables automation agents to generate the full directory and file tree as specified.

---

### [RootDirectory]/README.md

```
# [Feature Name] — [Exercise/Demo] Resource Kit

Welcome! This resource kit contains:
- Exercises and solutions to guide mastery of `[Feature Name]`.
- Demos with step-by-step walkthroughs and working example code.
```

---

### [RootDirectory]/[Exercise1]/instructions.md

```
# Exercise 1: [Title]

## Goal
[Clearly state the learning goal or feature being practiced.]

## Task
[Describe the steps the learner must perform.]

## Input/Output
[Give any starter data, sample input, and expected outcome.]

## Tips
- [Add hints or common pitfalls]
```

---

### [RootDirectory]/[Exercise1]/starter/[file2.ext]

```
[Provide starter code or scaffold. Use appropriate syntax highlighting: e.g., ```python, ```
```

---

### [RootDirectory]/[Exercise1]/solution/[file1.ext]

```
[Provide the complete solution for the exercise. Use appropriate file formatting.]
```

---

### [RootDirectory]/[Demo1]/walkthrough.md

```
# Demo: [Short Title]

## What You'll See
[Overview of what is demonstrated.]

## Steps
1. [List major steps, with code or terminal snippets as needed.]
2. ...

## Expected Output
[Describe or show (via code or image reference) expected results.]
```

---

### [RootDirectory]/[Demo1]/src/[demo-file.ext]

```
[Complete source code or markup for the demo.]
```

---

### [RootDirectory]/[Demo1]/assets/[any-supporting-files]

```
[Binary or text resource—describe its purpose and format if not plaintext.]
