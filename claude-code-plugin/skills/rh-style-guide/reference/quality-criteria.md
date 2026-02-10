# Quality Criteria for AI Quickstarts

Quickstarts must meet these quality criteria for inclusion in the Red Hat AI quickstart catalog on redhat.com.

## Must Have

### Deployable without admin permissions
- Must NOT require cluster admin access
- No `ClusterRole` or `ClusterRoleBinding` resources
- No operations requiring `oc adm` commands
- All resources must be namespace-scoped
- Regular users with standard project/namespace access must be able to deploy

### Appealing user interface
- Must include a frontend application that users can interact with
- The UI should demonstrate the AI capability in an intuitive way
- Dashboard, chat interface, form-based interface, or visual display
- Must be accessible via a web browser

### Industry use case focus
- Must demonstrate a real-world problem being solved with AI
- Technology should serve the use case, not be the focus itself
- The README must explain the industry context and business value
- "What problem does this solve?" must have a clear answer

### Complete deployment path
- Clear, tested deployment instructions
- Working `make` targets or equivalent scripts
- Environment variable documentation
- Cleanup/delete instructions that remove all created resources

## Must NOT

### Require cluster admin access
- No cluster-scoped resources
- No privileged security contexts
- No node-level operations

### Focus solely on technology
- A bare model serving endpoint is not a quickstart
- A technology demo without a use case is not a quickstart
- Must show AI solving a real problem, not just running

### Deploy isolated components without a UI
- A backend API alone is not sufficient
- Must have a user-facing interface
- Must have a usage pathway users can follow

## Recommended

### Interactive demo
- Arcade interactive experience or demo video
- Screenshots of the running application
- Guided walkthrough of key features

### Architecture documentation
- Clear architecture diagram showing all components
- Data flow documentation
- Explanation of AI/ML pipeline

### Comprehensive testing
- Automated tests for backend services
- Health check endpoints
- Deployment verification scripts
