---
title: Microsoft 365 Copilot App Builder: Build apps easily
description: Discover how to build apps with Microsoft 365 Copilot App Builder. Create and share apps easily—start building today!
author: mduelae
ms.author: mkaur
ms.reviewer: mkaur
ms.date: 08/29/2025
ms.topic: how-to
ms.service: powerapps
---
# Build apps with Microsoft 365 Copilot

Microsoft 365 Copilot App Builder lets you quickly create and share lightweight apps in your Microsoft 365 environment. This article explains how to use App Builder to streamline app creation and collaboration.

App generation is a core feature of chat experiences in Microsoft 365 Copilot. This feature lets you build and share apps without extra tools or licenses if you already use Microsoft 365.

You don't need Power Apps, extra sign-up, or authentication steps. Open Microsoft 365 Copilot, describe the app you need, and start building.

## Key features of Microsoft 365 Copilot App Builder

**No Setup Required**

- Launch Copilot and describe your app.
- No sign-up, no authentication prompts.
- Works out of the box for Microsoft 365 users.

**Save and share app data**

- Create apps that store simple data.
- Share with teammates for collaborative use.

**Office-like sharing**

- Share your app across your organization just like Word or Excel documents.
- Use familiar sharing controls and permissions.

**One-click execution**

- Recipients can run the app directly in Microsoft 365 Copilot.
- No installation or configuration needed—just click and go.


## How stored data works in App Builder

App Builder in Microsoft 365 Copilot uses SharePoint Lists as the underlying data source. This setup gives you a scalable, governed foundation for no-code apps.

## Build an app

Here's how data flows and changes in a typical app-building scenario:

1. Enter your prompt in the text box. For example:
   
    ```copilot-prompt
    I want to build a demo signup sheet that tracks a list of demos
    ```

1. Copilot creates an app with:

    - A schema for the demo table
    - A front-end UX for data entry and viewing

1. Ask Copilot to add organizational info for demo participants and show it as cards.
    - The schema and UX update instantly.

1. To share your app, select **Share** and get a sharing link.
    - The app and its data table are stored in SharePoint Lists.
    - Send the link to your team so they can start adding demo entries.

### End-user experience

1. Team members select the link.

    - They see the list of demos and a form to add new ones.
    - There aren't any consent dialogs or extra data-sharing steps.
    - Data and app access are shared just in time through the link.
