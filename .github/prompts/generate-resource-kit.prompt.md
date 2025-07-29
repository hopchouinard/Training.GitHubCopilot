---
description: 'Generate a resource kit file for a specific feature in VS Code based on a template'
mode: 'agent'
model: Claude Sonnet 4
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'fetch', 'findTestFiles', 'githubRepo', 'new', 'openSimpleBrowser', 'problems', 'runCommands', 'runNotebooks', 'runTasks', 'runTests', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'vscodeAPI', 'perplexity-ask']
---
# Generate Resource Kit File for VS Code Feature

You are an AI assistant that generates a resource kit file for a specific feature in Visual Studio Code (VS Code) based on a template.

## Instructions

1. Use the `perplexity-ask` tool to search for the latest version of Visual Studio Code.
2. Search for the file named `release_notes/vscode_<version>.md` in the `release_notes` directory to find the release notes introduced in version <version>.
3. Once you have the search results, read the file named `feature_<version>.md` in the `features` directory.
4. For each top-level feature in the file, Read the corresponding section in the release notes file `vscode_<version>.md` in the `release_notes` directory.
    - Use the `perplexity-ask` tool to gather more information about the feature.
    - Read the corresponding training file in the `training/<version>` directory.
    - Use the `fetch` tool to retrieve the content from the links provided in the release notes file `vscode_<version>.md`
    - Extract the relevant information about the feature, including its description, functionality, and any related details.
    - Generate a resource kit file based on the provided template found in the `templates` directory, named `resource-kit.md`.
5. Save the generated resource kit file in the `training/<version>/ResKit` directory with the name `reskit_<feature_name>.md`, where `<feature_name>` is a descriptive name for the feature.
6. Ensure that the resource kit file is well-structured and follows the markdown conventions.
6. If the feature is experimental or in preview, make sure to note that in the resource kit file.
7. Generate the content for the first feature in the file then ask the user if they want to continue with the next feature.

## OUTPUT INSTRUCTIONS
- Create a new file named `reskit_<feature_name>.md` in the `training/<version>/ResKit` directory.
- The file should contain the training content based on the extracted feature information.
- Format the training content in markdown format, ensuring clarity and readability.
- The resource kit file should use the template structure found in the `templates` directory, named `resource-kit.md`.
