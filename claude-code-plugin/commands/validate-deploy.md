---
description: Validate deployment configuration for a Red Hat AI quickstart
disable-model-invocation: true
context: fork
agent: general-purpose
allowed-tools: Read, Glob, Grep, Bash
---

# Deployment Validator

Validate that the deployment configuration for this quickstart is complete, correct, and meets Red Hat AI quickstart requirements.

## Checks to perform

Run ALL of the following checks and report results as a checklist.

### 1. Compose file consistency

- [ ] `compose.yml` or `docker-compose.yml` exists
- [ ] Every service in the compose file has a corresponding Dockerfile or uses a public image
- [ ] All service ports are documented
- [ ] All `depends_on` references point to services that exist in the file
- [ ] No hardcoded secrets or passwords (check for `password`, `secret`, `api_key` in values)

### 2. Helm chart validation

- [ ] `deploy/helm/` directory exists with at least one chart
- [ ] `Chart.yaml` exists with valid name and version
- [ ] `values.yaml` exists
- [ ] Every service from `compose.yml` has a corresponding Helm template (Deployment + Service)
- [ ] No `ClusterRole`, `ClusterRoleBinding`, or other cluster-admin resources exist (quickstarts must not require admin permissions)
- [ ] Image references in Helm values match or are configurable
- [ ] Resource limits (CPU, memory) are defined for all containers

### 3. Dockerfile validation

- [ ] Dockerfiles exist for each custom service
- [ ] Base images are specified with version tags (not `latest`)
- [ ] No `RUN` commands that require root/sudo for runtime operations
- [ ] Multi-stage builds are used where appropriate

### 4. Makefile / build targets

- [ ] `Makefile` exists
- [ ] `make setup` or `make install` target exists for dependency installation
- [ ] `make dev` target exists for local development
- [ ] `make build` or `make containers-build` target exists
- [ ] `make deploy` target exists for deployment
- [ ] `make clean` or cleanup target exists

### 5. Environment variables

- [ ] `.env.example` or `.env.sample` exists documenting all required env vars
- [ ] All env vars referenced in code have corresponding entries in the example file
- [ ] No actual secrets or API keys are committed (search for patterns like `sk-`, `ghp_`, `token=`)
- [ ] Helm values provide configurable environment variables

### 6. README deployment instructions

- [ ] README has a "Deploy" section (H2)
- [ ] Deploy instructions reference actual commands that exist in the project (Makefile targets, scripts)
- [ ] README has a "Delete" section (H3)
- [ ] Delete instructions provide complete cleanup steps
- [ ] Prerequisites are listed before deployment steps

## Output format

Present results as a checklist with pass/fail status for each item:

```
## Deployment Validation Results

### Compose File: 4/5 passed
- [x] compose.yml exists
- [x] All services have Dockerfiles or public images
- [x] Service ports documented
- [x] depends_on references are valid
- [ ] ISSUE: Hardcoded password found in compose.yml line 23

### Helm Charts: 6/7 passed
...
```

At the end, provide:
- **Total score**: X/Y checks passed
- **Blocking issues**: Any items that MUST be fixed before publication
- **Recommendations**: Suggestions for improvement that are not strictly required
