# Maintenance, Deprecation, and Archival Policy

This document defines maintenance expectations, deprecation criteria, and archival processes for AI quickstarts in the [rh-ai-quickstart](https://github.com/rh-ai-quickstart) organization to help maintain a high quality customer experience.

The policy applies to all repositories in the AI quickstart ([rh-ai-quickstart](https://github.com/rh-ai-quickstart)) organization because of the program's visibility and impact on Red Hat's reputation and customer experience.

> **NOTE:** AI quickstart program maintainers will update this policy as needed and without warning as program, customer or community needs shift over time.


## Guiding Principles

- **Grace periods, not sudden removal**: Quickstarts move through notification and deprecation stages before archival, giving maintainers time to respond
- **Preservation over deletion:** Archived quickstarts remain accessible as read-only repositories for reference and learning
- **Revival is possible:** Archived quickstarts can be restored if a maintainer commits to ongoing support
- **Transparency:** Maintainers and users are notified at each stage transition
- **Automation with human review:** Quickstarts requiring maintenance are identified through automation 


## Overview 

When a quickstart fails to meet maintenance standards (defined below), it moves through a staged process: 

### Stage 1: Notification of maintenance required
- **Trigger:** Any maintenance related trigger defined below 
- **Actions:** Maintainer notified, GitHub issue created, Issue tracked at program level
- **Goal:** Opportunity to fix, find new maintainer to fix, or opt for deprecation
- **Expectations:** Issue resolved within timeline, general quickstart functionality check, ask for help if you need it
- **Timeline:** 60 days (extensions granted for complex issues, partner or community engagement)

### Stage 2: Deprecation
- **Trigger:** Maintenance window expired without improvement
- **Actions:** Unpublished from catalog (if applicable), consumers notified, repo marked "deprecated"
- **Goal:** Protect customer experience, opportunity to fix and republish 
- **Expectations:** Maintainers fix issue and republish quickstart or opt to archive 
- **Timeline:** 30 days 

### Stage 3: Archival 
- **Trigger:** Deprecation timeline expired without resolution 
- **Action:** Repository is archived (public for published quickstarts, privately for unpublished), removed from promotional materials, or moved to a separate GitHub organization if needed
- **Goal:** Preserve history and credit while protecting customer experience
- **Timeline:** Indefinite 
- **Revival:** Archived quickstarts can be restored if a maintainer commits to ongoing support
- **Voluntary archival:** Contributors may choose to archive a quickstart on their own for any reason. Contact the administration team for assistance. 


## Maintenance standards and action triggers 

> **NOTE:** Maintainers are expected to maintain their quickstarts proactively. The triggers below define when the admin team will intervene. Please do not wait for notifications to address issues.

**Review cadence:** The AI quickstart program runs automated maintenance checks quarterly (or on-demand). Quality evaluation uses AI to assess README structure, repository metadata (LICENSE, description, images), tag format, application type (must have UI, not notebook-only), and business value against [CONTRIBUTING.md](CONTRIBUTING.md) requirements.

The following conditions trigger a notification of maintenance required:

| Trigger | Criteria | Maintainer action | 
|----|----|----|
| **Inactivity** | 6+ month old open issues OR Pull Requests | Review for updates, freshness, accuracy, etc. Create plan to publish or deprecate | 
| **Product versions** | Quickstart references unsupported versions of OpenShift (OCP), OpenShift AI (RHOAI), or AI Inference Server (RHAIIS) based on [Red Hat lifecycle data](https://access.redhat.com/support/policy/updates) | Update to supported product versions per lifecycle policy |
| **Product compatibility** | Incompatible product version combinations (e.g., RHOAI 3.5 and OCP 4.16 are not compatible) | Update to compatible versions per [compatibility matrix](https://access.redhat.com/support/policy/updates/rhoai-sm/lifecycle#dates) |
| **Does not meet quickstart requirements** | quickstart does not meet requirements defined in [documentation](CONTRIBUTING.md) | Update, deprecate or transfer accordingly | 

### What gets checked for "Does not meet requirements"

When this trigger fires, one or more of these automated checks failed:

**Repository basics:**
- Has open source LICENSE file (MIT, Apache-2.0, etc.)
- Has GitHub repository description filled in (Settings → About)
- Has `docs/images/` folder with images

**README structure:**
- Title ≤64 characters, starts with action verb
- Short description ≤160 characters
- Has required H2 sections: Detailed description, Requirements, Deploy, Tags
- Has required H3 sections: Architecture, Hardware requirements, Software requirements, Delete

**Tags:**
- Tags section uses format: `- **Key:** Value` (bullet + colon required)
- Has valid Industry tag from [official list](CONTRIBUTING.md#industry-tags)

**Application type:**
- Has deployable application with UI (not notebook-only)

**Product versions:**
- Uses supported versions of OCP, RHOAI, RHAIIS
- RHOAI + OCP versions are compatible

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed requirements and examples.

## Disclaimer 

This policy is short on purpose. It's not designed to generate issues for our community. Its purpose is to create a maintenance baseline to ensure quality experiences for our community and customers. To that point, this policy will change over time to address needs appropriately.
