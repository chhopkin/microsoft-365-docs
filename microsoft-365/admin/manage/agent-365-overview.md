---
title: Agent overview in Microsoft 365 admin center
description: Track agent usage across your organization and take steps to improve impact from Microsoft 365 admin center.
#customer intent: As an IT admin, I want to manage agents for Microsoft 365 Copilot so that I can control their availability and functionality within my organization.
f1.keywords:
- NOCSH
ms.author: erikre
author: erikre
manager: scotv
ms.date: 04/15/2026
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

# Agent management in Microsoft 365 admin center

Agents are powerful AI companions that can handle a range of interactions and tasks. An agent can resolve issues that require complex conversations and autonomously determine the best action to take based on its instructions and context. It coordinates language models, along with instructions, context, knowledge sources, articles, tools, inputs, and triggers to accomplish goals that members of your organization need to accomplish. Your organization can use agents in multiple languages across websites, mobile apps, Facebook, Microsoft Teams, and any other supported channel.

Agent governance involves using policies, settings, and admin actions to control how agents at your organization are accessed, published, deployed, and managed across your organization. When you apply an agent governance approach to managing agents, you ensure agents and the data they use remain secure and compliant.

By using governance across your agent lifecycle, you help ensure agent adoption is consistent and safe. Governance ensures agents are onboarded intentionally, operate within guardrails, and are managed consistently from build through retirement.

Organizations face significant challenges related to agent governance, including the following:
- How to apply consistent governance policies across all agents, regardless of how or where they’re built.
- How to balance developer freedom and experimentation with centralized oversight.
- How to identify and retire low value or ownerless agents before they create risk or cost.

By managing agents within Microsoft 365 admin center, organizations can establish these guardrails for agents and people, onboard agents with IT oversight, and govern agent access to resources and data, thereby meeting the challenges that organization face. In addition, organizations track their governance approach with built-in compliance and data retention details.

The following capabilities help your organization confidently manage and govern your agent ecosystem:

- **Bring agents under control from day one** - Onboard and approve agents through one IT controlled flow, applying policy templates to every agent for governance and compliance.
- **Control what agents can access and do** - Enforce least-privilege access by controlling which users, data, and tools agents can use and limit access to only the resources and other agents they need.
- **Automate ongoing agent governance** - Leverage rules-based agent management to automatically enforce lifecycle policies, such as expiring inactive agents, flagging ownerless agents, or blocking risky agents.
- **Be audit-ready from the start** - Strengthen visibility and traceability of agent actions and interactions, including who approved an agent, what it accessed, and how it behaved.
- **Reduce compliance and safety risks** - Establish data safety and compliance controls to detect, retain, and investigate unethical agent interactions.

The Agent workload within [Microsoft 365 admin center](https://admin.microsoft.com/) allows you to view a summary of agents that you manage, deploy, and monitor at your organization. It provides usage and insights that help monitor agent adoption and governance. The Agent workload serves as the grounding control plane for all agents managed at your organization.

The Agent workload will help you accomplish the following tasks:
- Discover and review the agents that exist in your organization's tenant
- Understand who published and owns each agent
- Control availability and access to each agent
- Apply agent governance and policy decisions consistently across channels

## View the Agent overview

You can access and view the **Agent overview** using the following steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.cloud.microsoft/).
2. Select **Agents** > **Overview**.
   The **Agent overview** pane is displayed.

