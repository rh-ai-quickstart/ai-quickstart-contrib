# Welcome to the publisher's guide! :book: 

This page describes publishing a quickstart in the [AI catalog](https://docs.redhat.com/en/learn/ai-quickstarts) on redhat.com. 


## The process

### 1. Prerequisites 

1. quickstart repository is in the [AI quickstart GitHub organization](https://github.com/rh-ai-quickstart)
2. quickstart meets [repository requirements](https://github.com/rh-ai-quickstart/ai-quickstart-contrib/blob/main/CONTRIBUTING.md#what-are-the-repository-requirements)

### 2. Publish

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


### 3. Update an existing quickstart
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

