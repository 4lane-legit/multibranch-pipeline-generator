# multibranch-pipeline-generator
Job DSL code that generates multi branch pipeline for any repo you want.

## Why do we need this?
So in any organizations in the advet of microservices and microfrontends too many new repos pop into existence everyday, 
if you have a jenkins then it becomes tough to create too many multibrach pipelines for companies where there is a single CICD Admin.

This is a very useful utility that allows even non admins to register projects for Multibranch pipelines.

## How to use this?
The Jenkinsfile in the root directory is just what you need to check, 
go to the jobs/multibranch_build.groovy and 

First things first, make sure you create a 0th mutibranch job manually that runs this script. So that everytime you commit to this repo, the new Multibranch projects gets picked by 0th job.

```
String stashUrl = 'your awesomegit account' // Edit this with your git account name, it also supports organizations.
String stashUser = 'jenkins' // jenkins user that talks with your github account.

def gitStuff =   [
  [project: '', url: stashUrl, user: stashUser, repo:  'your-awesome-project' ]
  //add any number of projects here.
]; // register any number of new projects.

```

### How this works?
The code registers a new multiranch pipeline by defaut allowed to clone nested submodules, however this can be turned off.
The code for now doesnt support webhooks and uses traditional SCM polling, by default every second, but this can be replaced easiy with webhooks. use this for reference:
https://jenkinsci.github.io/job-dsl-plugin/

# Version Info: RELEASE-1.0.0
 