> [!IMPORTANT]
> Certain features are available within Microsoft 365 admin center based on services licensed in your subscription. Based on your subscription, you may see Agent 365 branding and additional agent related features and details. To view your licensed subscriptions in the [Microsoft 365 admin center](https://admin.cloud.microsoft/), select **Billing** > **Licenses** > **Subscriptions**.

## Agent overview summary

Using the **Agent overview**, you can view key agent details for your tenant, including the following items:

- A snapshot of agent health and actionable insights for the last 30 days
- Track agent adoption and usage trends
- Identify alerts and governance gaps
- Critical actions for administrators to review, such as:
  - Approve pending requests
  - Manage agents without owners
- Total agents in your organization
- Enable visibility and control across all agents in your tenant
 
> [!TIP]
> A tenant is an instance of Microsoft Entra ID. Your subscription to Copilot or Agent 365 is hosted by a Microsoft Entra tenant. For more information about creating and understanding tenants, see [Set up a new Microsoft Entra tenant](/entra/identity-platform/quickstart-create-new-tenant) in the Microsoft Entra documentation.

:::image type="content" source="../../media/agents/agent-overview.png" alt-text="Screenshot showing the agent workload in Microsoft 365 admin center, which provides management controls and details for agents within your organization's tenant." lightbox="../../media/agents/agent-overview.png":::

View access to the agent **Overview** doesn't grant permissions to install, modify, or manage agents. Administrative actions continue to be governed by role-based access controls aligned with agent installation and consent workflows.

## Agent management roles and permissions

Access to agent management in Microsoft 365 admin center is controlled by [Microsoft Entra admin roles](/entra/identity/role-based-access-control/permissions-reference). 

While several administrative and security roles can view agent-related information for monitoring and reporting purposes, only select roles are authorized to perform governance actions such as approving agent requests or assigning ownership.

The following table provides agent management capabilities  Microsoft 365 admin center:

| Role | View insights and organization   data | View agent registry information | Install, modify, approve, and manage agent configurations |
|:---:|:---:|:---:|:---:|
| Global Administrator | ✔ | ✔ | ✔ |
| AI Administrator | ✔ | ✔ | ✔ |
| Global Reader | ✔ | ✔ | ✖ |
| AI Reader | ✔ | ✔ | ✖ |
| Security Administrator | ✔ | ✔ | ✖ |
| Security Reader | ✔ | ✔ | ✖ |
| Security Operator | ✔ | ✔ | ✖ |
| Reports Reader | ✔ | ✖ | ✖ |
| User Experience Success Manager | ✔ | ✖ | ✖ |

The **AI Administrator** and **Global Administrator** roles have tenant‑wide visibility and governance authority, where-as by contrast, product-specific admin roles allow governance only within the boundaries of their products (such as Power Platform Administrator and Fabric Administrator).

> [!IMPORTANT]
>
> Use and assign roles with the fewest permissions to accomplish tasks. Accounts with lower permission roles help improve security for your organization. Global Administrator is a highly privileged role. Limit its use to emergency scenarios when you can't use an existing role. For more information, see [About admin roles in the Microsoft 365 admin center](/microsoft-365/admin/add-users/about-admin-roles).

## Governance actions for agents

Administrators can use governance insights in the Microsoft 365 admin center to identify and remediate compliance gaps related to agent usage across the organization.

Examples of governance include the actions:
- Review and approve pending agent installation requests
- Assign ownership to agents without a designated owner

These actions can be initiated based on the following agent views:
- Pending Requests for agents
- Ownerless agents

Selecting these options in Microsoft 365 admin center navigates you to relevant filtered views within the agent **Registry** to take corrective action.

> [!IMPORTANT]
> Governance actions, such as approving agent requests or assigning agent ownership, can only be performed by admins assigned to the **AI Administrator** or **Global Administrator** Microsoft Entra roles. Other supported roles can monitor governance gaps but can't take administrative actions. In addition, admins that have been assigned the **AI Administrator** role aren't authorized to configure **Conditional Access** policies or **Microsoft Entra** access package policies. These actions require a highly privileged administrator role with appropriate Microsoft Graph permissions.

## Hero metrics for agent adoption and impact

Hero metrics provide a high-level summary of the most critical indicators of agent adoption and impact. These metrics give administrators an immediate sense of scale, engagement, and business value.

**Agent registry** - The total count of all agents available in your organization's catalog, including Microsoft-built, partner-built, and custom (LOB) agents. This Agent registry reflects the breadth of agents deployed across your tenant. In the **Agent overview**, you can select **Explore All agents** > **Registry** to view your inventory in detail.
- **Active users** - The number of unique users who interacted with at least one agent within last 30 days. If a user interacts at least once with one agent in the last 30 days, they're considered as an active user.
- **Agent run-time** - Total hours worked by agents during the last 30 days, calculated as the sum of each agent session's duration (end time minus start time).
- **Agent detector** - The external connected platforms that were scanned. You can connect to external platforms to find and monitor agents used in your organization. Your use of external non-Microsoft products is subject to the third-party service provider's terms of use. You're responsible for complying with each provider's terms of use.

## Top actions for you

View actionable governance cards that display urgent tasks for you (the administrator) to maintain compliance and improve adoption. These cards help you quickly identify and resolve governance gaps.

- **Pending Requests for Agents** - See the total number of agent requests awaiting admin approvals within the last 30 days. The card lists the three oldest pending requests, prioritized by oldest first. It also displays the delta badge next to the key metric to highlight week-over-week change in the total requests. To take immediate action, select **Manage requests**. This selection navigates to the **Agent Registry** > **Requests** tab. This tab lists all pending agent requests submitted by users within your organization.
- **Agents at risk** - View the total number of agents with security risks. Select **Manage agent risks** to view agents filter by risk in the **Agent Registry**. 
- **Agents without owners** - View the total number of agents without an assigned owner and still pending owner assignment. Select **Assign Owner** to view a list of agents filtered by **Agents without owners**.
- **Agent with exceptions** - View the total number of agents with errors in their conversations. Select **View details** to view a list of agents filtered by agents with errors.
 
## Agent analytics

Get detailed insights into how agents are distributed and used. This information helps administrators understand adoption patterns and optimize resources.

- **Agents by creators** - View a breakdown of all agents in your inventory by their source of publisher, such as who created and shared the agent. There are two categories:
  - **Your organization** - Agents that your organization created and published. These agents can be shared by the creator or used only by the creator.
  - **External partners** - Agents created by external partners.
  - **Microsoft** - Agent created by Microsoft.
- **Top platforms used to build agents** - See which creation platforms are most used for building agents. For example:
  - Microsoft 365 Copilot Agent Builder
  - Copilot Studio
  - Agents Toolkit
  - SharePoint
  - Other
- **Active users in Copilot over time** - View a trend chart that shows daily active user engagement with agents over the last 30 days. This chart reveals adoption momentum and helps you spot usage spikes or declines.
- **Trending agents by active users** - You can view the agents with the most active users in your organization over the last 30 days.

