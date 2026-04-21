---
title: Agent settings in Microsoft 365 admin center
description: Agent settings in Microsoft 365 admin center.
#customer intent:
f1.keywords:
- NOCSH
ms.author: erikre
author: ErikRe
manager: scotv
ms.date: 04/09/2026
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.subservice: agent-management
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- m365copilot
- magic-ai-copilot
- operations-pod
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
---

# Agent settings in Microsoft 365 admin center

The **Agent** settings page in [Microsoft 365 admin center](https://admin.microsoft.com/) provides centralized controls for managing AI agents across your organization. These settings help administrators enforce security, compliance, and governance standards while enabling flexibility for collaboration and productivity.

## Overview

The **Agent settings** page includes the following configuration options:

- **Agent management rules** - Set and run rules to manage or perform actions on agents.
- **Allowed agent types** - Specify which categories of AI agents are permitted for use within the organization.
- **Security templates** - Create preset policies, rules, and allow lists for new AI agents to ensure consistency and compliance.
- **Sharing** - Manage who can share AI agents within your organization and define the methods they can use to share them.
- **User access** - Control which users or groups can interact with AI agents, aligning access with organizational roles and permissions.

These settings allow you to customize agent behavior, control access, and maintain compliance with enterprise standards.

:::image type="content" source="../../media/agents/agent-settings.png" alt-text="Screenshot showing the Agent settings page in the Microsoft 365 admin center." lightbox="../../media/knowledge-agent-idea.png":::

## Agent management rules

Agent Management Rules in the Microsoft 365 Admin Center (MAC) enable tenant administrators to apply governance and lifecycle controls across AI agents at scale using bulk administrative actions. 

Rather than requiring you to manually review and take action on agents individually, Agent Management Rules allow you to:

- Identify agents that meet defined conditions
- Review impacted agents prior to run
- Apply governance actions across affected agents in bulk

This experience helps organizations maintain compliance, ownership accountability, and deployment consistency across agents while keeping administrators in the control loop. 

### Supported Rule‑Based Bulk Actions

Agent Management Rules currently support the following governance scenarios:

- Install Microsoft agents
- Reassign ownerless agents created with Agent Builder to manager
- Block agents that are confirmed compromised

#### Install Microsoft agents

Microsoft first‑party (1P) agents are consistently among the most installed and widely used agents. However, administrators currently lack a scalable way to install these agents proactively across their tenant.

Using the Install Microsoft (1P) Agents rule, you can do the following:

- Identify Microsoft‑published agents within the tenant
- Review eligible agents prior to installation
- Install selected agents for all users through a single bulk action
- Microsoft agents appear as installed and are readily available for end-users in the organization  

#### Reassign ownerless agents created with Agent Builder to manager

Agents may become ownerless when their original creator leaves the organization. Administrators must currently identify and transfer ownership manually, which can result in lifecycle governance gaps.

> [!NOTE]
> This rule is only supported when the agent is created using Microsoft 365 Copilot Agent Builder.

Using the Reassign Ownerless Agents rule, you can do the following:

- Identify agents that no longer have a valid owner
- Review ownerless agents prior to reassignment
- Transfer ownership using a bulk reassignment action to the manager of the previous owner based on Microsoft Entra ID hierarchy

#### Block agents that are confirmed compromised

When an agent is flagged by security tooling such as Microsoft Defender, Microsoft Purview, or Microsoft Entra ID, administrators must mitigate potential risks that could result in misuse or data exposure. 

Using the Block Agents with Risk Alert rule, you can do the following:

- Identify agents that meet defined security risk criteria
- Review affected agents prior to enforcement
- Apply blocking action across impacted agents in bulk

## Allowed agent types

**Allowed agent types** allows control of which types of agents users can view and install from the agent catalog. You can select from the following options:

- **Allow apps and agents built by Microsoft** - Enables users to install agents created by Microsoft.

- **Allow apps and agents built by your organization** - Enables users to install custom agents developed within your tenant.

- **Allow apps and agents built by external publishers** - Enables users to install non-Microsoft agents built by external developers.

:::image type="content" source="../../media/agents/allowed-agent-types.png" alt-text="Screenshot of Allowed agent types." lightbox="../../media/knowledge-agent-idea.png":::

> [!TIP]
>
> - If you disable an option, agents of that type don't appear for users in the Agent store.
> - Agents built by Microsoft are visible to users even if the setting is disabled. Users aren't able to install those agents.

## Security templates

To enhance governance and security for agents, you can apply a template that includes predefined security policies:

- **Default Templates**: Microsoft offers out-of-the-box default templates that include essential security and compliance controls from Microsoft Entra, Purview, and SharePoint. For customers enrolled in the Frontier program with an active Agent 365 license, these default templates automatically assign the Agent 365 license, helping reduce manual license management.

- **Custom Templates**: If you need additional governance beyond the default, create a custom template and apply extra policies such as Restrict External Content sharing to meet your organization's requirements.

> [!NOTE]
>
> As an administrator, you can choose which default template to apply based on the agent type. There are two default templates:
>
> - One for agents that allow instance creation.
> - One for agents that don't allow instance creation.
>
> When an agent is activated or published, a dropdown menu displays both Microsoft default templates. Select the desired template to apply its policies to the agent.

For more information about protecting AI agents, see [Detect, block, and investigate threats to AI agents using Microsoft Defender](/defender-xdr/security-for-ai/ai-agent-detection-protection).

### Create custom templates

To create custom template that can be apply to AI agents used at your organization, follow these steps:

1. Open the [Microsoft 365 admin center](https://admin.microsoft.com/) in your browser.
1. Select **Agents** > **Settings** > **Template** > **Add New Template**.
1. Select the agent that will use the template:

   - Agent that allows instances.
   - Agent with no instances.
   - Provide the template name.
   - Provide description for the template.

    :::image type="content" source="../../media/agents/details-page.png" alt-text="Screenshot of Details page." lightbox="../../media/knowledge-agent-idea.png":::

1. Select the **Next** button and then choose any custom policies you want to add to the template. Microsoft's built-in default policies appears preselected and locked. Since the default policies are locked, they can't be edited. You can add additional policies as needed to meet your organization's requirements.
1. You can review and finish adding the template.

When an agent is being activated or published, a dropdown menu with both your custom templates and Microsoft's default templates is displayed. To apply its policies to the agent, select the desired template from the list.

## Sharing

**Sharing** allows defining who can share agents within your organization and how sharing works.

Options include:

- **Allow all users to share with anyone in the organization** - All users can share their agents with others in your tenant.

- **No users can share with anyone in the organization** - Sharing is disabled at the org level, but users can still share directly with specific individuals.

- **Allow specific groups of users to share with anyone in the organization** - Restrict broad sharing permissions to designated groups.

Only agents built with **Agent Builder** are governed by sharing control.

:::image type="content" source="../../media/agents/sharing.png" alt-text="Screenshot of Shared settings." lightbox="../../media/knowledge-agent-idea.png":::

## User access

**User access** allows control of how members of your organization access and install agents.

> [!NOTE]
>
> As the administrator, you should use discretion when managing individual agent's distribution and costs.

To manage access to Copilot agents, follow these steps:

1. Open the [Microsoft 365 admin center](https://admin.microsoft.com/) in your browser.

1. Select **Agents** > **Settings** > **User access** to manage your organization's agents.

1. Select who can access agents within your organization.

    The setting has three options:

    - **All users** - This option is the default. It means that all users in the organization can access agents, subject to the existing app policies and user assignments.

    - **No users** - This option means that no users in the organization can access agents.

    - **Specific users/groups** - This option lets you select specific users or groups in your organization to have access to agents. While some users in your organization might have permission to install and use agents from the **Agent Registry** list, only the users or groups you select in this setting can use agents.

    > [!IMPORTANT]
    >
    > Data processed by non-Microsoft services isn't subject to Microsoft agreements. Review the terms provided by non-Microsoft agent publishers to make sure that you're familiar the agent's data handling and privacy practices. In addition, consult your internal policies before allowing access.

    :::image type="content" source="../../media/agents/user-access.png" alt-text="Screenshot of User access page." lightbox="../../media/knowledge-agent-idea.png":::

1. Select **Save** to update your Copilot agent settings for your tenant.
