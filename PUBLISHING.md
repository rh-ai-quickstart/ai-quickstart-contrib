# Publishing guide

This guide covers requirements and process to publish your quickstart to the [AI quickstart catalog](https://docs.redhat.com/en/learn/ai-quickstarts) on redhat.com.

---

## Table of Contents

* [Before you publish: quality standards](#before-you-publish-quality-standards)
  * [Naming and branding consistency](#naming-and-branding-consistency)
  * [Content quality (style, accessibility, SEO)](#content-quality)
  * [Legal and compliance](#legal-and-compliance)
  * [README quality standards](#readme-quality-standards)
* [The publishing process](#the-publishing-process)
  * [Prerequisites](#prerequisites)
  * [Submit for publication](#submit-for-publication)
  * [The review process](#the-review-process)
  * [Update an existing quickstart](#update-an-existing-quickstart)

---

## Before you publish: quality standards 

Creating content that meets Red Hat's corporate standards ensures your quickstart publishes faster and protects Red Hat legally. Following these practices makes your content compliant, accessible, and optimized for search.

### Naming and branding consistency

Improper product naming is the most common reason for editorial delays. Accurate naming protects our trademarks and ensures a professional brand presence.

* **Use the Official List:** Always cross-reference the [Official Red Hat Product Names List](https://docs.google.com/spreadsheets/d/1DLS_lS3VKidgZIvcLmLp9BoiqptkvqHWfe1D5FD2kfk/edit?gid=1259317633#gid=1259317633) (OPL).
* **The "First Mention" Rule:** Use the full product name with the appropriate trademark symbol on the first mention _only_ (e.g., **Red Hat® OpenShift®**) on the first mention. Subsequent mentions can use approved short names (e.g., **OpenShift**). Always refer to the OPL for the latest information on short names.
* **Abbreviations:** Ensure the product name is stylized correctly. If a trademark or registered mark is required, include it. Avoid unauthorized abbreviations like "RHAI" or "RAI." For more information, always refer to the OPL.

### Content quality

The [BX Content Toolbox](https://red.ht/content-toolbox) is your primary resource for self-editing (VPN Required). Using these tools before submission will speed up the publishing process and save Red Hat money.

**Key Focus Areas:**
* **Style Guide:** Check for Red Hat-specific grammar, punctuation, and "voice and tone" (conversational yet professional).
* **Accessibility Analyzer:** Ensure your quickstart meets WCAG 2.2 AA standards.
  * **Headings:** Use logical nesting (H2 > H3).
  * **Alt Text:** All images must have descriptive alt text that explains the function or meaning of the image, not just a literal description. AI tools can help generate alt text. Consider using a prompt asking for accessibility alt text for your image.
    * For example, markdown image links should be descriptive: `[Architectural diagram for document ingestion](path to image)`, NOT `[image1](path to image1)`
* **Inclusive Language:** Use the analyzer to flag non-inclusive terms (e.g., replace "master/slave" with "primary/secondary" or "blacklist" with "blocklist").

**SEO Best Practices**

* **Short Descriptions:** Every guide must start with a concise, 1-2 sentence abstract that summarizes the value proposition.
* **Keywords:** Include "AI," "quickstart," and the specific product name in the first paragraph.
* **Link Text:** Use descriptive link text. Avoid "Click here" or "Read more." Use "Download the Red Hat Enterprise Linux installation guide."

### Legal and compliance

To ensure your quickstart is discoverable and legally sound, follow these requirements:

**Legal & AI Compliance**

* **Disclosure:** If any part of the quickstart was generated using AI, consult legal on whether a disclosure (e.g., "Assisted-by: AI") is required.
* **No Guarantees:** Avoid language that "guarantees" specific performance metrics or outcomes, as AI results can vary based on user data.
* **Copyright:** Do not use copyrighted third-party material or logos within your examples.

---

### README quality standards 

#### Required content completeness

Your README must include all required sections from the [README structure requirements](CONTRIBUTING.md#readme-specifications):
- AI quickstart title (action-focused, starts with action verb, describes the business solution, <64 chars) 
- Short description (expand on business solution, <160 chars)
- Detailed description (2-3 paragraphs) 
- Architecture diagrams 
- Requirements (hardware & software - be specific!) 
- Deploy instructions 
- Delete instructions 
- Tags (approved Red Hat industry required) 

Missing any required section from the [README structure requirements guide](CONTRIBUTING.md#readme-specifications) is a **Blocker**.

#### Review severity levels 

Issues with your README file are classified by severity: 

##### **🚫 BLOCKER** - Must Fix Before Publication

**Criteria:** 
- **Security vulnerabilities:** Hard coded credentials, API keys, passwords in examples, or exposed secrets 
- **Broken critical paths:** Installation links return 404, deployment instructions are missing steps, or required actions are abset
- **Impossible deployment:** Requires manual admin approval, emailing for license files, or access to resources not publicly available 
- **Missing required README component:** README is missing any required section from [README structure requirements](CONTRIBUTING.md#readme-specifications)
- **Exceeding character limits:** README title and short description **MUST** be shorter than maximum char length
- **Broken links:** broken links to diagrams, internal or external links
- **Inappropriate Tagging:** Industry tag must reference [Red Hat approved industry tag](CONTRIBUTING.md#industry-tags)
- **Tag format:** Tags must be in dedicated section at the bottom of the README, in a bulleted list with key and value pairs with key in bold and value in normal text

**Examples:**
- ❌ Hardcoded password: `ADMIN_PASSWORD=secret123` in deployment instructions
- ❌ Installation link to a non-existent or inaccessible URL
- ❌ README states "Contact admin@redhat.com to request access to the license file"
- ❌ Missing Prerequisites, Installation, or Usage sections entirely
- ❌ Link to architectural diagram is broken
- ❌ `Industry: HR`
  - HR is not an approved industry tag
  - Entry is not a bulleted list
  - Industry is not bold

##### **⚠️ MAJOR** - Should Fix Before Publication

Quality issues that don't prevent publication but significantly impact user experience or brand compliance.

**Criteria:**
- **Trademark violations:** Trademark symbols (® or ™) used incorrectly (see [Naming and Branding Consistency](#naming-and-branding-consistency))
- **Structural problems:** Poor organization, missing recommended sections, or illogical flow
- **Unclear instructions:** Steps work but are confusing, lack context, or assume undocumented knowledge
- **Significant style violations:** Inconsistent formatting, unprofessional language, or accessibility issues
- **Technical inaccuracies:** Commands work but are suboptimal or misleading

**Examples:**
- "OpenShift™ AI uses OpenShift™ operators" (trademark symbol repeated - should only be on first mention)
- Missing Troubleshooting section for a complex multi-step deployment
- Command shown as `sudo ./install.sh` without explaining why sudo is required
- Using non-inclusive language flagged by the Content Toolbox analyzer

**IMPORTANT:** Trademark formatting issues are **ALWAYS "major"**, never "blocker". They impact brand compliance but don't prevent deployment.

##### **ℹ️ MINOR** - Nice to Have

Polish improvements that enhance clarity or consistency but don't significantly impact functionality or user success.

**Criteria:**
- Minor formatting inconsistencies (heading levels off by one, inconsistent bullet styles)
- Wordiness or opportunities for clearer phrasing
- Missing optional sections (FAQs, Related Resources, Additional Examples)
- Small style improvements that don't affect comprehension

**Examples:**
- Minor inconsistency: Some sections use numbered lists, others use bullets for similar content
- A paragraph that could be reworded for clarity but is still understandable
- Missing a "Related Resources" section

##### **💡 SUGGESTION** - Optional Enhancements

Non-critical improvements that could enhance the quickstart but aren't necessary for publication.

**Criteria:**
- Style preferences beyond Red Hat standards
- Additional examples that would be helpful but aren't required
- Future enhancements or ideas for the next version
- Alternative approaches or recommendations

**Examples:**
- "Consider adding a diagram showing the architecture"
- "Could include an advanced configuration example for power users"
- "Might benefit from a video walkthrough"

#### Classification decision rules

When uncertain which severity level to assign, use these decision rules:

1. **Default to lower severity:** If torn between two levels, choose the less severe classification
2. **Security and deployment first:** 
   - Does it expose credentials or secrets? → **Blocker**
   - Does it prevent successful deployment? → **Blocker**
   - Everything else is not a blocker
3. **Trademark is always Major:** No matter how many violations, trademark issues are brand compliance, not deployment blockers
4. **User impact test:**
   - Would a user be unable to complete deployment? → **Blocker**
   - Would a user struggle significantly or get confused? → **Major**
   - Would a user notice but still succeed? → **Minor**
   - Is it a "nice to have"? → **Suggestion**

#### Common edge cases

**"The README has 10 trademark violations - isn't that a blocker?"**
- No. Even multiple trademark issues are **Major**. They need fixing for brand compliance, but don't prevent deployment.

**"The installation link works but goes to an outdated version"**
- **Major** if the outdated version still works but causes confusion
- **Blocker** if the outdated version is incompatible or broken

**"There's a typo in a critical command"**
- **Blocker** if the typo breaks the command (e.g., `kubectl get pods` misspelled as `kubctl get pods`)
- **Major** if the typo is in explanatory text but command is correct
- **Minor** if it's in supplementary documentation

**"The README is missing a Troubleshooting section"**
- **Major** for complex deployments where users will likely encounter issues
- **Minor** for simple deployments with few failure modes

---
## The Publishing Process

### Prerequisites 

1. quickstart repository is in the [AI quickstart GitHub organization](https://github.com/rh-ai-quickstart)
2. quickstart meets [repository requirements](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/blob/main/CONTRIBUTING.md#what-are-the-repository-requirements)

### Submit for publication

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

### The review process

After you submit a PR, your quickstart goes through a two-stage review process:

#### 1. Automated review

An AI-powered review automatically checks your README against the [README Quality Standards](#readme-quality-standards) defined above.

**What it checks:**
- All required sections are present
- Trademark usage follows the "first mention only" rule
- No hardcoded credentials or security issues
- Links are working and accessible
- Instructions are clear and complete
- Follows Red Hat style and branding guidelines
- Character limits are respected (title <64 chars, short description <160 chars)

**What you receive:**
- A PR comment with categorized findings (Blocker/Major/Minor/Suggestion)
- Summary count of issues by severity
- Detailed descriptions with specific locations and suggested fixes
- References to which guidelines were violated

#### 2. Manual review

The `publication-admin` team performs a final review for:
- Content accuracy and technical correctness
- Overall quality and polish
- Final approval for publication

**Your responsibility:**
- **Address all Blockers** - These must be fixed before merging
- **Address Major issues** - Strongly recommended before publication
- **Be available** to respond to questions and make updates promptly
- **Ask questions** if any feedback is unclear

The review process ensures consistent quality across all published quickstarts while helping you improve your content.

### Update an existing quickstart
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

