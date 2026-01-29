# Welcome to the contributor's guide (FAQ)! :computer: 

Here you'll find details on how to contribute AI quickstarts!

## Table of contents

* [How are quickstarts maintained?](#how-are-quickstarts-maintained)
* [How are AI quickstarts organized?](#how-are-ai-quickstarts-organized)
* [What are the repository requirements?](#what-are-the-repository-requirements)
* [How do I join the GitHub organization?](#how-do-i-join-the-github-organization)
* [How do I create a new quickstart?](#how-do-i-create-a-new-quickstart)
* [Can I bring an existing quickstart into this organization?](#can-i-bring-an-existing-quickstart-into-this-organization)
* [How to publish and promote your quickstart?](#how-to-publish-and-promote-your-quickstart)
* [Can I deploy and share a working example?](#can-i-deploy-and-share-a-working-example)



## How are quickstarts maintained? 

AI quickstarts are maintained by their contributors. Your quickstarts are maintained by
you. We ask for prompt attention to known issues and requests. If necessary
actions are not completed, we may pause the promotion of your AI quickstart on
redhat.com. 

### :warning: STOP 

**REMEMBER:** *AI quickstart contributors are responsible for the maintenance of their quickstarts!*

## How are AI quickstarts organized? 

Every AI quickstart is its own repository. We do this so they are easy to browse,
clone and deploy! AI quickstarts are collected here in the 
[AI quickstart GitHub Organization](https://github.com/rh-ai-quickstart). 

Here's what it looks like: 

```
rh-ai-quickstart/
├── [vllm-cpu]()/
│   ├── README.md 
│   ├── docs/images/
│   └── helm/
└── [vllm-tool-calling]()/
    ├── README.md 
    ├── docs/images/
    └── vllm-tool-calling/
```

## What are the repository requirements? 

### Required

* A descriptive repository name makes your quickstart easy to find and understand 
* `README.md` - use the README structure documented in the [README file specifications](#readme-file-specifications) section
  * [ai-quickstart-template](https://github.com/rh-ai-quickstart/ai-quickstart-template) includes a README in the correct format
* Put the images your README uses in the `docs/images/` folder
* Be as descriptive as possible! REMEMBER: you aren't just documenting code, you're documenting the use case
* Add a description to your repository's About section

### What criteria are we using? 

Here are some examples of best practices and common pitfalls: 

| Best practice or pitfall? | Status |
|---|---|
| deployable by a regular user with regular permissions | :white_check_mark: |
| an appealing user interface | :white_check_mark: | 
| conveying an industry use case solved using Red Hat AI | :white_check_mark: |
| examples only deployable by cluster admins | :x: | 
| focusing only on the technology, not the problem it solves | :x: |
| examples that only deploy a single component without a friendly UI or way to us it | :x: |


IMPORTANT: as mentioned in the 
[How to publish and promote your quickstart](#how-to-publish-and-promote-your-quickstart) section, 
select quickstarts will be featured on redhat.com. This curated set will be selected using this criteria to 
promote actionable use cases. Since they will be highly visible, we will highlight the most relevant 
examples that any one can try and tell a compelling story. 

### README file specifications

README files must follow the same structure for 2 important reasons: 
1. consistency for our user base - quickstarts adhere to the same redhat.com professional standards we are used to
2. content is reused so titles, descriptions and more must meet these criteria 

The table below defines our README file structure, including whether the section is required, the expected order and the criteria each section must meet.

| | Section name | Heading level | is required? | Criteria | 
| --- | --- | --- | --- | --- | 
| 1 | AI quickstart title | H1 | **Required** | * Max character length: **64**<br>* Action focused, begin with **verb** like: Deploy, accelerate, use, boost, etc <br>* Title must be descriptive about the use case, for example "Boost online sales with AI", not "Deploy granite on XYZ version 1.2.3" |
| 2 | Short description | Normal text | **Required** | * Normal text directly underneath the title<br>* No longer than **160 characters**<br>* Describe the use case with a deeper description <br>* Idenitfies what the user will take away from the quickstart, including business benefits, skills or specific applications.| 
| 3 | Table of contents | H2 | Optional, but recommended | * Standard markdown ToC | 
| 4 | Detailed description | H2 | **Required** | * a couple paragraphs describing the use case and solution in detail<br>* This is not a technical deep dive, it's detailed description of the use case and solution approach| 
| 5 | See it in action | H3 | Optional, but recommended | * Opportunity to link to videos or arcades for users without a target environment | 
| 6 | Architecture diagrams | H3 | **Required** | * Put your images in the `docs/images` folder |  
| 7 | Requirements | H2 | **Required** | | 
| 8 | Notes on requirements | Normal text | Optional | * Using normal text, call out anything the user MUST know, if applicable | 
| 9 | Minimum hardware requirements | H3 | **Required** |  * List minimum hardware requirements to deploy your quickstarts<br> * User should have **ZERO** surprises<br>  * Be as specific as possible. Don't just say GPU. Be as specific as possible | 
| 10 | Minimum software requirements | H3 | **Required** | * List minimum requirements, again, no surprises <br> * Be specific. Don't stop at "OpenShift AI". Instead, tested with OpenShift AI 2.22<br> * If it only works with a specific version, *please* say so. | 
| 11 | Deploy | H2 | **Required** | * Instructions to deploy your quickstart<br> * This section is flexible on how it's formatted, be clear and consistent<br>* Be thorough: assume the user will follow instructions *exactly* with limited knowledge<br>* This section should be straightfoward, link to more detailed, or "Advanced Deployment" instructions in a separate section at the bottom of the README |
| 12 | Delete | H3 | **Reqiured** | * Include instructions to remove the quickstart when finished | 
| 13 | Reference | H2 | Optional, but recommended | * Include external links to blogs, supporting information, documentation or learning materials, if needed | 
| 14 | Optional technical section | H2 | Optional | * Space to add more H2 & H3 headings to further explain your quickstarts<br> * Here is where you can have a "Advanced deployment" section, or <br>* "Technical deep dive" or a **"Guided experience"** walking a user through how to use your quickstart | 
| 15 | Tags | H2 | **Required** | * This is a bulleted list following the format **Tag name**: short description <br>* Multiple tags will be supported in the future, but for now: <br>* ONLY use the **Industry**: [INSERT Industry here] tag <br>* More information can be found in the [MIST guidelines](#mist-guidelines) section | 

For a clear example, please see the README file in the [ai-quickstart-template](https://github.com/rh-ai-quickstart/ai-quickstart-template) repository.

Additionally, remember to avoid jargon and follow standard Red Hat corporate style guides. 


## How do I join the GitHub organization?

* Submit a new "Membership request" issue following the process outlined in the [user guide](user-guide.md#getting-help-submitting-feedback-and-making-requests).

## How do I create a new quickstart?

**1. Click "Repositories" in the [AI quickstart org](https://github.com/rh-ai-quickstart)**

![rh-ai-quickstart-repos.png](docs/images/rh-ai-quickstart-repos.png)

**2. Click "New repository" (top right)** 

![rh-ai-quickstart-new-repo.png](docs/images/rh-ai-quickstart-new-repo.png)

**3. Click "No template" and select `rh-ai-quickstart/ai-quickstart-template`**

![rh-ai-quickstart-template.png](docs/images/rh-ai-quickstart-template.png)

**4. Give your repository a name, make it Public and "Create repository" ** 

**5. Build! :rocket:**

**6. P.S. Remember to update *placeholder* text in the template README**

**7. P.P.S Remember to add a description to your repository**

1. Click the gear icon in the top right of your repository

![rh-ai-quickstart-repo-gear.png](docs/images/rh-ai-quickstart-repo-gear.png)

2. Add a short description 

![rh-ai-quickstart-repo-description.png](docs/images/rh-ai-quickstart-repo-description.png)


### Is there a template repository? 

Yes. We got you! 

The `ai-quickstart-template` repository will pre-populate your repository with: 
 
* a README.md file - **NOTE** You'll want to replace the text! 
* `docs/images/` folder to store images supporting your README
* `.github/workflows/` GH Actions to manually submit a PR for publication


### Do I have to create an Arcade? 

You don't *have* to create an Arcade, but it is recommended. Remember: not all
users will have immediate access to an environment when they find your 
quickstart. Arcades let users experience the example even if they aren't ready 
to deploy just yet. 

Don't forget to include a link to the Arcade in your README file. And, if you 
want to go the extra mile, you can export the Arcade as a video and embed it 
in your README. 

Red Hatters can get started by searching `"interactive experiences (Arcade)"` on
the Source.


## Can I bring an existing quickstart into this organization?

Yes! Here are the two most common options for existing rh-ai-quickstart members 
(not a member? [Open an issue to request membership](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/issues)):

### 1) Simple & fast: fork your repository to rh-ai-quickstart

1. In your github Repository, click "Fork" in the upper right corner 
2. Select "rh-ai-quickstart" from the "Choose an owner" dropdown
3. Enter a new repository name if the pre-populated repository name is taken 
4. Click "Create fork" near the bottom when ready
5. Navigate to your new [AI quickstart](https://github.com/orgs/rh-ai-quickstart/repositories) fork and get started


### 2) Transfer ownership to rh-ai-quickstart

#### *Owners* of rh-ai-quickstart with *admin* in the source repo can:  
1. In your Github repository, click "Settings" (top right of the repo)
2. Scroll down to the "Danger Zone" 
3. Click the "Transfer" in the "Transfer ownership" section
4. Make sure "Select one of my organizations" is selected and select "rh-ai-quickstart" from the dropdown
5. Update the repository name, if needed 
6. Type the confirmation and select "I understand, transfer this repository" when ready
7. Navigate to your [AI quickstart](https://github.com/orgs/rh-ai-quickstart/repositories) and get started

#### If you have *admin* in the source repo but are not an *owner* of rh-ai-quickstart, you can: 
1. Make an owner of `rh-ai-quickstart` an *admin* in the source repository
2. Request they transfer ownership on your behalf 


## How to publish and promote your quickstart?

Your AI quickstart is discoverable once you push commits to 
[github.com/rh-ai-quickstart](https://github.com/rh-ai-quickstart). 
While many users will browse GitHub, we will curate an AI quickstart catalog on 
redhat.com. [PUBLISHING.md](PUBLISHING.md) describes our publication process. 


## Can I deploy and share a working example? 

Yes, the AI BU runs an OpenShift AI cluster for any Red Hatter to use. You can
deploy your example and share it internally. Reach out using internal channels
for help. 


## Tag your quickstart

Red Hat's Metadata Initiative for Structured Taxonomy (MIST) group provides 
guidance on tagging content destined for redhat.com. Effective tagging helps
Red Hatters, customers and partners find the content they need. 

Before publishing on redhat.com, each quickstart will need: ([summarized from the Source](https://source.redhat.com/departments/marketing/marketing_content_team/marketing_content_team_wiki/how_to_write_compelling_metadata_and_choose_taxonomy_tags_for_redhatcom_webpages))
* compelling, search engine-friendly:
  * titles 
  * descriptions
  * and metadata
* taxonomy tags to make content findable and usable 


### MIST guidelines

*NOTE: Red Hat's technical writers will assist with this content* 

*Section below describes the tags MIST recommends. A few notes:
* Tag list may be incomplete for quickstart use case
* Some tags may be prepopulated while others marked optional
* Will provide instructions on where to update tags when available*


Tags: 
| is_required? | Tag | Example | 
| --- | --- | --- |
| required | Industry | Retail |
| required, if applicable | Partners | Intel |
| required | Product | OpenShift AI (put the "featured" RH product) |
| optional | Use case | Productivity |
| optional | Product line | AI | 
| optional | Business challenge | efficiency | 
| optional | Region | EMEA |
| optional | Resource type | quickstart |
| optional | Services | |
| optional | Sub Type | |
| optional | Topic | |

<!-- what about other metadata? last edit, publish date? authors? -->


<!--  Comment this block out until decision made on where and how to update tags

### How to update tags

Help us keep things organized by tagging your quickstart repo. 
1. Go to your repository
2. Click the gear in the About section (top right)
3. Add relevant topic information
4. Include a tag for your team too, see [list of tags](#list-of-tags) below

### List of tags

* `rh-ai-bu`
* `rh-ai-bu-cai`
* `rh-ai-engineering`
* `rh-ecosystem-engineering`
* `rh-ai-ssa`
* `rh-consulting`
* `customer`
* `partner`
* `community`
-->
