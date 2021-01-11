# Our Tools, Tech and Process!

>Audience: Developers, QA, Management

We employ a diverse set of tools and technologies at Komodo, so before we go any further please remember the following:

 - _Talk to the project lead before employing a new technology on an existing project_
 - _Talk to the development team, the DTL and review the proposal before making technology decisions about a new project_
 - _This list of tools & tech may well be out of date - if you're unsure - ask the team!_

## Your Mac

If at all possible, we recommend using [Homebrew](https://brew.sh/) to install, update and maintain applications on your Mac. Homebrew gives much finer control over which applications are installed on your machine, the versions, and when they are updated. It is also more straightforward than hunting the internet for how to update an app.

Generally, we would expect some of the following to be installed on your Mac, as relevant to your project:

 - IDE / Code editors - such as [PHPStorm](https://www.jetbrains.com/phpstorm/), [Visual Studio](https://visualstudio.microsoft.com/vs/mac/), [Visual Studio Code](https://code.visualstudio.com/), [Atom](https://atom.io/), [XCode](https://developer.apple.com/xcode/) etc.
 - Browsers - such as [Chrome](https://www.google.com/chrome/), [Firefox](https://www.mozilla.org/en-GB/firefox/new/), [Safari](https://www.apple.com/uk/safari/), [MS Edge](https://www.microsoft.com/en-gb/windows/microsoft-edge) etc.
 - Team comms - [Slack](https://slack.com/intl/en-gb/) 
 - Database browsers - such as [Sequel Pro](https://www.sequelpro.com/), [DBeaver](https://dbeaver.io/), [Robo3T](https://robomongo.org/) etc.
 - GIT browser - such as [SourceTree](https://www.sourcetreeapp.com/)
 - Dev Environment Tools - such as [Docker For Mac](https://docs.docker.com/docker-for-mac/install/), [Vagrant](https://www.vagrantup.com/), [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

>The above list is far from exhaustive, but is more an indication of what is sensible. Apps like [Spotify](https://www.spotify.com/uk/) are also fine. None of the above are _required_, they are simply suggestions.

**As outlined in the [Security Policy](#security-policy) - please exercise reasonable due diligence when installing software on your Mac.**

## Project Development

Some elements that exist on every project are detailed here. Please follow these conventions.

### Git, Git Flow and Pull Requests / Peer Review

At Komodo, just about all of our projects use Git for source control (there's some super legacy Mercurial, but nothing from the last 5 years). Please use Git everywhere! 

For Greenfield projects, please create the project on [GitHub](https://github.com/). Most existing projects are on [Bitbucket](https://bitbucket.org/dashboard/overview) - we may consider migrating the active ones to GitHub next year but for now, please carry on using BitBucket for these.

All projects follow the [**Git Flow** branching strategy](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). You are expected to follow this when working on new functionality and features. 

>The only exception to the standard Git Flow strategy that we make is that we usually omit `release` branches to save on complexity. Check your project to see if we are using `release` branches or not.

Essentially, you have 4 branch types:

 - `master`: should always be releasable and is used for "production".
 - `develop`: where new developments are integrated and tested together. 
 - `feature`: where a new feature is developed, in isolation. Must be branched from `develop` and integrated back to `develop`.
 - `hotfix`: used sparingly - where a fix for a problem must be made as fast as possible to `master` - bypassing `develop`.

All `feature` branches should be [pull requested](https://help.github.com/en/articles/about-pull-requests) and if possible, peer reviewed (whereby developers sit together and discuss / reason about / review the created code), before being integrated into `develop`. If you have questions, suggestions, or potential improvements to the created code, please comment on the PR with suitable explanations as to how to revise it. It is very important to ensure and maintain code quality on a project.

### README.md

There should be enough information in every project’s `README.md` to get started with development quickly, and without any support.

It is **critical** that all PRs which merge to `develop` should be evaluated for their impact on getting the project up and running from scratch, and **making sure the `README.md` is up to date** with any changes.

As per [this highly rated README template],(https://gist.github.com/PurpleBooth/109311bb0361f32d87a2) contents of the `README.md` should include:

 - Project Title
 - Project Summary
 - Getting Started
   - Prerequisites
   - Installing
 - Running the tests
 - Deployment
 - Built With

>If you're in doubt about whether to place a note in the `README.md`, add it. Better to have and not need, than need and not have ;-).

### Docs

In addition to the `README.md`, it’s great to see a `docs` folder with any relevant technical notes or discussions about the project. Some examples of what might exist in the `docs` folder include:

 - A reference / background to the project - including links to the proposal, designs etc
 - A summary of the technology choices made on the project, and their reasoning
 - Infrastructure and architecture summaries and diagrams
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
 - Install all relevant OS, system and application dependencies
 - Setup a development database, and a test database if required
 - Seed some up-to-date test data if needed
 - Setup a `watcher` to ensure code changes are refreshed automatically

>Sometimes it’s simply not possible to achieve this in one command, especially in environments where variables must be configured, but please try to keep startup steps to an absolute minimum.


### Environments, Configuration and Feature Flags

Wherever possible, try to ensure that your development environment, QA environment, and any other environments mirror your production environment. Ideally, there should be a one-to-one parity between all environments so that they are exactly the same, except for configuration options and database content. This is the best way to ensure that the code you create will behave as consistently for end users as it did during testing.

Use `ENV` variables, housed in `.env` files to configure your environments. **Never commit these into the project repo**. If necessary, include a `.example.env` in the project repository with sensible development environment variables setup for people to get going. 

Where relevant, use [feature flags](https://en.wikipedia.org/wiki/Feature_toggle) to enable or disable functionality within an environment with relative ease. This is especially useful in gating unfinished developments in code, allowing you to keep releasing quickly even with unfinished functionality.

### Database, Database Migrations and Access to Live Data

You're expected to ensure that any changes to the database structure or content that are not transient, MUST be made through the use of [database migrations](https://en.wikipedia.org/wiki/Schema_migration). Generally at Komodo for PHP projects, we leverage [Laravel's Migrations](https://laravel.com/docs/5.8/migrations) or [Symfony's Migrations](https://symfony.com/doc/master/bundles/DoctrineMigrationsBundle/index.html). For JavaScript projects, check out [Knex](http://knexjs.org/#migrations).

Database schema should be reasonable and justifiably thought out, considering [normalization](https://en.wikipedia.org/wiki/Database_normalization) whilst also understanding the performance impacts of your decisions and [de-normalizing](https://en.wikipedia.org/wiki/Database_normalization) as appropriate. Work with your team, considering what you're querying, how often, and how much as part of your database design.

On a growing number of projects today, it is impossible to get access to production data. As such, consider the implications of design decisions, logging and changes when building your database.

### Debugging, Manual Testing, Linting and Code Quality

The days of relying solely on `print_r` or `console.log` debug statements are long gone. In addition to these statements, it's perfectly possible to setup breakpoints and additional introspection in your environment using [Xdebug for PHP](https://xdebug.org/), the [Node Debugger](https://nodejs.org/api/debugger.html), [React Dev Tools](https://reactjs.org/blog/2019/08/15/new-react-devtools.html) or [Reactotron](https://github.com/infinitered/reactotron) to name but a few.

Wherever possible, add [Sentry](https://sentry.io) to your project so that exceptions are caught and reported to Sentry. It's also suggested you read the [Sentry Documentation](https://docs.sentry.io/) to make the most of what it can add to your debugging toolset.

Beyond these tools, we can help ourselves minimise on errors in the project by ensuring we have relevant automated help. Linters, such as [ESLint](https://eslint.org/) for JavaScript or [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer) for PHP can detect and automatically fix stylistic problems in code that might result in errors. [Test watchers](https://continuousdelivery.com/foundations/test-automation/) can continuously scan the project for changes in code and test, re-running your tests on change to ensure functionality is maintained. Static Analysis tools such as [PHPStan](https://github.com/phpstan/phpstan) can also help identify issues early.

We have a device library in the office, with a range of mobile and tablet devices to test websites and applications on. Beyond this we have a [Browserstack](https://www.browserstack.com/) account, enabling testing across a vast array of virtual devices and browsers. Its use is strongly encouraged as part of manual testing and QA.

Whilst not strictly a debugging tool, [BrowserSync](https://www.browsersync.io/) is a fantastic project that enables you to develop on projects and test across all browsers in a "synchronised" fashion. It has an array of features from network throttling to file synchronisation and is relatively straightforward to add to projects.

### Automated Tests

It's expected that any Greenfield project should have suitable test frameworks in place from commencement, with standards agreed between the team to detail what is in scope for testing, how it will be tested, and what measures of quality will be enforced for testing on the project.

Some existing projects have tests, others do not (particularly inherited or legacy projects). Where possible, please try to always improve on the code you receive - adding tests for functionality you create, even if none existed before. If you're unsure here, talk to the project lead and DTL to determine a sensible way forward. 

Where possible, ensure there is a test `watcher` on your project, so that as code and tests are updated, all tests are re-run to verify continued functionality.

>It is reasonable that tests might not be included on your project due to time, complexity or relevancy. Confirm with the project team.

### Bug Reporting

This is a topic in and of itself so if you need to report a bug, [read the bug reporting docs](#bug-reporting).

### CI, CD and Deployment

[CI](https://en.wikipedia.org/wiki/Continuous_integration) and [CD](https://en.wikipedia.org/wiki/Continuous_delivery) are setup for just about every recent project we have worked on, and are expected to be configured for new Greenfield projects. These tools support you in ensuring that what you create is well tested, maintains its functionality, and is deployed in a timely manner. At Komodo, the services we have used for this are:

 - [CodeShip](https://codeship.com/) for lighter, more straightforward CI + CD
 - [Jenkins](https://jenkins.io/) for heavier, more complex CI + CD
 - [CircleCI](https://circleci.com/) for a specific project, being considered for more extensive use on future projects
 - [Microsoft App Center](https://appcenter.ms/apps) for mobile projects

In general CI / CD should be configured to:

 - Build / Compile the project and verify its integrity
 - Run tests to ensure continued functionality
 - Lint the project to maintain code quality
 - Automatically deploy the project (where relevant)
 - Notify developers of issues with the project and its build, tests or deployment

### Monitoring

Once deployed, we should ensure reasonable monitoring systems are in place to ensure continued availability. Responsibility for _who_ is monitoring the system is assumed to be the customer, unless we agree to provide this as part of an SLA agreement / maintenance agreement. 

_What_ is monitored will vary from project to project. Check with the PM / AM, the customer, and the rest of the development team when setting up monitoring. [Uptime Robot](https://uptimerobot.com/) is a free solution we employ that you can use for website / web app uptime monitoring and notifications. [Sentry](https://sentry.io) will also send us exception reports from production environments when configured to do so. [Microsoft App Center](https://appcenter.ms/apps) can also be configured to capture mobile app crash reports.

## Technologies and Company Experts

In general, the company has three primary technology approaches, with their various supporting technology stacks employed across our projects. Within the team, there are experts that should be able to help you out when working with these stacks. 

This is by no means an exhaustive list, but rather "a good place to start". Read the relevant tool / framework documentation online to understand its latest incantation, and ensure to talk to the senior team when making significant technical decisions.

### PHP Lead Web

PHP is one of our ongoing primary web languages in the business. `Scott Salisbury` is a senior PHP developer and the best person to consult when it comes to PHP considerations on projects. 

We strive to employ the latest versions of PHP, but some legacy projects go back all the way to using PHP 5.4.

Generally, PHP projects will come in one of 3 variants.

#### Laravel
[Laravel](https://laravel.com/) is our preferred PHP stack for most projects. It's straightforward, well supported, scalable, and has a good library of tools, components and libraries to aid in development.

#### Symfony
[Symfony](https://symfony.com/) is used on one specific project. It's powerful and fast, but complicated. 

#### WordPress
[WordPress](https://en-gb.wordpress.org/) is the world’s most widely used CMS. We tend to treat it as a necessary evil, appropriate for some projects. Checkout `Sage`, `Bedrock` and `Trellis` by [Roots](https://roots.io/) as they will **REALLY** help you in getting started and creating a secure, maintainable and well structured site.

### JavaScript Lead Web

JavaScript is the other primary web language in the business. `Chris Neale`, `Jess Kelsall` and `Drew Miley` tend to lead JavaScript projects on the web. 
 
#### Node JS

Used on the back end, [Node](https://nodejs.org/en/) comes in all shapes and sizes. Every node project is different, so make sure to consult extensively with the senior JS devs before making radical technical decisions.
 
#### React

[React](https://reactjs.org/) is our primary frontend framework, used across a number of projects.

### Mobile

Generally, all mobile work done at the company comes under the purview of `Mike Flowers`. There are 3 different variants.

#### React Native

Most Greenfield mobile applications are developed with [React Native](https://facebook.github.io/react-native/), enabling a wide array of team members to work on the project.

#### Xamarin C#

We continue to support some existing C# based [Xamarin](https://dotnet.microsoft.com/apps/xamarin) projects, though we do not anticipate any Greenfield projects using this technology in future.

#### Objective-C

There is only one project currently being "supported" for [Objective-C](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/Introduction/Introduction.html), and it's not anticipated for any new projects to be written in this language.

---

![Happy Coding!](https://media3.giphy.com/media/25JgMcsSndyuBkoaV2/giphy.gif?cid=790b761139f168c40b5c6e116cde7367d7f39d7195b8cab6&rid=giphy.gif)

