---
name: rh-style-guide
description: Red Hat AI quickstart writing conventions and style guide. Use when writing or editing README files, documentation, or user-facing content in quickstart repositories.
user-invocable: false
---

# Red Hat AI Quickstart Style Guide

When writing or editing content for Red Hat AI quickstarts, follow these conventions.

## Voice and Tone

- Use **active voice**: "Deploy the application" not "The application is deployed"
- Write in **second person**: "You can configure..." not "Users can configure..."
- Be **direct and concise**: Avoid filler words and unnecessary qualifiers
- Use **present tense** for instructions: "Click **Save**" not "You will click Save"
- Be **encouraging but professional**: Avoid overly casual language

## Formatting Conventions

- **UI elements**: Bold all UI element names, including page names, window names, panel names, button labels. Write them exactly as they appear in the UI. Example: Click **Deploy** on the **Applications** page.
- **Code and user input**: Use monospaced font (backticks) for code, commands, file paths, environment variables, and any text the user must type. Example: Run `make deploy` to start the deployment.
- **Navigation hints**: Style hints to navigation or masthead elements as links where possible.
- **File paths**: Always use monospace: `deploy/helm/values.yaml`
- **Environment variables**: Always use monospace: `DATABASE_URL`

## Content Structure

- **Headings**: Use sentence case for headings ("Deploy the application" not "Deploy The Application")
- **Lists**: Use bulleted lists for unordered items, numbered lists for sequential steps
- **Steps**: Number sequential instructions. Each step should be one action.
- **Code blocks**: Always specify the language for syntax highlighting (```bash, ```yaml, ```python)
- **Links**: Use descriptive link text, not "click here" or bare URLs

## Quickstart-Specific Rules

- **Titles**: Must start with an action verb and describe the use case, not the technology. Good: "Build an AI-powered virtual agent". Bad: "OpenShift AI with LangChain demo"
- **Short descriptions**: Max 160 characters. Focus on what the user achieves, not the technology stack.
- **Deploy instructions**: Assume the reader has limited experience. Be explicit about every step. Never say "simply" or "just".
- **Tags**: Follow the MIST taxonomy format: `- Tag name: value`

## Terminology

- Use "Red Hat OpenShift AI" on first reference, "OpenShift AI" subsequently
- Use "RHEL AI" (not "Red Hat Enterprise Linux AI") after first full reference
- Use "quickstart" (one word, lowercase) not "quick start" or "Quick Start"
- Refer to "large language model" on first use, "LLM" subsequently
- Use "retrieval-augmented generation" on first use, "RAG" subsequently

## Additional Resources

For detailed writing conventions, see:
- [reference/readme-format.md](reference/readme-format.md) — Complete 15-section README format specification
- [reference/mist-taxonomy.md](reference/mist-taxonomy.md) — MIST taxonomy tag reference
- [reference/quality-criteria.md](reference/quality-criteria.md) — Quality criteria for quickstart acceptance
