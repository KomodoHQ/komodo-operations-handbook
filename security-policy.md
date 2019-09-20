# Security Policy

Security is of paramount importance here at Komodo, and we expect you to follow the details within this document to the best of your ability. 

## Password Policy

We employ [LastPass](https://lastpass.com/?ac=1&lpnorefresh=1) in the business to create and store passwords. 

If you are [registering for any accounts](#where-is), either on behalf of the business (e.g. such as a new tool or service) or yourself for business function (such as JIRA) we expect you to generate a random password from LastPass. This password should also be stored in LastPass.

If the password you are creating is related to a project, rather than yourself, ensure to store it as part of the `Shared-Projects` group in LastPass. If you dont have access to the group, contact a member of management for access.

## Two-Factor Everywhere

Please ensure that **for every account you employ related to the business, you add two-factor authentication**. Our recommended app is Google Authenticator ([for iOS](https://apps.apple.com/us/app/google-authenticator/id388497605) / [for Android](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=en_GB)).

2FA will be randomly checked and if you're found to be lacking somewhere, expect a strongly worded slack message.

## Machine Security and Installed Applications

On you're first day you will be asked to set a new password for your office Mac. Please ensure that once set, you create a LastPass shared note with `ian@komododigital.co.uk` including your Mac Password. This is necessary in case we require emergency access to your Mac.

>If at any point you update your Mac login password, ensure to share the updated one with management.

Use reasonable judgement when installing software on your Mac. We expect only applications relevant to your role and reasonable for office use should be installed. If you're wondering where the line is, Spotify is fine, but Steam is not. 

If in doubt, talk to management.

## SSH Keys

Please ensure that your private and public SSH keys are in LastPass as a secure note, again shared with `ian@komododigital.co.uk`. If you have a password for them, ensure to include the password on the note. This is necessary in case access to servers / services is needed in an emergency and your Mac is unavailable.

If you need help with how to setup an SSH Key, follow GitHubs guide at [https://help.github.com/en/enterprise/2.15/user/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent](https://help.github.com/en/enterprise/2.15/user/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

## Sharing Credentials (internal & external)

The only acceptable method of digitally directly sharing credentials with clients / customers is via a LastPass secure note. If you are unsure how to create one, shout up in the office and someone will give you a hand.

Internally, shared credentials should be in the relevant project folder for that project in LastPass.

You may share credentials quickly via Slack internally, provided you immediately delete the message upon succesfully receipt from the recipient.

If the above options are not available, the only other acceptable method is verbally, via telephone.

## Physical Security, Off Premises & Remote, VPN

Be smart when it comes to your person. Some key points:

 - It is wholly unacceptable to have credentials or passwords written down on paper.
 - If your phone is lost or stolen, and has any business related materials and / or 2FA accounts, please report this immediately to the business so we may take the appropriate action.
 - If you suspect any data breach, please report it immediately.

As a business, we do allow for remote working. Generally, we require this activity be taken using company hardware. 

>There are exceptions to this - if required please talk to management. 

When taking office equipment off premises, such as laptops, please pay special attention to the security and safety of the environment around you - this is especially true when working on sensitive projects.

**Upon leaving the business, you are required to delete any and all business related data from personal equipment and ensure that office equipment has none of your personal data.**

The company does have an account with a VPN provider. When working off site, on an unsecured connection (such as on the train) you are expected to use this VPN to secure your traffic. Contact management for access details.

# Project / Code Security

Any project related credentials should be stored in LastPass and **never, ever committed into GIT**. If you discover credentials have been added to GIT by accident, please report this immediately so we can take the appropriate action to revoke the security credentials.

This includes, but is not limited to:

 - Passwords
 - API Keys
 - SSH Keys

Further to this, database copies / backups and log files should also **never, ever committed into GIT**.

# WiFi, Mobile Devices & Guests

Personal devices and non-company hardware is forbidden from access to the `Komodo Internal` WiFi network. Please connect these to the `Komodo Guest` network, the details of which are in LastPass. Only office hardware should be connected to the `Komodo Internal` network.

>There are exceptions to this - if required please talk to management. 

Guests in the business may only be invited onto the `Komodo Guest` wifi.
 
![Stay Safe!](https://media1.giphy.com/media/10NPdN6z9vTYWI/giphy.gif?cid=790b761106092607fbe460f87b32b5b306647c48518e3716&rid=giphy.gif)
