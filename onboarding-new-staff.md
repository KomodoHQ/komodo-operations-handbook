# Onboarding New Staff

>Audience: Management

## Before new team members start

Upon arranging a start date with a new development / qa team member at the company, please ensure to do the following.

1. Add the start date and time as a meeting invite to the calendar of the new team member's manager. 
  - For now, this can be added to Scott Salisbury's calendar. 
  - Book out a 1 hour meeting to provision the laptop
  - Book out a second 1 hour meeting to do introductions and onboarding (including Nicola O'Neill from a HR perspective)
2. Organise delivery of a new Macbook Pro, together with any additional peripherals (keyboard, mouse, monitor, USB adapters etc) to the new team member in advance of their start date.
3. Send an email to the new team member informing them of this hardware's arrival and expected delivery date. 
  - Inform the new team member **they must not turn the machine on** until they have spoken to Scott Salisbury and he has provisioned the machine.
  - Under no circumstances must they change the laptop configuration or install any software until they have spoken to Scott Salisbury.
  - They may unpackaged the laptop and charge it up in advance.
4. Book in a meeting for the new team member's probation review for 3 months from the date of their start.

## On the morning new team members start

Before speaking to the new team member on the morning they start, there are a number of accounts that they must be invited to and that must be setup. These are:

 - Google Apps / Gmail
   - Register them for an email address in the format of `firstname.surname@komododigital.co.uk` at [https://admin.google.com/ac/home](https://admin.google.com/ac/home)
   - Ensure to add their user accounts to the `Office` (aka `Studio`) and `Devs` groups at [https://admin.google.com/ac/groups](https://admin.google.com/ac/groups)
 - Slack
 - JIRA
 - Harvest
 - Mincoffs
 - Bitwarden

## Setting up hardware (Macs)

The process to configure and provision Mac hardware is fairly uniform, only varying a little bit depending on whether you have the hardware in front of you.

### Local account setup

Perform the following steps in order to being the setup process.

1. Turn on the mac.
2. Configure the mac to use UK timezone, UK keyboard etc. Connect to Wifi.
3. Make the first account an Administrator account, using the name Administrator. Set the password to be the password as recorded under the Bitwarden entry called `Office Mac Desktop / Laptop Administrator Password` which is in the shared folder `Shared-MasterAccounts\Komodo Staff\Machines`. 
4. Disable location services, Siri, and do not allow Touch ID to log in.
5. Do not create an Apple account (instead select to skip).
6. Do not enable additional tracking, or sending crash reports to Apple.
7. Log in.
8. Skip to [Provisioning](#).

### Remote access setup

Assuming you are on a phone call with the new team member, instruct the team member to perform the following steps in order to being the setup process.

1. Turn on the mac.
2. Configure the mac to use UK timezone, UK keyboard etc.Connect to Wifi.
3. Allow the team member to register for a user account, which is an Administrator account.
4. Disable location services, Siri. They may choose to enable Touch ID to log in.
5. Do not create an Apple account (instead select to skip).
6. Do not enable additional tracking, or sending crash reports to Apple.
7. Log in.
8. Open Safari, download Google Chrome.
9. In Google Chrome, go to [https://remotedesktop.google.com/support/](https://remotedesktop.google.com/support/).
10. Get the new team member to sign in with their company Google account.
11. Go to "Remote Support" and under "Get Support" download and install the chrome plugin.
12. Generate a support access code, and use this to take remote control of the machine.
13. Skip to [Provisioning](#).

### Provisioning

At this point, you should be logged into the first account added to the Mac, and ready to begin provisioning. Follow the steps below.

1. Create a new entry in the "Resource Hardware List - Office & Remote" Google Sheet for the new Mac.
2. Open the Apple menu (top left - ) and go to "About this Mac"/
3. Copy the serial number for the Mac, and add it to the new line in Google Sheet.
4. Find the name of an X-men character from https://en.wikipedia.org/wiki/List_of_X-Men_members that hasn't been used for another Mac so far in the list.
5. Go to "System Preferences -> Sharing" and name the Mac "<Xmen>'s <Device>" - e.g. "Magneto's Macbook Pro". Regcord it in the Google Sheet.
6. Add either an Administrator account or a User account in "System Preferences -> Users & Groups" - whatever is missing from the Mac depending on setup path taken earlier.
7. Add a new user group in "System Preferences -> Users & Groups" called 'brew-usergroup' and assign both user accounts to it. Hit apply and close.
8. Open a terminal, paste the following command and hit enter to install Homebrew.
  ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"```
9. Install the Xcode command line tools when prompted.
10. Once the above is finished, execute the following commands to ensure app access is shared.
  ```
  sudo dseditgroup -o edit -a $(whoami) -t user brew-usergroup
  sudo chgrp -R brew-usergroup $(brew --prefix)/*
  sudo chmod -R g+rwX $(brew --prefix)/*
  ```
11. Type `brew doctor` and ensure the system is ready to brew.
12. Visit `https://gist.github.com/ianoshorty/cf9174fb7b09fcc145170313e53f7314` and run the commands in the script to install our usual software suite.
13. Go to "System Preferences -> Security & Privacy -> FileVault".
14. Enable FileVault, DO NOT use iCloud but instead generate a recovery key.
15. Store the recovery key as a secure note in Bitwarden under the `Shared-MasterAccounts\Komodo Staff\FileVaults` shared group with the Mac's device name.
16. Apply and lock.
17. If time allows, apply any **SECURITY ONLY* fixes to the mac, but **DO NOT* upgrade it to a newer OS version (e.g dont upgrade Catalina to Big Sur).
18. Ensure that the new hardware's details are fully recorded in the Google Sheet. 
19. Return control to the new team member.

## Onboarding

Once the team member has had their hardware provisioned, the next stage is to go through verbal onboarding. Have a call with the team member, open the [Welcome To Komodo](welcome-to-komodo.md) document walk through the following on a screenshare:

 - Welcome the team member, thank them for joining etc.
 - Verify that basic accounts have been received, and immediately ensure 2FA is setup for Gmail and Slack.
 - Talk through the key team members
   - Directors
     - Andy Greener (MD)
     - Jason Christie (PD)
   - Management
     - Chris Jones (Client Services)
     - Phoebe Dowley (Account Management)
     - Nicola O'Neill (Office Management)
   - Teams & Leads
     - Design
       - Thomas Wood - aka Woody (Senior Designer)
     - Development
       - PHP - Laravel, Symfony, WordPress
         - Scott Salisbury (Head of Web Development)
       - Frontend / JS - React / Node
         - Daniel Carney (Senior Developer)
       - Mobile / React Native
         - Mike Flowers (Senior Developer)
 - Talk about probation, probation rules and restrictions and review policy, expectations.
 - Talk about HR elements, when you're paid, booking holiday etc.
 - Walk through and confirm clear and thorough understanding of the [Security policy](security-policy.md) at Komodo.
 - Talk about business etiquette - things like core business hours, slack status for lunch / away from desk etc.

## Work plan for the new team member

At this point, introduce the team member to the project and give some background and history into the client, what we've done for them, what the project they will be working on is, how far through the project we are etc. Recommend they open a Google doc and start aggregating questions about the project from their onboarding over the next few days.

Then, introduce the team member to the other people working on the project, and ask them to support the team member in onboarding.

## Post onboarding check in

At a suitable time after the team member has been onboarded, check in to see how they are settling in, how things are going, do they need any additional support etc.