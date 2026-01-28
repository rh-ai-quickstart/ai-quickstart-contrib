# The (eventually) complete user guide to AI quickstarts! :raised_hands: 

This *user guide* is an effort 
to put everything you'll need to know about AI quickstarts in one place. It
exists to make sure you're successful with AI quickstarts. 

AI quickstart creators may want to start with the 
[contributor's guide](CONTRIBUTING.md)
instead.

## Table of contents
* [General AI quickstart information](#general-ai-quickstart-information)
* [Getting started](#getting-started)
* [Getting help, submitting feedback and making requests](#getting-help-submitting-feedback-and-making-requests)

## General AI quickstart information 

### AI quickstarts definition 

Quickstarts are simple, ready-to-use AI examples using Red Hat platforms. 
They are straightforward and focused example use cases - easy to launch, easy to
get, and *ready to go!*

Quickstarts exist because some of us learn by doing and want evidence, proof, or
to simply get started as quickly as possible. **If that sounds like you, you're
in the right place.** Please continue reading!

### "Logistics" 

AI quickstarts are collected in the 
[AI quickstarts GitHub Organization](https://github.com/rh-ai-quickstart). 
Each repository is a quickstart making it easy for you to get started. 

Red Hatters, our partners and community members create and maintain AI
quickstarts for anyone to use in their Red Hat AI platform. Each quickstart is
stored as a repository in the 
[AI quickstarts GitHub Organization](https://github.com/rh-ai-quickstart). 
Organizing quickstarts this way makes them easier to maintain long term. 

Every repository is an AI quickstart with a few notable exceptions: 
* [The .github repository](https://github.com/rh-ai-quickstart/.github) - is the landing page for AI quickstarts. You can safely ignore it.
* [ai-quickstart-template](https://github.com/rh-ai-quickstart/ai-quickstart-template) - is a template repository for creators to get started easily.
* [ai-quickstart-contrib](https://github.com/rh-ai-quickstart/ai-quickstart-contrib) - is where we document, manage projects and plans, and interact with the community through Github issues, for example. This is where you get help if you need it. 


## Getting started

### Deployment tool prerequisistes 

The tools you need depend on the quickstart you want to deploy. Each quickstart
will document the specific tools needed. 

But, consider installing these commonly used tools beforehand to save yourself time. 

| Useful Tool | Description | Link to instructions | 
| --- | --- | --- | 
| `git` | Easily clone (download) AI quickstarts before deployment | [Installing git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) | 
| `oc` | Tool makes it easy to connect to OpenShift and deploy quickstarts | [OpenShift CLI (oc)](https://docs.redhat.com/en/documentation/openshift_container_platform/4.8/html/cli_tools/openshift-cli-oc#cli-getting-started) | 
| `helm` | Package manager for kubernetes | [Helm CLI](https://docs.redhat.com/en/documentation/openshift_container_platform/4.3/html/cli_tools/helm-cli#getting-started-with-helm-on-openshift-container-platform)  | 
| `make` | Automates builds and tasks | Included in \*nix environments use package managers or trusted installation instructions for Windows environments | 

These tools are useful to have especially when you're deploying from a local
terminal. Alternatively, your cluster administrator could install the 
[OpenShift Web Terminal operator (4.16)](https://docs.redhat.com/en/documentation/openshift_container_platform/4.16/html/web_console/web-terminal#installing-web-terminal)
to deploy examples directly from OpenShift. 

Remember, create an 
[issue](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/issues)
 if you would like help or updates to this documentation. 


### Deploy your first quickstart! :rocket: 

Launch a private chatbot using the 
[LLM CPU Serving quickstart](https://github.com/rh-ai-quickstart/llm-cpu-serving). 

**Here's what you'll need to do:**
1. Read through the [README](https://github.com/rh-ai-quickstart/llm-cpu-serving)
2. Follow directions in the "[Install](https://github.com/rh-ai-quickstart/llm-cpu-serving?tab=readme-ov-file#install)" section 
3. Launch the chatbot

*Simple & ready to go!* 


## Getting help, submitting feedback and making requests 

All feedback and suggestions are welcome. Specific and actionable feedback is
preferred. Please create a GitHub issue directly in the quickstart repository 
whenever possible.

For general feedback, please create an
[issue in ai-quickstart-contrib](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/issues)
. General requests may resemble: 
* General help requests 
* Suggesting a new AI quickstarts 
* General feedback

If you're **ever unsure** where to submit a request, just submit an "issue" in the 
[ai-quickstart-contrib repository](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/issues).

### Here's how to submit a request. 
1. Navigate to [ai-quickstart-contrib](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/tree/main)
2. Select "[Issues](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/issues)"
3. Click the green "New issue" button, top right 

![rh-ai-quickstart-contrib-issues.png](docs/images/rh-ai-quickstart-contrib-issues.png)

4. Pick an appropriate issue type 

![rh-ai-quickstart-contrib-new-issue.png](docs/images/rh-ai-quickstart-contrib-new-issue.png)

### GitHub membership

To join the AI quickstart Github organization, please use the **Membership request** option 
when creating your request. Membership allows you to create AI quickstart 
repositories for others to use.

### Other 

**Quickstart suggestion** can be used to suggest a new quickstart. Please note, all
suggestions are welcome but there are no guarantees we'll be able to build it! 


Use "Blank issue" for all other requests, feedback or anything else on your
mind.
