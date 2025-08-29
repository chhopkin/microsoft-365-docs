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
# Build Apps with Microsoft 365 Copilot

Microsoft 365 Copilot now includes powerful, native capabilities for code generation and app building—making it easier than ever for information workers to create lightweight apps directly within their Microsoft 365 environment.

## Overview

App generation is now a core feature of chat experiences in Microsoft 365 Copilot. This functionality is designed to empower users—especially those already working in Microsoft 365—to build and share apps without needing additional tools or licenses.

There’s no dependency on Power Apps, and no extra sign-up or authentication steps. Just launch Microsoft 365 Copilot, describe the app you need, and start building.

## Key Features

**No Setup Required**

- Launch Copilot and describe your app.
- No sign-up, no authentication prompts.
- Works out-of-the-box for Microsoft 365 users.

**Save and Share App Data**

- Create apps that store simple data.
- Share with teammates for collaborative use.

**Office-Like Sharing**

- Share your app across your organization just like Word or Excel documents.
- Use familiar sharing controls and permissions.

**One-Click Execution**

- Recipients can run the app directly in Microsoft 365 Copilot.
- No installation or configuration needed—just click and go.

## Use Case Example

Imagine you need a simple app to track team feedback during a product launch. With Microsoft 365 Copilot:

1. Open Copilot and describe your app: “I need an app to collect feedback from my team.”
1. Copilot generates the app instantly.
1. You share the app link with your team.
1. Team members open the link and submit feedback—no setup required.


## How Stored Data Works in App Builder

App Builder in Microsoft 365 Copilot uses SharePoint Lists as the underlying data source, providing a scalable and governed foundation for no-code apps.

### Why SharePoint Lists?

- SharePoint Lists have long been a reliable partner for Power Apps—even before AI integration.
- Compared to other low-code platforms (e.g., GitHub Spark with key-value pairs, Loveable with Supabase), SharePoint Lists offer enterprise-grade governance and scalability.

### Lists + Apps Storyboard

Here’s how data flows and evolves in a typical app-building scenario:

1. Enter your prompt in the text box, like the example.
   
    ```copilot-prompt
    I want to build a demo signup sheet that tracks a list of demos
    ```

1. Copilot generates an app with:

    - A schema for the demo table.
    - A front-end UX for data entry and viewing.

1. Then ask Copilot to include organizational info for demo participants and display it as cards.
    - The schema and UX are updated instantly.

1. To share your app, select **Share** and get a sharing link.
    - The app and its data table are seamlessly stored in SharePoint Lists.
    - You send the link to your team to start filling in demo entries.

### End-user experience

1. Team members select the link:

    - They see the list of demos and a form to add new ones.
    - No consent dialogs or extra data-sharing steps.
    - Data and app access are shared just-in-time via the link.
