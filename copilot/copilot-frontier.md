---
title: Get started with the Microsoft Frontier program
description: Learn how IT administrators can enable the Microsoft Frontier program to evaluate innovative and emerging AI features and agents before general availability.
author: dansimp
ms.author: dansimp
manager: dansimp
ms.date: 03/30/2026
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.subservice: admin
ms.custom: copilot-frontier
audience: Admin
ms.collection:
ms.localizationpriority: medium
---

# Get started with the Microsoft Frontier program

The Microsoft Frontier program gives organizations early access to innovative and emerging AI capabilities in Microsoft 365 before those features reach general availability (GA). By opting in to Frontier, IT administrators can evaluate new Copilot agents and AI-powered experiences, determine readiness for broader deployment across their tenant, and provide feedback about Frontier feature capabilities to Microsoft.

Access to Frontier experiences varies depending on your organization’s subscription and user roles. Frontier is managed at the tenant level. 

> [!IMPORTANT]
> Use of Microsoft Frontier requires a Microsoft 365 Copilot license.
> Not all preview features are available in Frontier. For more detailed information, see [Microsoft Frontier program](https://www.microsoft.com/microsoft-365-copilot/frontier-program). 

## Set up Frontier experiences

Frontier settings are managed in the Microsoft 365 Admin Center.

> [!IMPORANT]
> Frontier is managed at the tenant level. Before enabling Frontier, ensure that you've assigned Microsoft 365 Copilot licenses to your users, and you have an administrator account that can access the Microsoft 365 Admin Center.


## Enable Frontier features in Microsoft 365 Web apps

To enable Frontier preview experiences in Microsoft 365 applications and agents:

1. Sign in to the Microsoft 365 admin center with an account that includes one of the following roles: **AI Admin**, **Security Admin**, **Office Apps Admin**.   
2. Navigate to **Copilot** > **Settings**.
3. Select **Copilot Frontier**.
4. There are three tabs in the **Frontier settings** 
5. In the **Web apps** tab, choose how Frontier access is assigned in your organization:

   - **No access** (default)
   - **All users**
   - **Specific users or security groups**

5. If necessary for a selected feature, enroll participating users in:

   - Microsoft 365 Insider, or
   - the Beta Channel

After Frontier is enabled, supported preview features become available to eligible users as they're released.

If you're enabling Frontier feature agents, your users should now be able to go to the **Agent Store** and review available Frontier agents.

 Users who participate in Frontier experiences must be assigned a Microsoft 365 Copilot license.

### Configure AI-enabled Cloud PCs

To use AI-enabled Cloud PCs during Frontier preview, complete the following steps shown in [AI-enabled Cloud PC](http://aka.ms/AICloudPCsLearn).

User accounts and Cloud PCs meet required technical specifications. All AI enablement for eligible Cloud PCs are completed by using Microsoft Intune. Cloud PCs must also be enrolled in the Windows Insider Program Beta Channel.

- [Experience next-gen productivity with Windows 365 AI-enabled Cloud PCs](http://aka.ms/AICloudPCs)  
- [AI-enabled Cloud PC](http://aka.ms/AICloudPCsLearn)

### Enable Project Opal

Project Opal can complete tasks on users behalf using a Windows Cloud PC for Agents. Learn more about [Project Opal](/copilot/opal-settings-manage.md). 

To enable Project Opal Frontier experiences in your tenant:

1. Sign in to the Microsoft 365 admin center.
2. Navigate to **Copilot** > **Settings**.
3. Select **Project Opal (Frontier)**.

4. Choose specific users or groups who can access Project Opal:

   - **No access** (default)
   - **Specific user groups**

5. You might be prompted to complete a one-time configuration in the Opal Admin portal to:

   - Configure Cloud PCs
   - Set up starter prompts for users