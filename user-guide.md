# The (eventually) complete user guide to AI kickstarts! :raised_hands: 

Some of this content you'll find in other places too. This is an effort 
to put everything you'll need to know about AI kickstarts in one place, and 
is most useful to practitioners - **Red Hat AI users** & **OpenShfit cluster 
administrators**. AI kickstart creators may want to start with the 
[contributor's guide](CONTRIBUTING.md). 

## Table of contents
* [General AI kickstart information](#general-ai-kickstart-information)


## General AI kickstart information 

### AI kickstarts definition 

Kickstarts are simple, ready-to-use AI examples using Red Hat platforms. 
They are straightforward and focused example use cases - easy to launch, easy to
get, and *ready to go!*

### "Logistics" 

AI kickstarts are collected here in the 
[AI kickstarts GitHub Organization](https://github.com/rh-ai-kickstart). 
Each repository is a kickstart making it easy for you to get started.

Red Hatters, our partners and community members create and maintain AI
kickstarts for anyone to use in their Red Hat AI platform. Each kickstart is
stored as a repository in the 
[AI kickstarts GitHub Organization](https://github.com/rh-ai-kickstart). 
Organizing kickstarts this way makes them easier to maintain long term. 

Every repository is an AI kickstart with a few notable exceptions: 
* [The .github repository](https://github.com/rh-ai-kickstart/.github)
* [ai-kickstart-template](https://github.com/rh-ai-kickstart/ai-kickstart-template)
* [ai-kickstart-contrib](https://github.com/rh-ai-kickstart/ai-kickstart-contrib)

**.github** is the landing page for the AI kickstart Organization. You can
safely ignore it.

**ai-kickstart-template** is a template repository for creators to get started
easily. It contains a sample README file, preferred directory structures and
helper functions. 

**ai-kickstart-contrib** serves to document the project, manage projects and
plans, and interact with the community through Github issues, for example. This
is where you can get help, if you need it. More on that below. 


### Getting help, submitting feedback and making requests 

All feedback is welcome. Specific and actionable feedback is preferred. Please
create a GitHub issue directly in the kickstart repository whenever possible.

For general feedback, please create an
[issue in ai-kickstart-contrib](https://github.com/rh-ai-kickstart/ai-kickstart-contrib/issues)
. General requests may resemble: 
* General help requests 
* Requests for new AI kickstarts 
* General feedback

If you're **ever unsure** where to submit a request, just submit an "issue" in the 
[ai-kickstart-contrib repository](https://github.com/rh-ai-kickstart/ai-kickstart-contrib/issues).

Here's how to submit a general request. 

#### 1. Navigate to
[ai-kickstart-contrib](https://github.com/rh-ai-kickstart/ai-kickstart-contrib/tree/main)

#### 2. Select "Issues" 

Or, [go straight there](https://github.com/rh-ai-kickstart/ai-kickstart-contrib/issues)

#### 3. Click the green "New issue" button, top right 

![rh-ai-kickstart-contrib-issues.png](assets/images/rh-ai-kickstart-contrib-issues.png)

#### 4. Pick an appropriate issue type 

![rh-ai-kickstart-contrib-new-issue.png](assets/images/rh-ai-kickstart-contrib-new-issue.png)

You can use "Blank issue

DRAFT outline - things to document, but haven't yet - 
GENERAL 
* why should i care 
	some people learn by doing 
	some people want to see it in action, for inspiration about the product, or
what they could be doing with it going forward  
	some people want proof 
* what about LICENSE files
* OK, now the how 
* the README file tells you everything you need to know and how to install it
* detail the recommended contents of the README files 
	* Some come with arcades in case you just want to see the kickstart without installing or don't have RH AI 
* requirements vary by use case, by contributor, by software version 
* we will documentat what's required 
* sometimes assumptions are made. If you have trouble with a kickstart, create a GH issue 
* how can you install these 
	* local machine with terminal 
	* openshift web terminal
* here are some tools you'll need. won't need them every time but nice to have 
	* git
	* oc
	* helm 
	* make 
* what if you don't have them? generalized install instructions 
	* linux
	* mac
	* windows
	* openshift 
* environments
	* openshift
	* openshift ai
* if you don't have them you can always do the arcades
* Let's install a simple example using: 
	* local 
		* open terminal
		* you have oc already 
		* log in 
		* git clone vllm-cpu 
		* helm install 
	* openshift web terminal 
		* click terminal 
		* git clone
		* helm install 

