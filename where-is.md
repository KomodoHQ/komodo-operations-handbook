# Where Is?

>Audience: Developers, QA, Management
## Email? Gmail.

You should already have an email address setup for your account, which (unless you are told otherwise) will be in the format:

_\(firstname).\(lastname)@komododigital.co.uk_

>Login to Gmail at **[https://mail.google.com/mail](https://mail.google.com/mail)**.

## Project Documents? Google Drive.

Project documents belong in Google Drive, which your Gmail user account will give you access to.

All project documents should be in a shared folder for that project, administered by the PM / AM / Project Lead.

>Login to Google Drive at **[https://drive.google.com/drive/](https://drive.google.com/drive/)**.

## Work / Project Tasks? JIRA.

You should have an invite in your inbox to JIRA, if not contact a PM. 

All project tasks should be in JIRA, unless otherwise stated (there are some exceptions on a per-customer basis). 

Each project should have a JIRA board, with a backlog of work and an active sprint with tasks.

>Login to JIRA at **[https://komodohq.atlassian.net](komodohq.atlassian.net)**.

## Code? GitHub or BitBucket.

All our code is placed in GIT source control. 

For any new projects we create, we put them on GitHub. (More detail on new projects can be found in [New Project Setup](#NewProjectSetup). Ensure that your GitHub account is part of the KomodoHQ GitHub organisation - talk to the Dev Team Lead to get added if you are not a member.

>Login to GitHub at **[https://github.com/](https://github.com/)**.

For most existing / legacy projects, they are housed on BitBucket. You should have an invite to BitBucket, but if not contact the Dev Team Leader, and request to be added to the relevant projects you are working on.

>Login to BitBucket at **[https://bitbucket.org/dashboard/overview](https://bitbucket.org/dashboard/overview)**.
 
## Database + Code Backups? Dropbox or S3

Depending on the project context, backups usually reside in either Amazon S3 or Dropbox.

All maintenance projects (traditionally WordPress) have DB backups triggered on a CRON that regularly runs and exports to the `backups@komododigital.co.uk` account. Please ensure if you are creating a new project in a similar context, this convention is continued.

>Login to Dropbox at **[https://www.dropbox.com/login](https://www.dropbox.com/login)**.

Certain projects have backups exported to Amazon S3 (for example, the College of Policing Professional Profiles Portal). Configuration of these is on an ad-hoc basis.

>Login to Amazon AWS Console at **[https://console.aws.amazon.com/](https://console.aws.amazon.com/)**.


## Passwords, SSH Keys, Development Certificates, Secure Credentials? Bitwarden.

All secure credentials should be stored in Bitwarden. For project related credentials, ensure they are placed within a shared folder for that project.

Items that absolutely should be stored in Bitwarden (and NOT ANYWHERE ELSE) include:

 - Passwords
 - SSH Keys (private and public)
 - Development Certificates (e.g. iOS Distribution Certificates)
 - User accounts
 - API Keys

>Login to Bitwarden at **[https://vault.bitwarden.com/#/login](https://vault.bitwarden.com/#/login)**

## Time Tracking? Float.

Generally, your time on projects needs to be recorded. This is done on Float, which you can log into using your Google Apps / Gmail account. If you are not sure where to track your time, please contact an AM / PM.

>Login to Float at **[https://komodo.float.com/login](https://komodo.float.com/login)**

## Booking Holiday / HR? Mincoffs.

For HR related tasks, such as booking holiday, we use Mincoffs. You can also check your current holiday allocation and get staff personal details.

>Login to Mincoffs at **[https://mincoffs.xyhr.uk/Login.aspx](https://mincoffs.xyhr.uk/Login.aspx)**

## Hosting? Linode, AWS or Azure.

Project hosting is usually agreed as part of the proposal for the project. Generally, smaller projects are hosted on Linode, whilst bigger projects are stored on Amazon AWS. For some projects, the customer has requested to host on Microsoft Azure.

>Login to Linode at **[https://login.linode.com/login](https://login.linode.com/login)**

>Login to Amazon AWS Console at **[https://console.aws.amazon.com/](https://console.aws.amazon.com/)**.

>Login to Microsoft Azure at **[https://azure.microsoft.com/en-gb/](https://azure.microsoft.com/en-gb/)**

## CI / CD? Codeship, Jenkins or CircleCI.

CI / CD tends to be very project specific. Generally though, simple CI / CD processes (for example the Komodo Website build process) is on Codeship. For newer CI / CD processes, we use CircleCI.

For older, more complicated CI / CD processes, we use Jenkins (for example StreetStream), which _tends to be hosted with the platform_. See project documentation for links to this.

>Login to Codeship at **[https://app.codeship.com/sessions/new](https://app.codeship.com/sessions/new)**

>Login to CircleCI at **[https://circleci.com/](https://circleci.com/)**

## App Test Builds / CI? Microsoft App Center.

iOS and Android builds and over the air distribution is done via Microsoft App Center.

>Login to App Center at **[https://appcenter.ms/apps](https://appcenter.ms/apps)**

## Push Notifications? Firebase.

Generally, apps send push notifications via Google Firebase. 

>Login to Google Firebase at **[https://firebase.google.com/](https://firebase.google.com/)**

## Debugging? Sentry.

In application crash / bug reporting and tracking should be integrated with Sentry.

>Login to Sentry at **[https://sentry.io](https://sentry.io)**

![Lost?](https://media2.giphy.com/media/hEc4k5pN17GZq/giphy.gif)


