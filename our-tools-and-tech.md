# Our Tools, Tech and Process!
---

We employ a diverse set of tools and technologies at Komodo, so before we go any further please remember the following:

 - _Talk to the project lead before employing a new technology on an existing project_
 - _Talk to the development team, the DTL and review the proposal before making technology decisions about a new project_
 - _This list of tools & tech may well be out of date - if you're unsure - ask the team!_

## Common

Some elements that exist on every project are detailed here. Please follow these conventions.

### Git, Git Flow and Pull Requests / Peer Review

At Komodo, just about all our projects use Git for source control (theres some super legacy mercurial, but nothing from the last 5 years). Please use Git everywhere! 

For greenfield projects, please create the project on [GitHub](https://github.com/). Most existing projects are on [Bitbucket](https://bitbucket.org/dashboard/overview) - we may consider migrating the active ones to GitHub next year, but for now, please carry on using BitBucket for these.

All projects follow the [**Git Flow** branching strategy](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). You are expected to follow this when working on new functionality and features. 

>The only exception to the standard Git Flow strategy that we make is that we usually omit `release` branches to save on complexity. Check your project to see if we are using `release` branches or not.

Essentialy, you have 4 branch types:

 - `master`: should always be releaseable, and is used for "production".
 - `develop`: where new developments are integrated and tested together. 
 - `feature`: where a new feature is developed, in isolation. Must be branched from `develop` and integrated back to `develop`.
 - `hotfix`: used sparingly - where a fix for a problem must be made as fast as possible to `master` - bypassing `develop`.

All `feature` branches should be [pull requested](https://help.github.com/en/articles/about-pull-requests) and if possible, peer reviewed (whereby developers sit together and discuss / reason about / review the created code), before being integrated into `develop`. If the quality of what has been created is not acceptable, ensure you comment on the PR with suitable explanations as to how to improve it. 

### README.md

There should be enough information in every projects `README.md` to get started with development quickly, and without needing support.

It is **critical** that all PRs which merge to `develop` should be evaluated for their impact on getting the project up and running from scratch, and **making sure the `README.md` is up to date** with any changes.

As per [this highly rated README template](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2) contents of the `README.md` should include:

 - Project Title
 - Project Summary
 - Getting Started
   - Prerequisites
   - Installing
 - Running the tests
 - Deployment
 - Built With

>If you're in doubt about whether to place a note in the `README.md`, add it. Better to have and not need, then need and not have ;-).

### Docs

In addition to the `README.md`, its great to see a `docs` folder with any relevant technical notes or discussions about the project. Some examples what might exist in the `docs` folder include:

 - A reference / backround to the project - including links to proposal, designs etc
 - A summary of the technology choices made on the project, and their reasoning
 - Infastructure and architecture summaries + diagrams
 - Any relevant development / testing processes
 - Any tips for working on the project
 - Troubleshooting help

### One Line Startup

Ideally, you should be able to start development on a project with a single line terminal command, such as:

 - `npm start` 
 - `yarn start`
 - `./start.sh`
 - etc...

This command should do everything required to go from nothing to a working development environment, ready to start coding, with the only assumption being that you have checked out the project repository to your local machine. Examples of tasks this command should do include:

 - Provision and boot an environment
 - Install all relevant OS, system and application dependancies
 - Setup a development database, and a test database if required
 - Seed some up to date test data if needed
 - Setup a `watcher` to ensure code changes are refreshed automatically

>Sometimes, its simply not possible to achieve this in one command, especially in environment variables must be configured, but please try to keep startup steps to an absolute minimum.


### Environments, Configuration and Feature Flags

Wherever possible, try to ensure that your development environment, QA environment, and any other environments mirror your production environment. Ideally, there should be a one to one parity between all environments, such that they are exactly the same, except for configuration options and database content. This is the best way to ensure that the code you create will behave consistantly for end users as it did during testing.

Use `ENV` variables, housed in `.env` files, to configure your environments. **Never commit these into the project repo**. If necessary, include a `.example.env` in the project repository with sensible development environment variables setup for people to get going. 

Where relevant, use [feature flags](https://en.wikipedia.org/wiki/Feature_toggle) to enable or disable functionality within an environment with relative ease. This is especially useful in gating unfinished developments in code, allowing you to keep releaseing quickly, even with unfinished functionality.

### Tests

It's expected that any greenfield project should have suitable test frameworks in place from commencement, with standards agreed between the team to detail what is in scope for testing, how it will be tested, and what measures of quality will be enforced for testing on the project.

Some existing projects have tests, others do not (particularly inherited or legacy projects). Where possible, please try to always improve on the code you receive - adding tests for functionality you create, even if none existed before. If you're unsure here, talk to the project lead and DTL to determine a sensible way forward. 

Where possible, ensure there is a test `watcher` on your project, so that as code and tests are updated, all tests are rerun to verify continued functionality.

>It is reasonable that tests might not be included on your project, due to time, complexity or relevancy. Confirm with the project team.

### Database, Database Migrations and Access To Live Data

You're expected to ensure that any changes to the database structure or content that are not transient, MUST be made through the use of [database migrations](https://en.wikipedia.org/wiki/Schema_migration). Generally at Komodo, for PHP projects, we leverage [Laravel's Migrations](https://laravel.com/docs/5.8/migrations) or [Symfony's Migrations](https://symfony.com/doc/master/bundles/DoctrineMigrationsBundle/index.html). For JavaScript projects, check out [Knex](http://knexjs.org/#migrations).

Database schema should be reasonable and justifiably thought out, considering [normalization](https://en.wikipedia.org/wiki/Database_normalization) whilst also understanding the performance impacts of your decisions and [de-normalizing](https://en.wikipedia.org/wiki/Database_normalization) as appropriate. Work with your team, considering what you're querying, how often, and how much as part of your database design.

On a growing number of projects today, it is impossible to get access to production data. As such, consider the implications of design decisions, logging and changes when building your database.

### Debugging, Linting and Code Quality

The days of relying solely on `print_r` or `console.log` debub statements are long gone. In addition to these statements, it's perfectly possible to setup breakpoints and additional introspection in your environment, using [Xdebug for PHP](https://xdebug.org/), the [Node Debugger](https://nodejs.org/api/debugger.html), [React Dev Tools](https://reactjs.org/blog/2019/08/15/new-react-devtools.html) or [Reactotron](https://github.com/infinitered/reactotron) to name but a few.

Wherever possible, add [Sentry](https://sentry.io) to your project so that exceptions are caught and reported to Sentry. It's also suggested you read the [Sentry Documentation](https://docs.sentry.io/) to make the most of what it can add to your debugging toolset.

Beyond these tools, we can help ourselves minimise on errors in the project, by ensuring we have relevant automated help. Linters, such as [ESLint](https://eslint.org/) for JavaScript or [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer) for PHP can detect and automatically fix stylistic problems in code that might result in errors. [Test watchers](https://continuousdelivery.com/foundations/test-automation/) can continuously scan the project for changes in code and test, rerunning your tests on change to ensure functionality is maintained.

### Bug Reporting



- Bug reporting template
- Deployment
- Monitoring

Tech and People

- Mac OS
  - Brew

- PHP 
  - Laravel
  - WordPress

- JS
  - Node
  - React
  - React Native


![Happy Coding!](https://media3.giphy.com/media/25JgMcsSndyuBkoaV2/giphy.gif?cid=790b761139f168c40b5c6e116cde7367d7f39d7195b8cab6&rid=giphy.gif)