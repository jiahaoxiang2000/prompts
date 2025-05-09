# Prompts

We know that great prompts will yield even better results from the LLM. This project is a collection of prompts that we used on the GitHub Copilot for our diary jobs. Additionally, we want to easily sync the prompt files across multiple projects, so we use a git submodule to keep the prompts in sync across different projects.

## Limiting Usage Modes

> Starting with _April 2025 (version 1.100)_, prompt files can use the following features.

Prompt files may include Front Matter metadata headers to control how they are executed:

- **mode**: Specifies the chat mode to use when invoking the prompt (`ask`, `edit`, or `agent`).
- **tools**: If `mode` is set to `agent`, this lists the tools available to the prompt.

Here is an example prompt file:

```markdown
---
mode: "agent"
tools:
  [
    "getCurrentMilestone",
    "getReleaseFeatures",
    "file_search",
    "semantic_search",
    "read_file",
    "insert_edit_into_file",
    "create_file",
    "replace_string_in_file",
    "fetch_webpage",
    "vscode_search_extensions_internal",
  ]
---

Generate release notes for the features I worked on in the current release and update them in the release notes file. Use the [release notes writing instructions file](.github/instructions/release-notes-writing.instructions.md) as a guide.
```
