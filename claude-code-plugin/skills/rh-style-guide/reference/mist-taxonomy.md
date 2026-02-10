# MIST Taxonomy Reference

MIST (Metadata Initiative for Structured Taxonomy) is Red Hat's tagging system for categorizing content. All quickstarts published to the redhat.com catalog must include MIST-compliant tags.

## Tag Format

Tags appear in the README's Tags section (H2) as a bulleted markdown list:

```markdown
## Tags

- Industry: Healthcare
- Product: Red Hat OpenShift AI
- Use case: Clinical Decision Support
- Partners: NVIDIA
- Topic: RAG, Guardrails
```

## Required Tags

### Industry

The primary industry this quickstart targets. Choose one:

| Value | Description |
|-------|-------------|
| Retail | E-commerce, inventory, supply chain, customer experience |
| Healthcare | Clinical, pharmaceutical, medical devices, patient care |
| Financial Services | Banking, insurance, trading, risk, compliance |
| Manufacturing | Production, quality control, predictive maintenance |
| Telecommunications | Network operations, customer service, billing |
| Government | Public sector, defense, civic services |
| Energy | Oil & gas, utilities, renewable energy, grid management |
| Education | Higher education, e-learning, research |
| Media & Entertainment | Content creation, streaming, publishing |
| Transportation & Logistics | Fleet management, route optimization, warehousing |
| Cross-industry | Broadly applicable across multiple industries |

### Product

The featured Red Hat product. One or more of:

| Value | Description |
|-------|-------------|
| Red Hat OpenShift AI | ML/AI platform on OpenShift |
| RHEL AI | AI capabilities on Red Hat Enterprise Linux |
| Red Hat OpenShift Container Platform | Base container platform |
| Red Hat Ansible Automation Platform | IT automation |
| Red Hat Enterprise Linux | Base operating system |

## Required if Applicable

### Partners

Technology partners whose products are prominently used:

| Value | When to use |
|-------|------------|
| Intel | OpenVINO, Intel GPUs, Intel-optimized runtimes |
| NVIDIA | NVIDIA GPUs, CUDA, TensorRT, NIM |
| IBM | watsonx, IBM models, IBM Cloud |
| AWS | Amazon SageMaker, Bedrock, EKS integration |
| Azure | Azure OpenAI, AKS integration |
| Google Cloud | Vertex AI, GKE integration |

## Optional Tags

### Use case

Category of the AI use case:

- Customer Service / Virtual Agent
- Predictive Maintenance
- Fraud Detection
- Content Generation
- Document Processing / Extraction
- Clinical Decision Support
- Product Recommendation
- Anomaly Detection
- Log Analysis
- Compliance Monitoring
- Data Governance
- IT Process Automation
- Image / Video Analysis
- Sentiment Analysis
- Knowledge Management

### Topic

Technical topics demonstrated:

- RAG (Retrieval-Augmented Generation)
- Agents / Agentic Workflows
- Guardrails / Safety
- Fine-tuning
- Computer Vision
- NLP / Text Processing
- Prompt Engineering
- Model Serving
- Vector Search
- Embedding Models
- Multi-modal AI
- Observability / Monitoring

### Business challenge

The business problem addressed:

- Operational Efficiency
- Customer Experience
- Risk Management
- Compliance & Governance
- Cost Reduction
- Revenue Growth
- Employee Productivity
- Decision Intelligence

### Resource type

Always set to `Quickstart` for AI quickstart repositories.
