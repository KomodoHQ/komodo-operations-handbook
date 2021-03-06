# Starting a New Project!

>Audience: Developers, Management

So you're going to start a greenfield project? Enjoy! This document should help you get going - highlighting some of the various elements that you should consider, and proposing some technologies for you to look at that are established within the company today.

A good companion to this document is a summary of [Our Tools and Tech](our-tools-and-tech.md).

>**Note:** The elements discussed in here are purely informational. Please research and exercise your best judgement in selecting the most appropriate tool for the job and discuss that with the wider Komodo team. Also, please remember this document may be out of date and newer solutions may exist to your problem.

## Approach

### Requirements Gathering

The very first thing you should do when approaching a new project is to make sure you are fully briefed on the functional and non-functional requirements for that project. In other words, your first action should be to thoroughly read the proposal document. 

Upon reviewing the proposal:

 - Make a list of potential assumptions that the proposal has made, that you would like asserted and agreed.
 - Make a list of questions that have arisen from reading the proposal – let’s get those unknowns answered.
 - Make a list of potential risks that the project may be subject to, and identify suitable remedies or de-risking solutions.

Once you clearly understand the requirements and have cleared up the unknowns, it’s time to start looking at technology and strategy. The proposal may well already assert the underlying technology you're expected to use (e.g. PHP or Node), or it may leave it up to you to make a sensible choice. It may also be clear about libraries or frameworks (e.g. WordPress or Laravel), or it may not specify.

>**Remember:** Always read the proposal before making any technology decisions!

### Research and Plan Of Action

Working in collaboration with the project team, start researching possible solutions to your problem ensuring you consider any functional and non-functional requirements when making assessments of appropriateness for use. Create a document detailing research you've undertaken, and a plan of action (POA) for what your solution will look like.

