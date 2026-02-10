---
description: Generate or regenerate a complete README.md for a Red Hat AI quickstart
disable-model-invocation: true
argument-hint: [use-case description]
context: fork
agent: general-purpose
allowed-tools: Read, Glob, Grep, Bash, Write
---

# Quickstart README Generator

Generate a complete, standards-compliant README.md for a Red Hat AI quickstart repository. The user provides a brief use case description: "$ARGUMENTS"

## Instructions

Thoroughly analyze the codebase to understand the application architecture, then generate a README that meets all 15 required sections from the Red Hat AI quickstart contribution guide.

### Phase 1: Codebase Analysis

Scan the project to gather information about:

1. **Tech stack** — Read `package.json`, `pyproject.toml`, `requirements.txt`, `go.mod`, or similar dependency files to identify frameworks and libraries
2. **Services** — Read `compose.yml` or `docker-compose.yml` to identify all services (frontend, backend, database, model serving, etc.)
3. **API routes** — Search for route definitions (FastAPI routers, Express routes, etc.) to understand backend capabilities
4. **Frontend** — Identify the UI framework and key pages/components
5. **AI/ML components** — Look for model configurations, LLM integrations, vector databases, embedding models, guardrails
6. **Deployment** — Read Helm charts in `deploy/helm/`, Dockerfiles, and Makefile targets
7. **Environment variables** — Collect all required env vars from `.env.example`, Dockerfiles, and code
8. **Hardware requirements** — Check for GPU requirements in Helm values, model configs, or documentation
9. **Architecture images** — Check `docs/images/` for existing diagrams

### Phase 2: README Generation

Write a complete README.md with ALL of the following sections. Follow Red Hat writing conventions: active voice, no jargon, bold UI element names.

#### Section 1: Title (H1)
- Max 64 characters
- Starts with an action verb (Build, Deploy, Create, Monitor, Analyze, etc.)
- Use-case focused, not technology-focused

#### Section 2: Short Description
- Single paragraph immediately after the title
- Max 160 characters
- Identifies what the user will achieve

#### Section 3: Table of Contents (H2)
- Standard markdown links to all sections

#### Section 4: Detailed Description (H2)
- Multiple paragraphs explaining:
  - The industry problem being solved
  - How AI addresses it
  - What the user will have after deploying
  - Key features and capabilities

#### Section 5: See It in Action (H3)
- Placeholder: `> Add links to demo videos or Arcade interactive experiences here.`

#### Section 6: Architecture Diagrams (H3)
- If images exist in `docs/images/`, reference them with `![description](docs/images/filename.png)`
- If no images exist, add a placeholder: `> Add architecture diagram to docs/images/ and reference it here.`

#### Section 7: Requirements (H2)
- Parent section header only

#### Section 8: Notes on Requirements (text under Requirements)
- Any critical information users should know before starting

#### Section 9: Minimum Hardware (H3)
- Specific CPU, memory, storage, GPU requirements
- Base on the AI models and services discovered in Phase 1

#### Section 10: Minimum Software (H3)
- Specific versions of required software
- OpenShift version, oc CLI, Helm, Python, Node.js, etc.
- Based on what was discovered in Phase 1

#### Section 11: Deploy (H2)
- Clear step-by-step deployment instructions
- Include prerequisites setup, configuration, and deployment commands
- Reference actual Makefile targets, Helm commands, or scripts found in the project
- Assume the reader has limited experience — be explicit

#### Section 12: Delete (H3)
- Instructions for complete cleanup
- Reference actual cleanup commands from the project (Makefile targets, helm uninstall, etc.)

#### Section 13: Reference (H2)
- Links to relevant Red Hat documentation
- Links to upstream project docs (e.g., LangChain, LlamaIndex, Hugging Face)

#### Section 14: Optional Technical Sections (H2)
- If the project has notable technical depth, add sections for:
  - Advanced configuration
  - Guided experience / walkthrough
  - Troubleshooting

#### Section 15: Tags (H2)
- Bulleted list in `- Tag name: value` format
- Required tags:
  - **Industry**: Based on the use case
  - **Product**: Red Hat products used (e.g., OpenShift AI, RHEL AI)
- Optional tags (include if applicable):
  - **Use case**: Category of the AI use case
  - **Partners**: Any partner technologies
  - **Topic**: Technical topics (e.g., RAG, Agents, Guardrails)

### Phase 3: Write the file

Write the generated README to `README.md` in the project root.

Report a summary of what was generated and any sections that need manual attention (e.g., missing architecture diagrams, placeholder deploy instructions if no Makefile was found).
