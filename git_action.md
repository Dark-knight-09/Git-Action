
## Git Action

GitHub Actions is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.

workflows are defined in a YAML file needs to saved on repository's .github/workflows directory.

# Event
An event is a specific activity in a repository that triggers a workflow run. 
list of events are:
- push : Triggers the workflow on push events to the repository.
    - branches : The branches on which you want to run the workflow. 

- pull_request : Triggers the workflow on pull request events. This includes opening, closing, and synchronizing pull requests.
    - branches : The branches on which you want to run the workflow. 
    - types : The types of pull requests on which you want to run the workflow. 

- schedule : Triggers the workflow on a schedule.
     - cron : The cron syntax for the schedule. For example, `0 0 * * 0` runs the workflow every Sunday at 00:00.
- label : Triggers the workflow when a label is added to the repository.
- issue_comment : Triggers the workflow when an issue comment is created, edited, or deleted.
     - types : The types of issue comments on which you want to run the workflow. 
    
- create : Triggers the workflow when a branch or tag is created.
- delete : Triggers the workflow when a branch or tag is deleted.
- deployment : Triggers the workflow when a deployment is created.

- issue : Triggers the workflow when an issue 
    - types:  The types of issues on which you want to run the workflow.

# Jobs
A job is a set of steps that execute on the same runner. By default, a workflow with multiple jobs will run those jobs in parallel. You can configure a job to run sequentially after another job.

Job: 
- runs-on: The type of operating system that the job will run on. 
- needs: The jobs that must complete successfully before this job will run. (depend-on)
- if: The expression that determines whether to run the job or not.


# Steps
A step is a set of tasks that execute commands. A step can be either an action or a shell command.


# Actions
Actions are standalone commands that are combined into steps to create a job. Actions are the smallest portable building block of a workflow. You can create your own actions, and use and customize actions shared by the GitHub community.

Action:
- uses: The name of the action to run. You can use uses to specify the action to run in the step.
- with: The input parameters for the action. You can use with to pass input parameters to an action.
- env: The environment variables that are available to the action. You can use env to set environment variables for an action.


# Runner
A runner is a server that runs a job. You can use a GitHub-hosted runner, or you can host your own runner. github-hosted runners are virtual machines that are hosted by GitHub and run in a container-based environment. linux, windows and macos are the three types of github-hosted runners.

to run shell command:
- shell: the shell name( bash, pwsh, python, sh, cmd, powershell)
- run: command to run
- env: the environment variables that are available to the action.

# Workflow
A workflow is a file that defines a collection of jobs and the rules that execute those jobs. 

#This is the name of your workflow, it can be anything you like -->
name: 

#This specifies when the workflow(EVENT) should be run -->
on: 
    #The workflow will run when there's a push to the main branch
    push:
        branches:
        - main
    #The workflow will also run when a pull request is made to the main branch
    pull_request:
        branches:
        - main

#Jobs are a set of steps that execute on the same runner
jobs:
    #You can name the job anything you like
    build:
        #This specifies the type of runner that the job will run on
        runs-on: ubuntu-latest
        #Steps are a sequence of tasks that will be executed as part of the job
        steps:
            #This is a placeholder for an action, replace it with the action you want to use
            - uses: xxxxxxxxxxxxxxxx@xx
            #This step sets up Python 3.8 using the setup-python action
            - name: Set up Python 3.8
              uses: actions/setup-python@v2
              with: python-version: 3.8
            #This step checks out your repository's code onto the runner using the checkout action
            - name: Checkout code
              uses: actions/checkout@v2

























