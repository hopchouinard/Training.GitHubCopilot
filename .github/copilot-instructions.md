# Copilot Instructions for VS Code Training Materials Generator

## Project Architecture

This is an **automated, prompt-driven content generation system** for VS Code training materials. The core workflow uses a series of interconnected prompt files in `.github/prompts/` to orchestrate AI-powered content creation.

### Essential Workflow Sequence

1. **`retreive-RN-VSCode.prompt.md`** → Downloads VS Code release notes from microsoft/vscode-docs
2. **`extract-feature-from-RN.prompt.md`** → Parses release notes into structured feature catalogs
3. **`generate-training.prompt.md`** → Creates comprehensive training docs using templates
4. **`generate-resource-kit.prompt.md`** → Generates hands-on exercises and demos

### Key Directory Patterns

- **`.github/prompts/`**: Core workflow engine - all prompt files define AI agent behaviors
- **`templates/feature-training/`**: Content templates that ensure consistent structure
- **`release_notes/`**: Source materials (e.g., `vscode_1.102.md`)
- **`features/`**: Structured feature catalogs (e.g., `features_1.102.md`)
- **`trainings/{version}/`**: Generated training docs and ResKit folders

## Critical Development Workflows

### Content Generation Process

```bash
# Follow the prompt sequence:
# 1. Run retreive-RN-VSCode.prompt.md to get latest release notes
# 2. Run extract-feature-from-RN.prompt.md to create feature catalog
# 3. Run generate-training.prompt.md for each feature
# 4. Run generate-resource-kit.prompt.md for hands-on materials
```

### Template System Requirements

- **YAML front matter** is mandatory for all generated content
- Use exact template structures from `templates/feature-training/`
- Training files: `feature_{name}.md` in `trainings/{version}/`
- Resource kits: `reskit_{name}.md` in `trainings/{version}/ResKit/`

### AI Tool Integration Patterns

- **Perplexity API**: Use `perplexity-ask` for external research and version discovery
- **GitHub API**: Direct access to microsoft/vscode-docs for official documentation
- **File Operations**: Structured content creation following template patterns

## Project-Specific Conventions

### Naming Conventions

- Release notes: `vscode_{version}.md` (e.g., `vscode_1.102.md`)
- Feature catalogs: `features_{version}.md`
- Training files: `feature_{snake_case_name}.md`
- Resource kits: `reskit_{snake_case_name}.md`

### Content Structure Requirements

- All content must include YAML metadata following template schemas
- Training docs follow 8-section structure: Overview, Why It Matters, Feature Details, etc.
- Resource kits include directory structures, file listings, and complete content specifications

### Template Dependencies

- **`feature-training.md`**: Defines structure for theoretical training content
- **`resource-kit.md`**: Defines hands-on exercise and demo specifications
- Both templates include required YAML schemas and content section patterns

## Integration Points

### External Dependencies

- **Perplexity API**: Version discovery and feature research
- **GitHub API**: Official VS Code documentation access
- **microsoft/vscode-docs**: Canonical source for release notes

### Cross-Component Communication

- Prompt files reference specific file paths and naming conventions
- Templates define the data contract between generation stages
- Each workflow stage produces input for the subsequent stage

## Critical Developer Knowledge

### Prompt File Structure

All prompt files use consistent YAML front matter with `description`, `mode`, `model`, and `tools` arrays. The `tools` array defines available AI capabilities for each workflow stage.

### Version-Specific Patterns

Content is organized by VS Code version numbers (e.g., `1.102`). When adding new versions, maintain the established directory structure and naming conventions.

### Quality Assurance

Generated content follows markdown conventions with proper heading hierarchy, code block formatting, and consistent use of emojis for section identification (🚀, 📦, etc.).
