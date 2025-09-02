---
title: Microsoft 365 Copilot App Builder: Build apps easily (preview)
description: Discover how to build apps with Microsoft 365 Copilot App Builder. Create and share apps easily—start building today!
author: mduelae
ms.author: mkaur
ms.reviewer: mkaur
ms.date: 09/15/2025
ms.topic: how-to
ms.service: powerapps
---
# Build apps with Microsoft 365 Copilot (preview)

[This article is prerelease documentation and is subject to change.]

App Builder is an agent in Microsoft 365 Copilot that lets you create and share lightweight, interactive apps in your Microsoft 365 environment. You don't need coding skills or extra signups—just open Copilot, describe the app or visualization you want, and start building instantly.

App Builder lets you:

- Prototype ideas quickly
- Turn complex data sets into interactive visuals
- Build secure productivity tools for you or your team
- Quickly iterate and refine app features in Copilot chat
- Share and deploy apps to boost productivity and collaboration

Use enterprise data from documents, spreadsheets, and other sources to generate fully functional, secure apps—all without writing code. Just describe what you need, and App Builder does the rest. Explore data, prototype solutions, and streamline workflows.

:::image type="content" source="media/app-builder/app-builder-enter-prompt.png" alt-text=" Enter your prompt in the text box to create an app":::

> [!IMPORTANT]
>
> - This is a preview feature.
> - Preview features aren't meant for production use and might have restricted functionality. These features are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520), and are available before an official release so that customers can get early access and provide feedback.
> - This feature is only available in English.

## Prerequisites

App Builder is available in the Frontier program and you must [add it to your Copilot](managingappbuilder.md). Frontier lets you try the latest model innovation and give feedback before experiences are generally available.

## Key features

You don't need Power Apps or extra authentication. Open Microsoft 365 Copilot, describe your app, and start.

**No setup required**

- Open Copilot and describe your app.
- No sign-up or authentication prompt.
- Works out of the box for Microsoft 365 user.

**Save and share app data**

- Create apps that store simple data.
- Share with your teammate to collaborate.

**Office-like sharing**

- Share your app across your organization like Word or Excel document.
- Use familiar sharing controls and permissions.

**One-click execution**

- Recipients run the app directly in Microsoft 365 Copilot.
- No installation or configuration needed—just select, and go.


## Build an app

With App Builder, create interactive, secure apps using natural language—no coding required. Describe the problem you want to solve, the type of app you need, or the information you want to visualize. Add images to show how you want the app to look, and reference data from documents, spreadsheets, meetings, messages, and other Microsoft 365 sources.

**How it works**

1. Enter your prompt in the text box. For example:
   
    ```copilot-prompt
    I want to build a demo signup sheet that tracks a list of demos.
    ```

1. App Builder creates your app:
   - It generates a schema for your data, like a table for demo signups.
   - It builds a user interface for entering and viewing information.
   
    :::image type="content" source="media/app-builder/app-builder-build-an-app.png" alt-text="App Builder create an app":::

1. Refine your app:
    - Ask Copilot to add features, such as showing participant info as cards.
    - The app updates instantly as you make changes.

> [!NOTE]
> If you don’t see App Builder as an agent, your organization needs to be enrolled in the [Frontier program](https://adoption.microsoft.com/en-us/copilot/frontier-program/) and [add App Builder to your Copilot](managingappbuilder.md).


## Play an app

Play an app you create with App Builder by following these steps:

**For app makers**:

Open App Builder and find your app in the app list. Select the **Play** button next to the app to launch it. If you’re editing an app, play it directly from the editing screen to see how it works in real time.

**For shared users**:

 If someone shares an app with you, open the share link you get from the app maker or another user. This link launches the app so you can start using it right away. Play an app to test its functionality and experience it as your users do.

## Share an app

Share apps you create in App Builder with a share link, like you do with Word documents or PowerPoint decks. To share your app:

1. Open the app for editing in App Builder. 
1. Select the **Share** button in the top right corner to generate a share link.

Send this link to anyone in your organization who can use Microsoft 365 Copilot. Anyone with the link can open and use the app, including all its data. Share responsibly and only with people who should have access to the app’s information.

<insert image of share button>


Send this link to anyone in your organization who has access to Microsoft 365 Copilot. Anyone with the link will be able to open and use the app, including all the data it contains. Be sure to share responsibly and only with people who should have access to the app’s information.

<insert image of share button>

## Delete an app

1. Open App Builder and find your app in the app list.
1. Select the **Delete** icon next to the app to permanently remove it. Confirm the deletion, because you can't undo this action.

When you delete an app, everyone you shared it with immediately loses access, and the app and its data aren't available to others.

<insert image of delete button>


## Manage App Builder


App Builder is in the Agent store and is labeled with **(Frontier)**. If you have a Microsoft 365 Copilot license, follow these steps to find App Builder:

 1. Open Microsoft 365 Copilot Chat on the web. 
 1. Select **All Agents**. 
 1. Go to one of these categories in the store: **Built by Microsoft**, **agents**, or **productivity**. 
 
There aren't any usage limits for end users, but this might change as the feature evolves. 

App Builder's availability is controlled by your organization's Microsoft 365 app store settings, which follow your company's policies and permissions. Follow these steps to check or update these settings: 

1. Go to the Microsoft 365 admin center. 
1. If Copilot agents are set to **No Users**, change this to **All Users** or **Specific Users** to let users access App Builder.

By default, agents are available for users to install, but you might experience throttling during periods of heavy usage. Manage App Builder with the same controls as other Microsoft 365 apps in the admin center. For more information on managing Copilot agents, see [Manage agents for Microsoft 365 Copilot in Integrated Apps](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?view=o365-worldwide).
