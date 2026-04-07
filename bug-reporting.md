# Bug Reporting

>Audience: Developers, QA, Management

Whether it’s an internal bug report made by a developer or QA team member, or it’s an external bug report made by a client, a good bug report can make the difference between an hour worth of development work or a day worth.

In general, the following template should suffice for reporting a bug.

---

# Summary Title of Issue

## Expected Behaviour
> This should explain what the feature / element is "intended" to do, as understood by the bug reporter.

## Current Behaviour
> This should explain what the feature / element is "currently" doing in its buggy state, as understood by the bug reporter.

## Possible Solution (if applicable)
> If the person reporting the bug is able to, can they propose a solution to this?

## Steps to Reproduce
> This should be a clear, descriptive set of steps to reproduce the issue as consistently as possible.

## Context (Environment)

 - Device: XXX
 - Operating System: XXX
 - Browser: XXX
 - URL: XXX
 - Date(s) & Time(s) of when bug occurred: XXX

> This should be the configuration of the environment that was used to reproduce the issue.

## Additional Details

> Any additional points of note, such as how frequently the bug occurs or potential factors that may have introduced the issue.

## Screenshots / Videos

> Links to screenshots / videos that demonstrate the issue.

## Severity

> This should explain the severity of an issue using the below severity definitions. 
- **Blocker** - Not only is the issue Critical, but it prevents other defects from being resolved, and new functionality and feature development.
- **Critical** - The issue affects critical functionality or critical data. It does not have a workaround. *Example: Unsuccessful installation, complete failure of a feature.*
- **Major** - The issue affects major functionality or major data. It has a workaround but is not obvious and is difficult. *Example: A feature is not functional from one module but the task is doable if 10 complicated indirect steps are followed in another module/s.*
- **Minor** - The issue affects minor functionality or non-critical data. It has an easy workaround. *Example: A minor feature that is not functional in one module but the same task is easily doable from another module.*
- **Trivial** - The issue does not affect functionality or data. It does not even need a workaround. It does not impact productivity or efficiency. *Example: Minor layout discrepancies, spelling/grammatical errors.*

---

## Raising feedback in Jira

> General guidance for how feedback should be raised whilst working on KOMODO-managed Jira boards. 
> This guidance may be subject to the project you are working on

Tasks and Stories which are placed in the QA column of a board should contain the completed work towards the user story and acceptance criteria outlined in that ticket, however there may be instances where feedback can be given on that work. A QA team member will use this ticket to plan, design, and direct testing efforts and raise any feedback using **child issues** and **Labels** as shown below: 

- A ticket is progressed through In Progress and Peer Review status before reaching QA column
- Testing is performed on that ticket
- Feedback is raised as child ticket(s) following bug reporting guidance outlined in this page
- For each child ticket...
    - Assign a severity level
    - Assign a label of **QA**
    - Assign a label which indicates the nature of the feedback using the **Feedback Labels** below

Once feedback has been added, it shows good practise to communicate the tickets in a short update in the project channel in Slack. This provides an opportunity for discussion on the feedback and helps to eliminate any non-issues or false-positives, but also prevents feedback from being left unnoticed.

A Project Manager will prioritise the child tickets as required. Child tickets which are prioritised lower may be converted into tasks and placed in the backlog to be addressed at a later date.

After all remaining child tickets have been resolved by the developer and QA team members, the parent ticket will be tested again before being moved to Done. Parent tickets should not be marked as Done until all attached child tickets have been addressed.

## Feedback Labels

> This should explain the use of each label for QA raised feedback

- **Feedback-Bug**: Used when the feedback identifies a functional defect directly related to the parent ticket. These prevent the software from behaving as expected or the code fails to meet acceptance criteria
- **Feedback-Omission**: Used when the feedback identifies an omission from the original scope or requirements but should have been included. These could be missing features, functions, behaviours, etc.
- **Feedback-Enhancement**: Used when the feedback suggests an improvement the scope. These could be accessibility or UX improvements that weren't considered in the scope and would likely be agreed on through Slack discussions or similar
- **Feedback-Performance**: Used when the feedback identifies performance issues, such as a noticeably slow loading page or asset as part of the parent ticket's additions
- **Feedback-Security**: Used when the feedback identifies potential security vulnerabilities or concerns including privacy
- **Feedback-Regression**: Used when the feedback identifies that a previous feature no longer works as intended or a previously fixed issue has reoccurred in a later version

---

If you need a "tailored" bug reporting template, checkout https://github.com/devspace/awesome-github-templates.

![Bug!](http://i.imgur.com/ZjiFJ3D.gif)

