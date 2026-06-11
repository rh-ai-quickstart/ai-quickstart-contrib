# Publishing guide

This guide covers everything you need to publish your quickstart to the [AI quickstart catalog](https://docs.redhat.com/en/learn/ai-quickstarts) on redhat.com — from content quality to technical workflow. Not every quickstart qualify to be published on redhat.com and in order to do so, specific requirements have to be met. 

---

## Table of Contents

* [Before You Publish: Content Requirements](#before-you-publish-content-requirements)
  * [Naming and Branding Consistency](#naming-and-branding-consistency)
  * [The Content Toolbox](#the-content-toolbox)
  * [SEO and Legal Guidance](#seo-and-legal-guidance)
* [The Publishing Process](#the-publishing-process)
  * [Prerequisites](#prerequisites)
  * [Publish](#publish)
  * [Update an Existing Quickstart](#update-an-existing-quickstart)

---

## Before you publish: Content requirements

Creating content that meets Red Hat's corporate standards ensures your quickstart publishes faster and protects Red Hat legally. Following these practices makes your content compliant, accessible, and optimized for search.

### Naming and branding consistency

Improper product naming is the most common reason for editorial delays. Accurate naming protects our trademarks and ensures a professional brand presence.

* **Use the Official List:** Always cross-reference the [Official Red Hat Product Names List](https://docs.google.com/spreadsheets/d/1DLS_lS3VKidgZIvcLmLp9BoiqptkvqHWfe1D5FD2kfk/edit?gid=1259317633#gid=1259317633) (OPL).
* **The "First Mention" Rule:** Use the full product name with the appropriate trademark symbol on the first mention _only_ (e.g., **Red Hat® OpenShift®**) on the first mention. Subsequent mentions can use approved short names (e.g., **OpenShift**). Always refer to the OPL for the latest information on short names.
* **Abbreviations:** Ensure the product name is stylized correctly. If a trademark or registered mark is required, include it. Avoid unauthorized abbreviations like "RHAI" or "RAI." For more information, always refer to the OPL.

### The Content Toolbox

The [BX Content Toolbox](https://red.ht/content-toolbox) is your primary resource for self-editing (VPN Required). Using these tools before submission will speed up the publishing process and save Red Hat money.

**Key Focus Areas:**
* **Style Guide:** Check for Red Hat-specific grammar, punctuation, and "voice and tone" (conversational yet professional).
* **Accessibility Analyzer:** Ensure your quickstart meets WCAG 2.2 AA standards.
  * **Headings:** Use logical nesting (H2 > H3).
  * **Alt Text:** All images must have descriptive alt text that explains the function or meaning of the image, not just a literal description. AI tools can help generate alt text. Consider using a prompt asking for accessibility alt text for your image.
    * For example, markdown image links should be descriptive: `[Architectural diagram for document ingestion](path to image)`, NOT `[image1](path to image1)`
* **Inclusive Language:** Use the analyzer to flag non-inclusive terms (e.g., replace "master/slave" with "primary/secondary" or "blacklist" with "blocklist").

### SEO and Legal Guidance

To ensure your quickstart is discoverable and legally sound, follow these requirements:

**SEO Best Practices**

* **Short Descriptions:** Every guide must start with a concise, 1-2 sentence abstract that summarizes the value proposition.
* **Keywords:** Include "AI," "quickstart," and the specific product name in the first paragraph.
* **Link Text:** Use descriptive link text. Avoid "Click here" or "Read more." Use "Download the Red Hat Enterprise Linux installation guide."

**Legal & AI Compliance**

* **Disclosure:** If any part of the quickstart was generated using AI, consult legal on whether a disclosure (e.g., "Assisted-by: AI") is required.
* **No Guarantees:** Avoid language that "guarantees" specific performance metrics or outcomes, as AI results can vary based on user data.
* **Copyright:** Do not use copyrighted third-party material or logos within your examples.

---

## The Publishing Process

### Prerequisites 

1. quickstart repository is in the [AI quickstart GitHub organization](https://github.com/rh-ai-quickstart)
2. quickstart meets [repository requirements](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/blob/main/CONTRIBUTING.md#what-are-the-repository-requirements)

### Publish

Using gitflow workflow: 
1. fork or clone [ai-quickstart-pub](https://github.com/rh-ai-quickstart/ai-quickstart-pub)
2. branch from main with a _descriptive_ branch name: 
```
# update branch name first
git checkout -b [INSERT BRANCH NAME HERE] 
```
3. use `git submodule` to add your quickstart to the `quickstart/` folder
```
# assuming reference to main:latest
# update your repo details
git submodule add https://github.com/rh-ai-quickstart/INSERT-QUICKSTART-REPO-NAME.git quickstart/INSERT-QUICKSTART-REPO-NAME
```
4. `git add`, `git commit`
5. `git push` to origin
6. open a pull request to [ai-quickstart-pub](https://github.com/rh-ai-quickstart/ai-quickstart-pub) main branch
7. PR will be reviewed and approved by the `publication-admin` team. Please be available to make changes or updates during the review


### Pull Request Review (best-effort) SLA

For timely reviews, `rh-ai-quickstart/@publication-admin` team will follow, to the best of our ability, the following "service level agreements": 

**Review timeline:**
1. **Automated review:** When you open a PR, an AI reviewer will review and compare your README file to the standards and requirements set in [this repository](https://www.github.com/rh-ai-quickstart/ai-quickstart-contrib)
2. **Human review:** A member of the `rh-ai-quickstart/@publication-admin` team will aim to review, accept, reject and/or comment on your PR **within 7 days** of submission.
3. **Contributor response:** If a human reviewer comments or requests changes, the contributor has 21 days to acknowledge or update the PR. 
  * PRs with no contributor response after 21 days will be closed to keep the queue manageable.
  * Closes PRs can be reopened at any time by adding a comment when you're ready to continue.

**What this means for you:**
* Monitor your PR for AI-generated feedback and address issues early.
* If issues are addressed, update the submodule so human reviewers are up to date on your changes.
* Respond/acknowledge human reviewer comments to avoid automatic closure.
* If you need more time, just say so by leaving a comment on the PR to keep it active. 

**What is not enforced?**
* No escalations are enforced at this time should the PR SLA be breached. 
* Human reviewers are repeatedly notified
* If the SLA is breached, please contact the [@publication-admin](https://github.com/orgs/rh-ai-quickstart/teams/publication-admin) by commenting in your PR.


### Update an Existing Quickstart
1. update your cloned or forked version of [ai-quickstart-pub](https://github.com/rh-ai-quicksart/ai-quickstart-pub) with `git pull`
2. create a new branch 
```
git checkout -b [INSERT BRANCH NAME HERE]
```
3. change directories to your quickstart. Using `llm-cpu-serving` as an example: 
```
cd quickstart/llm-cpu-serving
git pull
```
4. change directories 
```
cd ../../
```
5. `git add`, `git commit`, `git push` 
6. open a new PR 

