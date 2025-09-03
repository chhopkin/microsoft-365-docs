---
title: Use App Builder in Microsoft 365 Copilot to build apps easily
description: Discover how to build apps with Microsoft 365 Copilot App Builder. Create and share apps easily—start building today!
author: mduelae
manager: tapanm
ms.author: mkaur
ms.reviewer: mkaur
ms.date: 09/2/2025
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.subservice: app-builder
---
# Build apps with Microsoft 365 Copilot

App Builder is an agent in Microsoft 365 Copilot that lets you create and share lightweight, interactive apps. You don't need coding skills—open Copilot, describe the app or visualization you want, and start building instantly.

App Builder lets you:

- Prototype ideas quickly
- Turn complex data sets into interactive visuals
- Build secure productivity tools for you or your team
- Quickly iterate and refine app features in Copilot chat
- Share and deploy apps to boost productivity and collaboration
- Use enterprise data from documents, spreadsheets, and other sources to generate fully functional, secure apps—all

:::image type="content" source="media/app-builder/app-builder-enter-prompt.png" alt-text="Screenshot of the App Builder prompt box in Microsoft 365 Copilot, where you enter your prompt to create an app.":::


## Prerequisites

You need to be part of the [Frontier program](https://adoption.microsoft.com/en-us/copilot/frontier-program/) to use App Builder, and you need to [TBD: add it to your Copilot](microsoft-365-copilot-overview.md). Frontier lets you try the latest model innovation and give feedback before these experiences are generally available. 

> [!IMPORTANT]
> This feature is only available in English.


## Build an app

Describe the problem you want to solve, the type of app you need, or the information you want to visualize. Add images to show how you want the app to look, and reference data from documents, spreadsheets, meetings, messages, and other Microsoft 365 sources.

1. Sign in to [Microsoft 365 Copilot](https://www.microsoft365.com/)
1. In the left navigation pane, under **Agents**, select **App Builder**.
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
> If you don’t see the App Builder agent, make sure you meet the [prerequisites](app-builder.md#prerequisites).


## Play an app

Play an app you create with App Builder by following these steps:

**For app makers**:

1. Open App Builder and find your app in the app list. 
1. Select the **Play** button next to the app to launch it. If you’re editing an app, play it directly from the editing screen to see how it works in real time.

**For shared users**:

 If someone shares an app with you, open the share link you get from the app maker or another user. This link launches the app so you can start using it right away. Play an app to test its functionality and experience it as your users do.

## Share an app

Share apps you create in App Builder with a share link, like you do with Word documents or PowerPoint decks. To share your app:

1. Open the app for editing in App Builder. 
1. Select the **Share** button in the top right corner to generate a share link.

Send this link to anyone in your organization who can use Microsoft 365 Copilot. Anyone with the link can open and use the app, including all its data. Share responsibly and only with people who should have access to the app’s information.


## Delete an app

When you delete an app, everyone you shared it with immediately loses access, and the app and its data aren't available to others.

1. To delete an app, open App Builder and find your app in the app list.
1. Select the **Delete** icon next to the app to permanently remove it. Confirm the deletion, because you can't undo this action.


## Manage App Builder

App Builder is in the Agent store and is labeled with **(Frontier)**. If you have a Microsoft 365 Copilot license, follow these steps to find App Builder:

 1. Sign in to [Microsoft 365 Copilot](https://www.microsoft365.com/)
 1. In the left navigation pane, Select **Chat** >  **All Agents**. 
 1. Go to one of these categories in the store: **Built by Microsoft**, **Agents**, or **Productivity**. 
 
There aren't any usage limits for end users, but this might change as the feature evolves. 

App Builder's availability is controlled by your organization's Microsoft 365 app store settings, which follow your company's policies and permissions. Follow these steps to check or update these settings: 

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).
1. In the left navigation pane, select **Copilot** > **Settings**. 
1. Select **Agents**
1. If Copilot agents are set to **No Users**, change this setting to **All Users** or **Specific users/groups** to let users access App Builder.

By default, agents are available for users to install, but you might experience throttling during periods of heavy usage. Manage App Builder with the same controls as other Microsoft 365 apps in the admin center. For more information on managing Copilot agents, see [Manage agents for Microsoft 365 Copilot](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).
