---
description: Scaffold a new Red Hat AI quickstart repository from the official template
disable-model-invocation: true
argument-hint: [quickstart-name]
allowed-tools: Bash, Write, Edit, Read, Glob, Grep
---

# Quickstart Init

Scaffold a new Red Hat AI quickstart repository. The user may provide a quickstart name as `$ARGUMENTS`.

## Step 1: Gather information

Ask the user for the following details (skip any already provided via arguments):

1. **Quickstart name** — kebab-case identifier (e.g. `fraud-detection-agent`). This becomes the repo name.
2. **Industry** — the target industry (e.g. Healthcare, Retail, Financial Services, Manufacturing, Telecommunications, Government, Energy)
3. **Use case description** — a 1-2 sentence description of what this quickstart demonstrates
4. **AI capabilities** — which AI patterns are used (select all that apply):
   - RAG (Retrieval-Augmented Generation)
   - Agentic workflows
   - Guardrails / safety
   - Fine-tuned models
   - Computer vision
   - NLP / text processing
5. **Target Red Hat products** — which products this runs on:
   - Red Hat OpenShift AI
   - RHEL AI
   - Red Hat OpenShift (base platform)

## Step 2: Clone and rename the template

Run the following commands to clone the template and rename all placeholders:

```bash
git clone https://github.com/rh-ai-quickstart/ai-quickstart-template.git <quickstart-name>
cd <quickstart-name>
rm -rf .git
git init
```

Then rename all occurrences of `ai-quickstart-template` to the quickstart name throughout the project:

```bash
find . -type f -not -path './.git/*' -exec sed -i '' "s/ai-quickstart-template/<quickstart-name>/g" {} +
```

Also rename the Helm chart directory if it exists:

```bash
mv deploy/helm/ai-quickstart-template deploy/helm/<quickstart-name> 2>/dev/null || true
```

## Step 3: Populate the README scaffold

Replace the template README.md with a scaffold that includes all 15 required sections pre-populated with the information gathered in Step 1. Follow this structure:

| Section | Level | Content |
|---------|-------|---------|
| Title | H1 | Max 64 chars, starts with action verb, use-case focused |
| Short Description | paragraph | Max 160 chars, identifies user takeaway |
| Table of Contents | H2 | Links to all sections |
| Detailed Description | H2 | Multiple paragraphs describing the use case and solution |
| See It in Action | H3 | Placeholder for demo video/Arcade links |
| Architecture Diagrams | H3 | Placeholder referencing `docs/images/` |
| Requirements | H2 | Parent section header |
| Notes on Requirements | text | Any critical user notes |
| Minimum Hardware | H3 | Based on AI capabilities selected |
| Minimum Software | H3 | Based on Red Hat products selected |
| Deploy | H2 | Placeholder deploy instructions |
| Delete | H3 | Placeholder cleanup instructions |
| Reference | H2 | Links to supporting docs |
| Optional Technical Sections | H2 | Placeholder for advanced content |
| Tags | H2 | Pre-populated MIST taxonomy tags based on gathered info |

For the Tags section, format as:

```markdown
## Tags

- Industry: <selected industry>
- Product: <selected Red Hat products>
- Use case: <brief use case category>
```

## Step 4: Ensure docs directory exists

```bash
mkdir -p docs/images
```

Create a placeholder file so the directory is tracked by git:

```bash
touch docs/images/.gitkeep
```

## Step 5: Initial commit

```bash
git add -A
git commit -m "Initial scaffold from ai-quickstart-template"
```

## Step 6: Summary

Tell the user what was created and suggest next steps:

1. Build out the application in `packages/`
2. Run `/quickstart:readme` to generate a full README once the app is built
3. Run `/quickstart:architecture` to generate architecture diagrams
4. Run `/quickstart:publish-check` before submitting for publication