Your POA should include:

 - Who you will need support from, by when, and in relation to what. (e.g. We will require content for the "about us" page from customer by 10th December).
 - Details of technology choice (e.g. PHP, Node, React etc), and sensible justification for use. (e.g. We are planning to leverage PHP as it is open source, has a collection of libraries that will speed up development, and has a proven support structure).
 - Top level frameworks / libraries you intend to employ to address requirements (e.g. We will use the PHPStripe stripe library to support Stripe payments in the application).
 - General application architecture, with supporting diagrams to illustrate technical elements and key interactions.
 - How you will handle testing. What testing frameworks will be put in place? What will be tested? What kind of test coverage are we going for? What needs to be manually tested vs what will be automated?
 - Hosting solution, including plans for immediate setup of a staging environment. How will you roll out and provision infrastructure? Is a third party responsible? How will it be maintained and updated?
 - What third party integrations are there? (e.g. email services such as [Mailgun](https://www.mailgun.com/), payment services such as [Stripe](https://stripe.com/gb), Push Notifications services such as [Firebase](https://firebase.google.com))
 - What project documentation is needed? Where will it be stored?
 - What measures of code quality control will be placed upon the project?
 - How will the project utilise CI/CD process?
 - Who in the project will take responsibility for each aspect?
 - How will you measure success on the project? Are there any relevant technical KPI’s?
 - Any outstanding known unknowns or questions for follow up.

### Technical Setup

Your number one goal with the technical setup phase of the project should be to ensure that it is easy to onboard and offboard development team members onto the project, whilst maintaining as high as possible development output and quality. 

To achieve this, you should prioritise:

 - Creating a robust development environment that can be [started using a one line command](our-tools-and-tech.md). The environment should be consistent across developers host machines, and where possible strive to mirror the production configuration. As such, we generally recommend utilising [Docker](https://www.docker.com/) or [Vagrant](https://www.vagrantup.com/) to package up your application, together with its host dependencies, in a deployable container. 
 - Setting up the testing process that works locally, within your environment (i.e. _NOT_ on your host machine). This may be running commands like `phpunit` or similar.
 - Setting up and provisioning a staging server so that you can immediately test and demonstrate what is being developed, independently of your local environment.
 - Setting up a CI/CD process that glues the above elements together in an automated fashion.
 - Creating suitable documentation to explain all of the above, including how to use / interact with each element.
   
   >**Note:** Your CI/CD process should only invoke functionality you can run from a development machine. We should always be able to build, test and deploy from development machines, as well as automatically via CI/CD.

### Functionality Delivery

Once the above has been completed, you should be in a position to commence work on the project, delivering features and functionality, whilst rotating team members as and when required. On most projects, this looks like iterating on the project in two-week agile sprints, but speak to the project manager to understand and validate delivery approach.

## Where Does the Code Belong?

Unless otherwise instructed, code should be placed under GIT source control and stored in a GitHub repository. Some notes:

 - Check who is retaining ownership of the code. This should be in the proposal or validated clearly afterwards as part of the POA. 
 - Give the repository a relevant name.
 - Ensure that the correct team members have access to the project - simply add the `All The Devs` group to the project on GitHub.
 - Make sure there is a project `README.md`, and that it is **KEPT UP-TO-DATE** with setup instructions.
 - Ensure the `README.md` describes the deployment process.
 - Ideally, ensure the project has very few, or even just 1 step to get up and running - e.g. `npm start`.
 - **Do not place sensitive content / credentials inside source control.** Avoid:
   - User accounts
   - Passwords
   - API Keys
   - SSH Keys
   - Database Backups
 - Avoid storing large files in GIT - doing this will really slow stuff down. E.g. Don’t place Sketch / PSD’s in the repo.

## Helpful Starter Technology

Whilst every project is different, below is a generic list of technology elements that have been used in the past at Komodo which may be helpful for your project. These elements are grouped by their top-level technology approach.

### PHP - WordPress

The [Roots](https://roots.io/) collection of tools - [Sage](https://roots.io/sage/), [Bedrock](https://roots.io/bedrock/) and [Trellis](https://roots.io/trellis/) provide the foundations for a robust, scaleable and modern WordPress based solution. Whilst you do not have to use all of the elements, working together they are fantastic for most Greenfield projects that we are in control of. From project structure, to infrastructure provisioning to theme development, they follow industry best practice and are very well documented. Use them.

### PHP - Laravel

We have our [own Laravel Bootstrap](https://github.com/KomodoHQ/docker-laravel) which could be a reasonable starter point. 

Also, checkout [Backpack for Laravel](https://backpackforlaravel.com) which is great and speedy for admin panel / CRUD type stuff.

We also have some [scripts to help provision Linode servers]() for PHP / MySQL stacks of this nature.

> @TODO: Add these to our github.

### Node - Express / API

[PM2](http://pm2.keymetrics.io/) is a fantastic tool for doing process monitoring, enabling you to keep an express server running indefinitely.

> @TODO: Create / Recommend a good boilerplate here

### Node - Command Line

[Commander](https://github.com/tj/commander.js/) is a great library to help build command line interfaces in Node.

[Inquirer](https://github.com/SBoudrias/Inquirer.js) helps with the above, allowing a TTY type interface for questions and answers that perform actions. 

> @TODO: Create / Recommend a good boilerplate here

### React

[Create React App](https://github.com/facebook/create-react-app) is the de facto bootstrap for building React web applications.

[Gatsby](https://github.com/gatsbyjs/gatsby) is a framework for building React static web-apps / sites, sourcing content from a variety of locations.

### React Native

[Ignite](https://github.com/infinitered/ignite) is a CLI to help construct React Native projects, including common elements needed for most apps from state management to debugging tools.

---

![Do, or do not!](https://media1.giphy.com/media/26FmQ6EOvLxp6cWyY/giphy.gif?cid=790b7611688c332e7405796f33d21238f991d32df2cefeae&rid=giphy.gif)