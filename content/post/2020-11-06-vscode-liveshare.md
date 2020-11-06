+++
author = "Sonia Mitchell"
title = "Live Share in Visual Studio Code"
date = "2020-11-06"
description = "How to set up Live Share in Visual Studio Code"
tags = [
    "Visual Studio Code",
    "Live Share",
    "Collaboration",
]
categories = [
    "Visual Studio Code",
    "Setup",
]
series = ["Visual Studio Code"]
+++

## Step 1 - Download the extension

Install the "Live Share" Microsoft extension from the VSCode marketplace. An icon should appear in the bottom toolbar. Now restart VSCode.

## Step 2 - Share a session

To create a new session, click on "Live share" in the bottom toolbar. The first time you do this, you'll be prompted to sign in, so "Sign in with GitHub" to open a link in your browser. Follow the instructions to "Authorize VisualStudioLiveShare". You'll know you're logged when your name appears in the bottom VSCode toolbar.

At this point an invite link should be copied to your clipboard, which you can share with a collaborator. To create a new invite link, you can click on Click on your name in the bottom toolbar and select "InviteOthers (Copy Link)". To end the session, click on your name in the bottom toolbar and "Stop Collaboration Session".

Alternatively, you can click on the "Live Share" icon in the side bar to open a Live Share panel. Here you can create session links or invite contacts to join your session (once you've collaborated with someone they'll be added to your contacts and if they're online you can invite them by clicking on the "Invite Contact" icon next to their name).

Your collaborators can edit your code, save it, and run it. But they won't have access to any objects in your environment or files on your computer. When code is run, it is run locally.
