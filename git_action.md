
## Git Action

GitHub Actions is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.

workflows are defined in a YAML file needs to saved on repository's .github/workflows directory.

# Event
An event is a specific activity in a repository that triggers a workflow run. 
list of events are:
- push : Triggers the workflow on push events to the repository.
- pull_request : Triggers the workflow on pull request events. This includes opening, closing, and synchronizing pull requests.
- schedule : Triggers the workflow on a schedule.
- label : Triggers the workflow when a label is added to the repository.
- issue_comment : Triggers the workflow when an issue comment is created, edited, or deleted.
- create : Triggers the workflow when a branch or tag is created.
- delete : Triggers the workflow when a branch or tag is deleted.
- deployment : Triggers the workflow when a deployment is created.

# Jobs
A job is a set of steps that execute on the same runner. By default, a workflow with multiple jobs will run those jobs in parallel. You can configure a job to run sequentially after another job.

# Steps
A step is a set of tasks that execute commands. A step can be either an action or a shell command.

# Actions
Actions are standalone commands that are combined into steps to create a job. Actions are the smallest portable building block of a workflow. You can create your own actions, and use and customize actions shared by the GitHub community.

#Runner
A runner is a server that runs a job. You can use a GitHub-hosted runner, or you can host your own runner. github-hosted runners are virtual machines that are hosted by GitHub and run in a container-based environment. linux, windows and macos are the three types of github-hosted runners.

# Workflow
A workflow is a file that defines a collection of jobs and the rules that execute those jobs. 

// This is the name of your workflow, it can be anything you like -->
name: 

// This specifies when the workflow(EVENT) should be run -->
on: 
    // The workflow will run when there's a push to the main branch
    push:
        branches:
        - main
    // The workflow will also run when a pull request is made to the main branch
    pull_request:
        branches:
        - main

// Jobs are a set of steps that execute on the same runner
jobs:
    // You can name the job anything you like
    build:
        // This specifies the type of runner that the job will run on
        runs-on: ubuntu-latest
        // Steps are a sequence of tasks that will be executed as part of the job
        steps:
            // This is a placeholder for an action, replace it with the action you want to use
            - uses: xxxxxxxxxxxxxxxx@xx
            // This step sets up Python 3.8 using the setup-python action
            - name: Set up Python 3.8
                uses: actions/setup-python@v2
                with:
                    python-version: 3.8
            // This step checks out your repository's code onto the runner using the checkout action
            - name: Checkout code
                uses: actions/checkout@v2























