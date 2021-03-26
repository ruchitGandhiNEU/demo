# Seer
Seer monorepo

## Services
- Projects - Responsible for projects management
- Variables - Responsible for integrating with preprocessor, variables selection
- Automodeler - Responsible for integration with automodeler and providing results
- Notifications - Responsible for communicating results of long running tasks to UI application
- UI - Seer UI application

### Pre-Requirement

- Latest `Node.js` is installed. https://nodejs.org/en/download/
- Latest `yarn` is installed https://classic.yarnpkg.com/en/docs/install/
- Latest `lerna` is installed with `npm i -g lerna`

### Local Development

Execute the following command to install dependencies:
```sh
$ lerna bootstrap
```

Put `.env` files into root of respective services (ask your collegues about those files)

Execute the following command to run watch-and-build:
```sh
$ lerna run dev --parallel
```
This command will start all services in watch-rebuild mode.

To run specific service or services use `--scope` flag
e.g. Run projects and variable services
```sh
lerna run dev --parallel --scope=@seer/projects --scope=@seer/variables
```

Note: Projects service performs authorization functionality (verify user access to certain project)

## Branching strategy
Please follow Gitflow workflow
The detils can be found here
https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

### Branch naming
- Use `feat/{JIRA-TICKET-ID}-something-brief` for feature branches: User stories, tasks
- Use `fix/{JIRA-TICKET-ID}-something-brief` bor bugfixes
- Use `hotfix/{JIRA-TICKET-ID}-something-brief` for production defects resolved by Hotfix flow

