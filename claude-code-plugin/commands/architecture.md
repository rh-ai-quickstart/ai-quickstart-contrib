---
description: Generate architecture diagrams for a Red Hat AI quickstart by analyzing compose files, Helm charts, and API routes
disable-model-invocation: true
argument-hint: [output-format: mermaid|ascii]
allowed-tools: Read, Glob, Grep, Bash, Write
---

# Architecture Diagram Generator

Analyze the codebase and generate architecture diagrams showing the service topology, data flow, and component relationships. The user may specify an output format as `$ARGUMENTS` (defaults to mermaid).

## Phase 1: Service Discovery

Scan the project to identify all services and their relationships:

1. **Container services** — Read `compose.yml` or `docker-compose.yml` for service definitions, ports, networks, and dependencies (`depends_on`)
2. **Helm chart services** — Read files in `deploy/helm/*/templates/` for Kubernetes Deployments, Services, and Ingress resources
3. **API endpoints** — Search for route definitions in the backend code:
   - FastAPI: `@app.get`, `@app.post`, `@router.`
   - Express: `app.get`, `app.post`, `router.`
4. **Database connections** — Search for database connection strings, SQLAlchemy engines, or Prisma schemas
5. **AI/ML services** — Look for:
   - Model serving endpoints (vLLM, TGI, Ollama configs)
   - Vector database connections (pgvector, Milvus, ChromaDB)
   - LLM API calls (OpenAI-compatible endpoints, LangChain, LlamaIndex)
   - Guardrail services
6. **External dependencies** — Identify any external APIs or services referenced

## Phase 2: Diagram Generation

Based on the discovered architecture, generate diagrams in the requested format.

### Mermaid format (default)

Generate a Mermaid diagram using the following conventions:

```
graph TD
    User[User / Browser] --> UI[Frontend<br/>React + Vite]
    UI --> API[Backend API<br/>FastAPI]
    API --> DB[(PostgreSQL<br/>+ pgvector)]
    API --> LLM[LLM Service<br/>vLLM / TGI]
    API --> Guard[Guardrails<br/>Detectors]
```

Guidelines:
- Use `graph TD` (top-down) for the primary architecture view
- Group related services visually
- Label edges with protocols or data types where meaningful (e.g., `-->|REST|`, `-->|gRPC|`)
- Use appropriate node shapes: `[]` for services, `[()]` for databases, `{{}}` for external services
- Include port numbers if they aid understanding

### ASCII format

Generate a clean ASCII box diagram:

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│   Browser   │────>│   Frontend   │────>│  Backend API │
│             │     │  React/Vite  │     │   FastAPI    │
└─────────────┘     └──────────────┘     └──────┬───────┘
                                                │
                                    ┌───────────┼───────────┐
                                    │           │           │
                              ┌─────▼─────┐ ┌──▼───┐ ┌────▼─────┐
                              │ PostgreSQL │ │ vLLM │ │Guardrails│
                              │ + pgvector │ │      │ │          │
                              └───────────┘ └──────┘ └──────────┘
```

## Phase 3: Write output files

1. Write the Mermaid diagram to `docs/architecture.mmd` (if mermaid format)
2. Write an ASCII version as a comment block at the top of the Mermaid file for quick reference
3. If the `mmdc` (mermaid-cli) tool is available, attempt to render to SVG:
   ```bash
   npx -y @mermaid-js/mermaid-cli mmdc -i docs/architecture.mmd -o docs/images/architecture.svg -t dark
   ```
   If `mmdc` is not available, inform the user they can install it with `npm install -g @mermaid-js/mermaid-cli`
4. If SVG was generated, also render a PNG for README embedding:
   ```bash
   npx -y @mermaid-js/mermaid-cli mmdc -i docs/architecture.mmd -o docs/images/architecture.png -t dark
   ```

## Phase 4: Update README

Check if README.md exists and has an "Architecture Diagrams" section (H3). If so, update it to reference the generated image:

```markdown
### Architecture Diagrams

![Architecture diagram](docs/images/architecture.png)
```

If the README doesn't have this section, inform the user to add the reference manually or run `/quickstart:readme` to regenerate the full README.

## Phase 5: Summary

Report:
- Number of services discovered
- The generated diagram (display the Mermaid source inline)
- Which output files were created
- Whether the README was updated
