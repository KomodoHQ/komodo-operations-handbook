# Starting a New Project!

So you're going to start a greenfield project? Enjoy! This document should help you get going - highlighting some of the various elements that you should consider, and proposing some technologies for you to look at that are established within the company today.

A good companion to this document is a summary of [Our Tools and Tech](our-tools-and-tech.md).

>**Note:** The elements discussed in here are purely informational. Please research and exercise your best judgement in selecting the most appropriate tool for the job, and discuss that with the wider Komodo team. Also, please remember this document may be out of date and newer solutions may exist to your problem!.

## Approach

### Requirements Gathering

The very first thing you should do when approaching a new project, is to make sure you are fully briefed on the functional and non-functional requirements for that project. In order words, your first action should be to thoroughly read the proposal document. 

Upon reviewing the proposal:

 - Make a list of potential assumptions that the proposal has made, that you would like asserted and agreed.
 - Make a list of questions that have arised from reading the proposal - lets get those unknowns answered.
 - Make a list of potential risks that the project may be subject to, and identify suitable remedies or de-risking solutions.

Once you clearly understand the requirements and have cleared up the unknowns, its time to start looking at technology and strategy. The proposal may well already assert the underlying technology you're expected to use (e.g. PHP or Node), or it may leave it up to you to make a sensible choice. It may also be clear about libraries or frameworks (e.g. WordPress or Laravel), or it may not specify.

>**Remember:** Always read the proposal before making any technology decisions!

### Research and Plan Of Action

Working in collaboration with the project team, start researching possible solutions to your problem, ensuring you consider any functional and non-functional requirements when making assessments of appropriateness for use. Create a document detailing research you've undertaken, and a plan of action (POA) for what you're solution will look like.

Your POA should include:

 - Who you will need support from, and by when, and in relation to what. (e.g. We will require content for the "about us" page from customer by 10th December).
 - Details of technology choice (e.g. PHP, Node, React etc), and sensible justification for use. (e.g. We are planning to leverage PHP as it is open source, and has a collection of libraries that will speed up development, and has a proven support structure).
 - Top level frameworks / libraries you intend to employ to address requirements (e.g. We will use the PHPStripe stripe library to support Stripe payments in the applicatoin).
 - General application architecture - with supporting diagrams to illustrate technical elements and key interactions.
 - How you will handle testing? What testing frameworks will be put in place? What will be tested? What kind of test coverage are we going for? What needs to be manually tested vs what will be automated?
 - Hosting solution, including plans for immediate setup a staging environment? How will you roll out and provision infrastructure? Is a third party responsbile? How will it be maintained and updated?
 - What third party integrations are there? (e.g. email services such as [Mailgun](https://www.mailgun.com/), payment services such as [Stripe](https://stripe.com/gb), Push Notifications services such as [Firebase](https://firebase.google.com))
 - What project documentation is needed? Where will it be stored?
 - What measures of code quality control will be placed upon the project?
 - How will the project utilise CI/CD process?
 - Who in the project will take responsbility for what aspects?
 - How will you measure success on the project? Are there any relevant technical KPIS?
 - Any outstanding known unknowns or questions for follow up.

### Technical Setup

You're number one goal with the technical setup phase of the project, should be to ensure that it is easy to onboard and offboard development team members onto the project, whilst maintaining as high as possible development throughput and quality. 

To achieve this, you should prioritise:

 - Creating a robust development environment, that can be [started using a one line command](our-tools-and-tech.md). The environment should be consistent across developers host machines, and where possible strive to mirror the production configuration. As such, we generally recommend utilising [Docker](https://www.docker.com/) or [Vagrant](https://www.vagrantup.com/) to package up your application, together with its host dependancies, in a deployable container. 
 - Setting up the testing process that works locally, within your environment (i.e. _NOT_ on your host machine). This may be running commands like `phpunit` or similar.
 - Setting up and provisioning a staging server, so you can immediately test and demonstrate what is being developed, independantly of your local environment.
 - Setting up a CI/CD process, that glues the above elements together, in an automated fashion.
 - Creating suitable documentation to explain all of the above, including how to use / interact with each element.
   
   >**Note:** Your CI/CD process should only invoke functionality you can run from a development machine. We should always be able to build, test and deploy from development machines, as well as automatically via CI/CD.

### Functionality Delivery

Once the above has been completed, you should be in a position to commence work on the project, delivering features and functionality, whilst rotating team members as and when required. On most projects, this looks like iterating on the project in two-week agile sprints, but speak to the project manager to understand and validate delivery approach.

## Where Does The Code Belong?

Unless otherwise instructed, code should be placed under GIT source control, and stored in a GitHub repository. Some notes:

 - Check who is retaining ownership of the code. This should be in the proposal or validated clearly afterwards as part of the POA. 
 - Give the repository a relevant name.
 - Ensure that the correct team members have access to the project - simply add the `All The Devs` group to the project on GitHub.
 - Make sure there is a project `README.md`, and that it is **KEPT UP TO DATE** with setup instructions.
 - Ensure the `README.md` describes the deployment process.
 - Ideally, ensure the project has very few, or even just 1 step to get up and running - e.g. `npm start`.
 - **Do not place sensistive content / credentials inside source control.** Avoid:
   - User accounts
   - Passwords
   - API Keys
   - SSH Keys
   - Database Backups
 - Avoid storing large files in GIT - doing this will really slow stuff down. E.g. Dont place Sketch / PSDs in the repo.

## Helpful Technology

Whilst every project is different, below is a generic list of technology elements that have been used in the past at Komodo, and may be helpful for your project. These elements are grouped by their top level technology approach.

### PHP - WordPress

### PHP - Laravel

### Node - Express / API

### Node - Command Line

### React

### React Native

### Infrastructure and Hosting