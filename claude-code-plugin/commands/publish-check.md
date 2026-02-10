---
description: Run a comprehensive pre-publication readiness check for a Red Hat AI quickstart
disable-model-invocation: true
context: fork
agent: general-purpose
allowed-tools: Read, Glob, Grep, Bash
---

# Publishing Readiness Check

Run a comprehensive pre-publication checklist to verify this quickstart meets all requirements for submission to the Red Hat AI quickstart catalog on redhat.com.

## Checklist

Evaluate ALL of the following categories and report a detailed pass/fail summary.

### 1. README Quality — Clear, concise, and free of typos

Read the full README.md and evaluate:

- [ ] **Spelling and grammar**: No typos, misspellings, or grammatical errors. Pay close attention to technical terms, product names, and headings.
- [ ] **Conciseness**: No unnecessary filler words, redundant sentences, or overly verbose explanations. Each sentence should add value.
- [ ] **Clarity**: Instructions are unambiguous. A reader with limited experience could follow the deploy steps without guessing. No unexplained jargon.
- [ ] **Consistent formatting**: Headings use sentence case, code is in backticks, UI elements are bolded, lists are formatted consistently.
- [ ] **Active voice**: Instructions use active voice ("Run the command" not "The command should be run").
- [ ] **Red Hat terminology**: Product names are correct — "Red Hat OpenShift AI" on first reference, "OpenShift AI" subsequently. "quickstart" is one word, lowercase.

### 2. README Accuracy — Includes vertical use case

- [ ] **Vertical use case described**: The README clearly identifies a specific industry problem (e.g., healthcare clinical decision support, retail product recommendations, financial fraud detection) — not just a generic technology demo.
- [ ] **Industry context**: The Detailed Description explains the real-world business problem and how AI addresses it.
- [ ] **Accurate tech stack**: Technologies mentioned in the README match what is actually in the codebase. Check `package.json`, `pyproject.toml`, `compose.yml`, and Helm charts against what the README claims.
- [ ] **Accurate deploy instructions**: Every command listed in the Deploy section exists and is runnable (Makefile targets, scripts, Helm commands). Cross-reference each command against actual project files.
- [ ] **Accurate delete instructions**: Cleanup commands in the Delete section reference real targets/scripts in the project.
- [ ] **Accurate requirements**: Hardware and software requirements match what the application actually needs (check GPU references in Helm values, Python/Node versions in configs).

### 3. README Completeness — Follows template structure

Verify each required section exists and meets criteria:

| # | Section | Level | Required | Criteria |
|---|---------|-------|----------|----------|
| 1 | Title | H1 | Yes | Max 64 characters; starts with action verb; use-case focused |
| 2 | Short Description | text | Yes | Max 160 characters; identifies user takeaway |
| 3 | Table of Contents | H2 | Optional | Standard markdown format with working links |
| 4 | Detailed Description | H2 | Yes | Multiple paragraphs on use case and solution |
| 5 | See It in Action | H3 | Optional | Links to videos or Arcade demos |
| 6 | Architecture Diagrams | H3 | Yes | Images in `docs/images/` referenced with markdown |
| 7 | Requirements | H2 | Yes | Parent section header |
| 8 | Notes on Requirements | text | Optional | Critical user information |
| 9 | Minimum Hardware | H3 | Yes | Specific CPU, memory, GPU requirements |
| 10 | Minimum Software | H3 | Yes | Specific versions of required software |
| 11 | Deploy | H2 | Yes | Clear instructions assuming limited user knowledge |
| 12 | Delete | H3 | Yes | Complete cleanup instructions |
| 13 | Reference | H2 | Optional | Links to supporting documentation |
| 14 | Optional Technical Sections | H2 | Optional | Advanced deployment, deep dives |
| 15 | Tags | H2 | Yes | Bulleted list following MIST taxonomy format |

Additional structural checks:
- [ ] `docs/images/` directory exists and contains at least one architecture diagram
- [ ] Architecture diagrams are referenced from the README with markdown image syntax
- [ ] No broken relative links (check all `[text](path)` patterns for local paths that exist)
- [ ] Code blocks specify language for syntax highlighting
- [ ] Tags include required **Industry** and **Product** values in `- Tag name: value` format

### 4. End-to-End Validation — Runs without errors and is reproducible

Verify the quickstart can be built and run:

- [ ] **Dependencies install**: Run `make setup` or equivalent. Check exit code.
- [ ] **Builds successfully**: Run `make build` or equivalent. Check exit code.
- [ ] **Containers build**: If `compose.yml` exists, run `make containers-build` or `podman-compose build` or `docker compose build`. Check exit code.
- [ ] **Tests pass**: If test targets exist (`make test`, `npm test`, `pytest`), run them. Check exit code.
- [ ] **Linting passes**: If lint targets exist (`make lint`, `npm run lint`), run them. Check exit code.
- [ ] **No hardcoded paths**: Search for absolute paths like `/home/`, `/Users/`, or hardcoded hostnames that would break on other machines.
- [ ] **Environment documented**: `.env.example` or `.env.sample` exists and covers all required variables. No committed `.env` files with real values.
- [ ] **No committed secrets**: Search for patterns: `sk-`, `ghp_`, `api_key=`, `password=`, `secret=`, `token=` with actual values (not placeholders).
- [ ] **.gitignore complete**: Covers `node_modules`, `__pycache__`, `.env`, `.venv`, `dist/`, `build/`

