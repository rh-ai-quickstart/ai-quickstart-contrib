# Quick Starts Plugin for Claude Code

A Claude Code plugin to help authors create, validate, and publish [Red Hat AI quickstarts](https://docs.redhat.com/en/learn/ai-quickstarts).

## Usage

Requires Claude Code 2.1.38 or later.

```bash
claude --plugin-dir /path/to/quick-starts-plugin
```

Commands are namespaced under `quickstart:`:

| Command | Description |
|---------|-------------|
| `/quickstart:init` | Scaffold a new quickstart repo from the template |
| `/quickstart:readme` | Generate a complete README from codebase analysis |
| `/quickstart:architecture` | Generate architecture diagrams |
| `/quickstart:validate-deploy` | Validate deployment configuration |
| `/quickstart:tags` | Generate and validate MIST taxonomy tags |
| `/quickstart:publish-check` | Run pre-publication readiness checklist |

The plugin also includes an automatic README compliance hook and a style guide skill that Claude loads when relevant.

## Features

### `/quickstart:init` — Scaffold a new quickstart

Scaffolds a new quickstart repo from the [template](https://github.com/rh-ai-quickstart/ai-quickstart-template). Prompts for quickstart name, industry, use case description, AI capabilities needed, and target Red Hat products. Clones the template, renames all `ai-quickstart-template` placeholders, and generates a README scaffold with all 15 required sections.

### README Compliance Validator (automatic hook)

An agent-based `PostToolUse` hook that fires whenever a `README.md` is written or edited. Checks compliance against the 15-section format:

- Required sections present (title, short description, detailed description, architecture diagrams, requirements, deploy, delete, tags)
- Title ≤ 64 characters with an action verb
- Short description ≤ 160 characters
- Tags follow MIST taxonomy format
- Referenced architecture images exist in `docs/images/`

### `/quickstart:readme` — Generate a README

Runs in a forked subagent. Scans the codebase to understand the architecture (routes, models, services, deployment configs), identifies the tech stack from `package.json`, `pyproject.toml`, and Helm charts, then generates all 15 required sections. Pass a use case description as an argument:

```
/quickstart:readme AI-powered fraud detection for financial transactions
```

### `/quickstart:architecture` — Generate architecture diagrams

Analyzes `compose.yml`, Helm charts, and API routes to discover service topology. Generates Mermaid diagrams (default) or ASCII diagrams. Optionally renders to SVG/PNG in `docs/images/` using mermaid-cli and updates the README reference.

```
/quickstart:architecture mermaid
/quickstart:architecture ascii
```

### `/quickstart:validate-deploy` — Validate deployment config

Runs in a forked subagent. Checks:

- Compose file consistency (services have Dockerfiles, no hardcoded secrets)
- Helm chart validation (no cluster-admin resources, resource limits defined)
- Dockerfile quality (versioned base images, no root requirements)
- Makefile targets (setup, dev, build, deploy, clean)
- Environment variable documentation (`.env.example` exists and is complete)
- README deploy/delete instructions reference real project commands

### `/quickstart:tags` — MIST tag assistant

Analyzes the project to suggest appropriate MIST taxonomy tags (Industry, Product, Use Case, Partners, Topic). Validates existing tags against the taxonomy and generates a correctly formatted Tags section for the README.

```
/quickstart:tags healthcare clinical decision support
```

### `/quickstart:publish-check` — Publishing readiness checklist

Runs in a forked subagent. Evaluates 7 categories covering the full publication criteria:

1. **README Quality** — spelling, grammar, conciseness, clarity, active voice, Red Hat terminology
2. **README Accuracy** — vertical use case described, tech stack matches codebase, deploy/delete commands reference real project files
3. **README Completeness** — all 15 required sections present with correct formatting, architecture images exist, no broken links
4. **End-to-End Validation** — runs build, tests, and lint; checks for hardcoded paths, committed secrets, `.gitignore` coverage
5. **Technical Review** — no cluster-admin resources, resource limits defined, versioned base images, no root at runtime, security check
6. **Peer Review** — flags items requiring human verification (PR reviews, UI usability, cross-person deploy testing)
7. **Known Issues** — checks open GitHub issues, searches for `TODO`/`FIXME` comments, flags placeholder content

Outputs a pass/fail checklist with blocking issues, items requiring human verification, and recommendations.

### Style guide (auto-invoked skill)

Claude automatically loads Red Hat writing conventions when working on quickstart content. Covers voice and tone, formatting (bold UI elements, monospace for code), quickstart-specific rules, and Red Hat terminology. Includes reference files for the full README format spec, MIST taxonomy, and quality criteria.

## Plugin Structure

```
quick-starts-plugin/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   ├── architecture.md
│   ├── init.md
│   ├── publish-check.md
│   ├── readme.md
│   ├── tags.md
│   └── validate-deploy.md
├── skills/
│   └── rh-style-guide/
│       ├── SKILL.md
│       └── reference/
│           ├── mist-taxonomy.md
│           ├── readme-format.md
│           └── quality-criteria.md
└── hooks/
    └── hooks.json
```

## Resources

- [Red Hat AI Quickstarts Catalog](https://docs.redhat.com/en/learn/ai-quickstarts)
- [Quickstart Contribution Guide](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/blob/main/CONTRIBUTING.md)
- [Quickstart Template Repo](https://github.com/rh-ai-quickstart/ai-quickstart-template)
- [Publishing Guide](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/blob/main/PUBLISHING.md)
- [Claude Code Plugins Documentation](https://code.claude.com/docs/en/plugins)
