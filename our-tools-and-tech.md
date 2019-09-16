# Our Tools and Tech!
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

>The only exception to the standard Git Flow strategy that we make is that we usually omit `release` branches to save on complexity. 

Essentialy, you have 4 branch types:

 - `master`: should always be releaseable, and is used for "production".
 - `develop`: where new developments are integrated and tested together. 
 - `feature`: where a new feature is developed, in isolation. Must be branched from `develop` and integrated back to `develop`.
 - `hotfix`: used sparingly - where a fix for a problem must be made as fast as possible to `master` - bypassing `develop`.

All `feature` branches should be [pull requested](https://help.github.com/en/articles/about-pull-requests) and if possible, peer reviewed (whereby developers sit together and discuss / reason about / review the created code), before being integrated into `develop`. If the quality of what has been created is not acceptable, ensure you comment on the PR with suitable explanations as to how to improve it. 

### Good Quality Readmes

- Git Flow - Branch Strategy
- Readme
- One command Startup (ideally!)
   - Up to date seed data
- Tests
- Migrationd
- Debugging
  - Sentry
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