If any build/test commands fail, report the exact error output. If commands don't exist, report which targets are missing.

### 5. Technical Review — Complete

- [ ] **No cluster admin required**: Search `deploy/` directory for `ClusterRole`, `ClusterRoleBinding`, `SecurityContextConstraints`, or `oc adm` commands. None should exist.
- [ ] **Resource limits defined**: Helm chart Deployments specify CPU and memory requests/limits.
- [ ] **Health checks present**: Deployments include readiness and/or liveness probes.
- [ ] **Dockerfiles use versioned base images**: No `FROM image:latest` — all base images should have specific version tags.
- [ ] **No root requirements at runtime**: Dockerfiles don't require `USER root` for the runtime stage.
- [ ] **Security**: No SQL injection, command injection, or other OWASP vulnerabilities in visible application code.
- [ ] **API endpoints secured**: If the app exposes APIs, check that authentication or access controls are mentioned.

### 6. Peer Review — Complete

These items cannot be fully automated. Flag them as requiring human verification:

- [ ] **Peer review performed**: Check for PR review comments, approved PRs, or a REVIEWERS file. If no evidence of peer review exists, flag as requiring human action.
- [ ] **Writing guide followed**: Content follows Red Hat corporate style — active voice, no jargon, accessible to non-experts.
- [ ] **UI is appealing and functional**: Flag that a human must verify the deployed UI is intuitive and demonstrates the use case effectively.
- [ ] **Deploy tested by someone other than the author**: Flag as requiring human confirmation.

### 7. Known Issues — Documented or resolved

- [ ] **GitHub Issues checked**: If this is a git repo with a remote, check for open issues. Run `gh issue list --state open` if the `gh` CLI is available. Report any open issues found.
- [ ] **Known limitations documented**: Check README for a "Known Issues", "Limitations", "Troubleshooting", or similar section. If the application has obvious limitations (e.g., specific GPU required, only works on certain OpenShift versions), verify they are documented.
- [ ] **TODOs resolved**: Search the codebase for `TODO`, `FIXME`, `HACK`, `XXX` comments. Report any found — these indicate unfinished work that should be resolved or documented before publication.
- [ ] **Placeholder content removed**: Search README for placeholder text like `TBD`, `TODO`, `PLACEHOLDER`, `INSERT`, `ADD HERE`, `your-name`, `example.com`. All placeholders should be replaced with real content.

## Output

Present results in this format:

```
# Publishing Readiness Report

## Summary: X/Y checks passed | Z blocking issues

### 1. README Quality: X/Y passed
- [x] Spelling and grammar: No issues found
- [x] Conciseness: Content is focused and efficient
- [ ] ISSUE: Passive voice in Deploy step 3 — "The container should be started" → "Start the container"
...

### 2. README Accuracy: X/Y passed
- [x] Vertical use case: Healthcare clinical decision support
- [ ] ISSUE: README claims Python 3.12 but pyproject.toml requires Python 3.11
...

### 3. README Completeness: X/10 required sections present
- [x] Title: "Build an AI-powered clinical assistant" (42 chars, action verb)
- [x] Short Description: "Deploy a clinical decision..." (128 chars)
- [ ] MISSING: Architecture Diagrams section
...

### 4. End-to-End Validation: X/Y passed
- [x] Dependencies install: `make setup` exited 0
- [ ] FAIL: `make test` exited 1 — 3 tests failed (output: ...)
...

### 5. Technical Review: X/Y passed
- [x] No cluster admin resources found
- [ ] ISSUE: Helm Deployment for `api` missing resource limits
...

### 6. Peer Review: X/Y passed (requires human verification)
- [ ] NEEDS HUMAN: No evidence of peer review found — ensure a teammate reviews before publishing
- [ ] NEEDS HUMAN: UI must be manually verified for usability
...

### 7. Known Issues: X/Y passed
- [ ] WARNING: 3 open GitHub issues found (#12, #15, #18)
- [ ] WARNING: 5 TODO comments found in codebase
- [x] No placeholder content in README
...

---

## Blocking Issues (must fix before publishing)
1. 3 failing tests in `make test`
2. Missing Architecture Diagrams section in README
3. README claims Python 3.12 but project requires 3.11

## Requires Human Verification
1. Peer review by a teammate
2. UI usability check
3. Deploy tested by someone other than author

## Recommendations (suggested improvements)
1. Add "See It in Action" section with demo video
2. Resolve 5 TODO comments in codebase
3. Address 3 open GitHub issues or document as known limitations

## Next Steps
- Fix blocking issues listed above
- Complete human verification items
- Run `/quickstart:architecture` to generate architecture diagrams
- Run `/quickstart:tags` to validate MIST taxonomy tags
- Once all checks pass, follow the publishing guide:
  https://github.com/rh-ai-quickstart/ai-quickstart-contrib/blob/main/PUBLISHING.md
```
