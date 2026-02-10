# README Format Specification

All Red Hat AI quickstart READMEs must follow this 15-section structure. Sections marked "Required" must be present for publication approval.

## Section Reference

### 1. Title (H1) — Required

- Maximum 64 characters
- Must start with an action verb (Build, Deploy, Create, Monitor, Analyze, Detect, Generate, Automate, etc.)
- Must be use-case focused, describing what the user will accomplish
- Do NOT lead with technology names

**Good examples:**
- "Build an AI-powered virtual agent for customer service"
- "Monitor PPE compliance with computer vision"
- "Automate IT processes with an AI self-service agent"

**Bad examples:**
- "LangChain RAG Demo on OpenShift" (technology-focused, no action verb)
- "AI Quickstart" (too generic)
- "Building an enterprise-grade retrieval-augmented generation system..." (too long)

### 2. Short Description (text) — Required

- Single paragraph immediately after the H1 title
- Maximum 160 characters
- Must identify what the user will take away from this quickstart
- Focus on the outcome, not the technology

### 3. Table of Contents (H2) — Optional

- Standard markdown anchor links to all sections
- Helps navigation in longer READMEs

### 4. Detailed Description (H2) — Required

- Multiple paragraphs explaining:
  - The industry problem being addressed
  - How AI/ML solves this problem
  - What the deployed quickstart provides
  - Key features and capabilities
- Should be 2-4 paragraphs

### 5. See It in Action (H3) — Optional

- Links to demo videos hosted externally
- Links to Arcade interactive experiences
- Screenshots of the running application

### 6. Architecture Diagrams (H3) — Required

- Must reference images stored in `docs/images/`
- Use standard markdown image syntax: `![description](docs/images/filename.png)`
- Diagram should show all major components and their relationships
- Include data flow direction

### 7. Requirements (H2) — Required

- Parent section header only (content goes in subsections below)

### 8. Notes on Requirements (text) — Optional

- Critical information users must know before starting
- Warnings about resource consumption, costs, or prerequisites

### 9. Minimum Hardware (H3) — Required

- Specific CPU, memory, and storage requirements
- GPU requirements if applicable (type, VRAM)
- Must not surprise users — list everything needed
- Example format:
  ```
  - CPU: 8 cores
  - Memory: 32 GB RAM
  - Storage: 100 GB
  - GPU: NVIDIA A10G or equivalent (24 GB VRAM)
  ```

### 10. Minimum Software (H3) — Required

- Specific version numbers for all required software
- Must list tested configurations
- Example format:
  ```
  - OpenShift Container Platform 4.14+
  - OpenShift AI 2.9+
  - oc CLI 4.14+
  - Helm 3.12+
  - Python 3.11+
  - Node.js 18+
  ```

### 11. Deploy (H2) — Required

- Clear, step-by-step deployment instructions
- Assume the reader has limited experience with the technologies
- Number each step
- Include actual commands from the project (Makefile targets, scripts)
- Show expected output where helpful
- Include configuration steps (environment variables, secrets)

### 12. Delete (H3) — Required

- Complete cleanup instructions
- Must remove ALL resources created during deployment
- Reference actual cleanup commands from the project
- Include both local and cluster cleanup if applicable

### 13. Reference (H2) — Optional

- Links to Red Hat product documentation
- Links to upstream project documentation
- Links to related blog posts or articles

### 14. Optional Technical Sections (H2) — Optional

- Advanced deployment configurations
- Deep-dive technical explanations
- Guided walkthrough experiences
- Troubleshooting guides

### 15. Tags (H2) — Required

- Bulleted list using `- Tag name: value` format
- Required tags: Industry, Product
- Required if applicable: Partners
- Optional: Use case, Product line, Business challenge, Region, Resource type, Services, Sub type, Topic
