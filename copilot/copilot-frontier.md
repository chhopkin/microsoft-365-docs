---
title: Get started with the Microsoft Frontier program
description: Learn how IT administrators can enable the Microsoft Frontier program to provide users with early access to emerging AI features and agents before general availability.
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
  - Tier2
ms.localizationpriority: medium
---

# Get started with the Microsoft Frontier program

The Microsoft Frontier program gives organizations early access to innovative and emerging AI capabilities in Microsoft 365 before those features reach general availability (GA). By opting in to Frontier, IT administrators can evaluate new Copilot agents and AI-powered experiences, determine readiness for broader deployment across their tenant, and provide feedback about Frontier feature capabilities to Microsoft.

Access to Frontier experiences varies depending on your organization’s subscription and user roles. Frontier is managed at the tenant level and must be enabled by an administrator before eligible users can access preview features in Frontier.

> [!IMPORTANT]
> For more detailed information, see [Microsoft Frontier program](https://www.microsoft.com/microsoft-365-copilot/frontier-program).

## Prerequisites

Frontier is managed at the tenant level. Before enabling Frontier in your tenant, ensure that the following requirements are met.

- Assign Copilot licenses to users
- An account with Microsoft 365 Admin Center access
- Meet Frontier feature-specific requirements, if applicable

## Set up Frontier experiences

IT administrators can enable Frontier capabilities across Microsoft 365 in multiple ways, depending on the type of AI experience they want to try. Use the following procedures to configure Frontier agents, Microsoft 365 app experiences, AI-enabled Cloud PCs, or Project Opal in your tenant.

### Enable Frontier agents

To make Frontier preview agents available to users in your organization:

1. Sign in to the Microsoft 365 admin center.
2. Navigate to **Copilot**.
3. Select **Agents and Copilot Frontier**, and then turn on Frontier.

   This setting allows Frontier agents and preview AI features to become available in your tenant.

4. Open **Copilot Chat**.
5. Go to **Settings** > **Copilot Frontier**.
6. Choose how Frontier access is assigned in your organization:

   - **No access** (default)
   - **All users**
   - **Specific users or security groups**

7. Go to the **Agent Store** and review available Frontier agents.

> [!NOTE]
> Some agents, such as Microsoft Agent 365, require modern billing to be enabled and acceptance of updated terms and conditions before they can be used.

## Enable Frontier features in Microsoft 365 apps

To enable Frontier preview experiences in Microsoft 365 applications:

1. Sign in to the Microsoft 365 admin center.
2. Navigate to **Copilot**.
3. Turn on **Copilot Frontier**.

   This setting activates early-access AI features at the tenant level.

4. Confirm that users who will participate in Frontier experiences have Microsoft 365 Copilot licenses assigned.

   Only licensed users can access Frontier features in Microsoft 365 apps.

5. If required for a selected feature, enroll participating users in:

   - Microsoft 365 Insider, or
   - the Beta Channel

After Frontier is enabled, supported preview features become available to eligible users as they are released.

### Configure AI-enabled Cloud PCs

To use AI-enabled Cloud PCs during Frontier preview, complete the following steps:

1. Confirm that user accounts and Cloud PCs meet required technical specifications:

   - User eligibility requirements are met.
   - Cloud PC devices meet supported configuration standards.

2. In Microsoft Intune, assign AI enablement to eligible Cloud PCs.

3. Enroll Cloud PCs in the Windows Insider Program Beta Channel.

   Enrollment in the Beta Channel enables experimental AI capabilities on supported Cloud PCs.

For detailed onboarding steps, see:

- http://aka.ms/AICloudPCs  
- http://aka.ms/AICloudPCsLearn

### Enable Project Opal

To enable Project Opal Frontier experiences in your tenant:

1. Sign in to the Microsoft 365 admin center.
2. Navigate to **Copilot** > **Settings**.
3. Turn on **Project Opal (Frontier)**.

4. Configure how access is assigned across your organization:

   - **No access** (default)
   - **All users**
   - **Specific users or security groups**

   Project Opal access is controlled at the tenant level.

5. If required after deployment, go to the Opal Admin portal to:

   - Configure Cloud PCs
   - Set up starter prompts for users

