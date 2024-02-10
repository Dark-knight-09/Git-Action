
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
























