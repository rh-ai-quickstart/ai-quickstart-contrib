---
description: Generate and validate MIST taxonomy tags for a Red Hat AI quickstart README
disable-model-invocation: true
argument-hint: [industry or use-case hint]
allowed-tools: Read, Glob, Grep
---

# MIST Tag Assistant

Analyze this quickstart project and generate appropriate MIST (Metadata Initiative for Structured Taxonomy) tags for the README's Tags section. The user may provide a hint about the industry or use case: "$ARGUMENTS"

## MIST Taxonomy Reference

### Required Tags

**Industry** — The target industry for this quickstart. Valid values include:
- Retail
- Healthcare
- Financial Services
- Manufacturing
- Telecommunications
- Government
- Energy
- Education
- Media & Entertainment
- Transportation & Logistics
- Cross-industry (if broadly applicable)

**Product** — The featured Red Hat product. Valid values include:
- Red Hat OpenShift AI
- RHEL AI
- Red Hat OpenShift Container Platform
- Red Hat Ansible Automation Platform
- Red Hat Enterprise Linux

### Required if Applicable

**Partners** — Technology partners whose products are used. Examples:
- Intel
- NVIDIA
- IBM
- AWS
- Azure
- Google Cloud

### Optional Tags

- **Use case** — Category of the AI use case (e.g., Customer Service, Predictive Maintenance, Fraud Detection, Content Generation, Document Processing)
- **Product line** — Broader product family
- **Business challenge** — The business problem addressed (e.g., Operational Efficiency, Customer Experience, Risk Management, Compliance)
- **Region** — If regionally specific
- **Resource type** — Type of content (e.g., Quickstart, Tutorial, Demo)
- **Services** — Red Hat services involved
- **Sub type** — More specific categorization
- **Topic** — Technical topics (e.g., RAG, Agents, Guardrails, Computer Vision, NLP, Fine-tuning)

## Analysis Steps

### Step 1: Detect technologies and context

Scan the project to identify:
- **AI frameworks**: LangChain, LlamaIndex, Hugging Face, PyTorch, TensorFlow
- **Model serving**: vLLM, TGI, Ollama, OpenVINO
- **Vector databases**: pgvector, Milvus, ChromaDB, Pinecone
- **Red Hat products**: OpenShift references in Helm charts, RHEL references in Dockerfiles
- **Partner technologies**: Intel OpenVINO, NVIDIA GPU references, cloud provider SDKs
- **Domain indicators**: Industry-specific terminology in code, configs, or existing docs

### Step 2: Read existing README

Read the README.md to understand:
- The stated use case and industry
- Any existing tags section
- The detailed description for domain context

### Step 3: Generate tags

Based on the analysis, generate a complete Tags section:

```markdown
## Tags

- Industry: <detected or suggested industry>
- Product: <detected Red Hat products>
- Use case: <categorized use case>
- Partners: <detected partner technologies>
- Topic: <detected technical topics>
- Resource type: Quickstart
```

### Step 4: Validate existing tags

If the README already has a Tags section, validate:
- [ ] Format follows `- Tag name: value` pattern
- [ ] Required tags (Industry, Product) are present
- [ ] Tag values match known valid values from the taxonomy
- [ ] No duplicate tags

Report any issues and provide the corrected version.

### Step 5: Present results

Show the user:
1. The recommended tags with reasoning for each choice
2. Any tags they should verify (e.g., Industry choice when multiple could apply)
3. The formatted Tags section ready to paste into the README

If the user wants to apply the tags directly, update the Tags section of README.md.
