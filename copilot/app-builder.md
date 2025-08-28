---
title: Microsoft 365 Copilt app builder
description: Learn how to use Microsoft 365 Copilt app builder
author: mduelae
ms.author: mkaur
ms.reviewer: mkaur
ms.date: 08/28/2025
ms.topic: how-to
ms.service: powerapps
---
# M365 Copilot: App Builder Agent Summary


Code generation and app building tools are becoming a core capability of chat experiences.

Our goal is to bring app generation for information workers that we have in Microsoft already and put it natively in M365 Copilot.

This capability is part of M365 Copilot without requiring any further licensing or dependency on Power Apps.


<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_0.png" style="max-width:800px;" />


## Overview

Similar to the Agent Builder capability in M365 Copilot you can launch M365 Copilot, describe my app\, and go\! No sign\-up\, no auth prompts\.

Save app data: I can create an app that saves simple data and can be used by others on my team/

Office\-like sharing: I can share my app with anyone in my org\, just like I can with Office docs\.

Users/Recipients of the link can run the app in M365 Copilot with one click and get tasks done in M365 Copilot\.

# Canonical examples

_Needs around complex visualizations\, combine productivity data/knowledge into something a bit more structured/with different visuals\, or into a process\._



  * Tracker – inventory\, event sessions\, tasks and more
  * Collection\, Voting \- Weekly demo session\- need to collect inputs\, suggestions
  * Decision maker – outline options\, pros/cons on a chart\, drag and drop
  * Create an interactive timeline – complex timeline that needs more than PowerPoint
  * Create a prototype of a website \([Bizchat Utterance](https://copilotdash.microsoft.com/ticket/7db4217a-be8b-4bd1-a2ef-1e169c2bf9b7)\)
  * Create a prototype of a dashboard \([Bizchat Utterance](https://copilotdash.microsoft.com/ticket/91dc1453-8675-469e-a2dc-0e88d815c60c)\)
  * ROI calculator/modeler – able to input\, drag different amounts and see outcomes
  * Interactive visual on content from LLMs – filterable tables\, expand collapse sections


[Canonical M365 Copilot App Examples\.loop](https://microsoft.sharepoint.com/:fl:/g/contentstorage/CSP_7917f8f3-509a-4ff9-84af-1beb8c610347/EfBOs-kUpolHrUKUPPQWJ2QBDaZcfBptM2IWhx_t2wJFGw?e=wuQyXO&nav=cz0lMkZjb250ZW50c3RvcmFnZSUyRkNTUF83OTE3ZjhmMy01MDlhLTRmZjktODRhZi0xYmViOGM2MTAzNDcmZD1iJTIxOF9nWGVacFEtVS1Fcnh2cmpHRURSM1dzVFZpTV9KMURnQm1TUjBEMEtwZldTSkx2SmpHZFJaaElyWGQtUFBPVCZmPTAxNlRHUldTN1FKMlo2U0ZGR1JGRDIyUVVVSFQyQk1KM0UmYz0lMkYmYT1Mb29wQXBwJnA9JTQwZmx1aWR4JTJGbG9vcC1wYWdlLWNvbnRhaW5lciZ4PSU3QiUyMnclMjIlM0ElMjJUMFJUVUh4dGFXTnliM052Wm5RdWMyaGhjbVZ3YjJsdWRDNWpiMjE4WWlFNFgyZFlaVnB3VVMxVkxVVnllSFp5YWtkRlJGSXpWM05VVm1sTlgwb3hSR2RDYlZOU01FUXdTM0JtVjFOS1RIWktha2RrVWxwb1NYSllaQzFRVUU5VWZEQXhObFJIVWxkVE5sZE9WbFJWVTBKSlQxZzFSVE5OVUVGU1FUZFJXVXRDU2tJJTNEJTIyJTJDJTIyaSUyMiUzQSUyMjFlOTg3NjE0LTlhNzctNDE1OC04Mjc5LTJmYWEyZDNjYzE3YyUyMiU3RA%3D%3D)

# Scoping

| Capability | Crawl/MVP \(September\) | Walk \(Oct \+\) |
| :-: | :-: | :-: |
| Discover | Discover App builder in list of Agents/on left rail\. | Also potentially invoked from main Bizchat/via tool |
| Build | Chat and multi\-turn iterations side by side a preview of the app\. Code is never seen\. | Additional visual updates for the app in the preview such as color picker\. |
| App Data | Ingest information from Bizchat to use\, store any structured data seamlessly in Lists for read/write\. | Be able to call tools from the app itself\. E\.g\. a button able to kick off an LLM call\. |
| Save/Lifecycle | App will be auto\-saved\, and auto\-published to make any changes available to users\. | Further undo\-redo capabilities\, lightweight version history\, Save a Copy\. |
| Sharing | Share via copy link for anyone in org\, shares app \+ data \(JIT access\)\. Share to individuals\. List data seamlessly shared\. | Share to security groups\. |
| User Discover | Can open link to app\, see it open in M365 Copilot\, like Copilot page\, with chat open\. | Discover via search\, via sources for Bizchat to use/reference\, via Apps page\, via grouping on the left rail e\.g\. Pages\. |

# Agent Discovery/ Invoking Creating App

# First Party Agent: App Builder

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_1.png" style="max-width:800px;" />

__MVP__

Discover the App Builder in in Agents List

See the list of My Apps that have been created

Be able to reference any sources

__Roadmap__

App Builder Agent recommended for relevant scenarios in main Bizchat

See Recent used\, Shared\, Favorites\, other templates

# App Builder: Loading

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_2.png" style="max-width:800px;" />

__MVP__

Leveraging Side by Side preview of the app

Information Worker friendly experience – not streaming code

# App Builder: Thoughts

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_3.png" style="max-width:800px;" />

__MVP__

Speak to sources that are being leveraged/ ingested

Show thoughts from coding in terms of outlining the experiences

# App Builder: Initial App & preview

__MVP__

See full interactive app preview in side by side

Able to navigate through app\, use it\, add data\.

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_4.png" style="max-width:800px;" />

# App Builder: Edits

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_5.png" style="max-width:800px;" />

__MVP__

Ask for any changes to the app via the Copilot chat

__Roadmap__

Enable lightweight edits inline the preview such as a color picker

Enable a lightweight undo redo/version history

# App Builder: Data

See appendix for more details

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_6.png" style="max-width:800px;" />

__MVP__

When coding agent identifies need for data\, seamlessly in the background a List will get created to store the data\.

List integration is seamless and follows lifecycle of the app\.

__Roadmap__

More complex data proposals and interactions with Lists

Able to call AI tools from the app e\.g\. summarize feedback and show in app\.

# App Builder: Share

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_7.png" style="max-width:800px;" />

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_8.png" style="max-width:800px;" />

__MVP__

Share via Copy link

__Roadmap__

Other share motions such as in teams\, email and so on

# End User Discovery of App

[Figma for Discovery](https://www.figma.com/design/Xrd4YRRxrQXLJaKq9kjFMB/M365--discovery--data--versions?node-id=0-1&t=PJYdLKgmJOCSRFPQ-1)

<img src="media\app-builder\App Builder in M365 Copilot overview - MVP_9.png" style="max-width:800px;" />

__MVP__

User that has been shared a link can select it and open the targeted app inside of M365 Copilot with the chat open

__Roadmap__

Discover via Search\, Apps page\, suggested by Copilot and more

# Roadmap- Beyond MVP top of mind

Apps that are created should be able to make LLM calls & Access Sydney tools\. E\.g\. Make an app that summarizes status on list of tasks \(Need an LLM call for the summary\)

Apps themselves should be able to be referenced like a source

Apps should be able to be used by Copilot e\.g\. Ask copilot to fill out something with the app\, e\.g\. Project Opal

Apps should be discoverable inside M365 Copilot via search\, in a list and more

# Closing slide

# ODSP & Lists integration

# Many applications require stored data

SharePoint Lists \+ Power Apps have been a strong together story since the beginning without any AI\.

Most of the vibe coding tools have some sort of data base as well – e\.g\. GitHub Spark with Key Value Pairs\, and Loveable with Supabase etc\.

With Lists \+ App Builder\, we can have an enterprise scaled and governed data source for no code generated apps for information workers\.

# Lists + Apps storyboard



* Input into App Builder Agent \- I want to build a demo signup sheet that tracks a list of demos
* An app is generated and I can see what that looks like for me\, and what kind of data it would store\. I can see the list and form\.
  * There is a schema for the table of demos\, and front end UX for the application
* I decide that I also need to see what orgs the demoers are from\. I ask Copilot to update to show what orgs the demos and demo\-ers are from and show as cards\.
  * The schema gets updated\, the UX gets updated
* With this looking good\, I want to Share the app\. I hit share\, and I get a link\. I send that link to my team to fill in the list of demos\.
  * The tables gets saved/stood up in SharePoint Lists seamlessly\.
* As an end user\- they open the link to play the app\, see the list of other demos and see the form to add a demo and fill it in\. \(NOTE there is no consent dialog/additional share of data\)
  * The data and app access are JIT shared with the link\.
* When returning to edit the app\, I can see the current app and list of data from the SP list\.


# Follow-ups on App + Lists needed

Should I be able to access the List\(s\) outside of the app? \(No?\)

If an App gets deleted\, should the Lists get deleted as well? \(Yes?\)

How can we share data access alongside the app share? \(S2S from Power Apps RP?\)

What is the best way to connect to Lists? Graph APIs vs SharePoint connector tradeoffs

Further governance challenges we should keep in mind?

Scale and perf – eg how many Lists per app makes sense? Performance SLA

# Storing the app and runtime

Right now we have approaches based on current Power Apps structure for these – leveraging storing in a hidden environment\, and the code apps runtime for Power Apps

Open to exploring other approaches to see what may be best for M365 Copilot scenarios

