---
title: Get started with the Microsoft Frontier program
description: Learn how IT administrators can enable the Microsoft Frontier program to evaluate innovative and emerging AI features and agents before general availability.
author: dansimp
ms.author: dansimp
manager: dansimp
ms.date: 04/07/2026
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

Access to Frontier experiences vary depending on your organization’s subscription and user roles. Frontier is managed at the tenant level.

> [!IMPORTANT]
> Use of Microsoft Frontier requires a Microsoft 365 Copilot license.
> Not all preview features are available in Frontier. For more detailed information, see [Microsoft Frontier program](https://www.microsoft.com/microsoft-365-copilot/frontier-program). 

## Set up Frontier experiences

Frontier settings are managed in the Microsoft 365 Admin Center.

> [!IMPORTANT]
> Frontier is managed at the tenant level. Before enabling Frontier, ensure that **Microsoft 365 Copilot** licenses are assigned to your users, and you have an administrator account that can access the Microsoft 365 Admin Center.

### Turn on Frontier features

To enable Frontier preview experiences:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with an account that includes one of the following roles: **AI Admin**, **Security Admin**, **Office Apps Admin**.   
2. Navigate to **Copilot** > **Settings**.
3. Select **Copilot Frontier**.
4. Choose how Frontier access is assigned in your organization:

   - **No access** (default)
   - **All users**
   - **Specific users or security groups**

After Frontier is enabled, supported preview features become available to eligible users as they're released. Note that it might take an hour or more for Frontier features and agents to be available to users.

> [!NOTE]
> Some AI features in Microsoft 365 Desktop and mobile apps are currently released as a part of the Microsoft 365 Insider program. Learn more about the [Microsoft 365 Insider Program for Business](https://aka.ms/msft365insiderbusiness).

### Manage Frontier agents
Before your users can access Frontier agents, you'll need to make sure that Agent types are approved.

1. In to the [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Agent** > **Settings** > **Allowed agent types**.
1. Verify that "Allow apps and agents built by Microsoft" is checked. This allows use of Microsoft Frontier agents. 

You can optionally allow other agent types by using this control. This allows users to be able to search and discover your own organization agents and allows users to build and use their own agents. 

> [!NOTE]
> You can manage access for specific agents for specific users or groups. For more information, see [Agent settings in Microsoft 365 admin center](/microsoft-365/admin/manage/agent-settings.md)
>
> You can also manage the agents that show up in the Agent Store. For more information, see [Set up Agent Store in Microsoft 365 Copilot](/microsoft-365/admin/manage/agent-settings/copilot-agent-store.md)

> [!IMPORTANT]
> After the Frontier program is enabled, **Frontier agents** are available from the Agent store in Microsoft 365 Copilot. Search for "Built my Microsoft", and Frontier program agents will be displayed with **(Frontier)** in the name. It might take up to an hour for Frontier agents to appear in the store. 

### Manage AI provider large language models
Some Frontier features and agents might require access to other AI provider large language models, such as Anthropic. Review the requirements and understand the implications for each large language model you want to use. 

To allow access to other models, use the Microsoft 365 Admin Center to explicitly approve each model. For more information, see [Manage AI provider settings in the Microsoft 365 admin center](/microsoft-365/copilot/copilot-anthropic-apps#manage-the-setting-in-the-microsoft-365-admin-center).

#### Researcher and analyst in Microsoft 365 Copilot

Researcher and Analyst are considered features of Microsoft 365 Copilot. Both Researcher and Analyst are automatically deployed to Microsoft 365 Copilot licensed users and are pinned to the Microsoft 365 Copilot app user interface. While you can block access to these capabilities, you cannot unpin them.  

### Configure AI-enabled Cloud PCs

To use AI-enabled Cloud PCs during Frontier preview, complete the following steps shown in [AI-enabled Cloud PC](https://aka.ms/AICloudPCsLearn).

User accounts and Cloud PCs meet required technical specifications. All AI enablement for eligible Cloud PCs are completed by using Microsoft Intune. Cloud PCs must also be enrolled in the Windows Insider Program Beta Channel.

- [Experience next-gen productivity with Windows 365 AI-enabled Cloud PCs](https://aka.ms/AICloudPCs)  
- [AI-enabled Cloud PC](https://aka.ms/AICloudPCsLearn)
