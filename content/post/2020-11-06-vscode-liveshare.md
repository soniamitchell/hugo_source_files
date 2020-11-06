+++
author = "Sonia Mitchell"
title = "Live Share in Visual Studio Code"
date = "2020-11-06"
description = "How to set up Live Share in Visual Studio Code"
tags = [
    "Visual Studio Code",
    "Live Share",
    "Collaborative tools",
]
categories = [
    "Visual Studio Code",
    "Collaborative tools",
]
series = ["Visual Studio Code"]
+++

## Step 1 - Download the extension

Install the "Live Share" Microsoft extension from the VS Code marketplace.

![0](/vscode_liveshare/1_extension.png)

## Step 2 - Share a session

To create a new session, click on "Live Share" in the status bar (at the bottom of the VS Code window). The first time you do this, you'll be prompted to sign in. Selecting "Sign in with GitHub" will open a link in your browser.

![1](/vscode_liveshare/2_signin.png)

"Authorize VisualStudioLiveShare" and accept all things.

![2](/vscode_liveshare/3_authorize.png)

You'll know you're logged when your name appears in the status bar to the left of the Live Share icon.

![3](/vscode_liveshare/4_bottom.png)

At this point an invite link should be copied to your clipboard, which you can share with your team mates. To end the session, click on your name in the status bar and "Stop Collaboration Session".

To create a new invite link, you can:

* Click on Live Share in the status bar
* Click on your name in the status bar and select "InviteOthers (Copy Link)"
* Click on the "Live Share" icon in the side bar to open a Live Share panel, and select "Share (Read/Write)"

![4](/vscode_liveshare/5_panel.png)

Once you've collaborated with someone they'll be added to your contacts and if they're online you can invite them by clicking on the "Invite Contact" icon next to their name.

![5](/vscode_liveshare/6_contacts.png)

If Read and Write access is enablesd, your team mates can edit your code, comment it, highlight sections of it, save it, and run it in real time. But they won't have access to any objects in your environment or files on your computer. When code is run, it is run locally.
