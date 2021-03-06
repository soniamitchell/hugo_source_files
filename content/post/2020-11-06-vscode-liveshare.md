---
title: Live Share in Visual Studio Code
subtitle: Collaboration made easy
date: 2020-11-06
tags: ["Visual Studio Code", "Live Share", "collaborative tools"]
---

The Visual Studio Code (VS Code) Live Share extension provides a great way to collaborate on code whilst working from home. Assuming read/write access is enabled, you and your team mates can edit code, highlight sections of it, save it, and run it in real-time.

Just bear in mind that when code is run, it is run locally, which means you won't have access to any objects that aren't in your own environment or datasets that aren't on your own machine. On the plus side, you don't have to go into the office and you can access code remotely using your own personalised setup and tools.

## Step 0 - Before you begin

We're assuming you already have [Visual Studio Code](https://code.visualstudio.com) installed  (Note: this is not the same as the Visual Studio IDE) on your machine.. and that you already have an account on [GitHub](https://github.com).
## Step 1 - Download the extension

Now, open up VS Code and install the "Live Share" Microsoft extension from the VS Code marketplace.

![0](/vscode_liveshare/1_extension2.png)

While you're there, if you're intending to work in R, you may as well install:
* the "R" Yuki Ueda extension and 
* the "R LSP Client" REditorSupport extension.
## Step 2 - Share a session

To create a new session, click on "Live Share" in the status bar (at the bottom of the VS Code window). The first time you do this, you'll be prompted to sign in. Selecting "Sign in with GitHub" will open a link in your browser.

![1](/vscode_liveshare/2_signin2.png)

"Authorize VisualStudioLiveShare" and accept ALL OF THE THINGS...

![2](/vscode_liveshare/3_authorize2.png)

You'll know you're logged when your name appears in the status bar to the left of the Live Share icon.

![3](/vscode_liveshare/4_bottom2.png)

At this point an invite link should be copied to your clipboard, which you can share with your team mates.

To create a new invite link, do any of the these things:

* Click on Live Share in the status bar
* Click on your name in the status bar and select "InviteOthers (Copy Link)"
* Click on the "Live Share" icon in the side bar to open a Live Share panel, and select "Share (Read/Write)"

![4](/vscode_liveshare/5_panel2.png)

Once you've collaborated with someone they'll be added to your contacts and if they're online you can invite them directly by clicking on the "Invite Contact" icon next to their name.

![5](/vscode_liveshare/6_contacts2.png)

To end the session, do one of the following:

* Click on your name in the status bar and "Stop Collaboration Session"
* Select the "Stop collaboration session" icon in the Live Share panel

More info [here](https://docs.microsoft.com/en-us/visualstudio/liveshare/use/vscode).
