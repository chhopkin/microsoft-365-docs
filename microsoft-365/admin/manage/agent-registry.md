---
title: Agent Registry in the Microsoft 365 admin center
description: Learn how to use Agent Registry in the Microsoft 365 admin center to manage, govern, and audit agents across your organization. Get started.
#customer intent: Learn about the Agent Registry in the Microsoft 365 admin center.
f1.keywords:
- NOCSH
ms.author: erikre
author: ErikRe
manager: scotv
ms.date: 04/08/2026
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

# Manage agent registry in Microsoft 365 admin center

The agent registry in [Microsoft 365 admin center](https://admin.microsoft.com/) provides a centralized view of all agents available for your organization. This list helps you monitor, manage, and govern agents your inventory of agents available for your organization.

The agent **Registry** lists all agents that are available to your organization, including:
- **Microsoft agents** - Built and maintained by Microsoft.
- **External partner-built agents** - Built by trusted non-Microsoft developers.
- **Shared by creator** - Agents created and shared by individual users or developers in your organization.
- **Published by your org** - Custom agents approved and published by your organization for broader use.

The agent **Registry** provides quick details about the agents your organization has available:
- **Total agents** - 
- **Agents without owners** -
- **Blocked agents** - 

:::image type="content" source="../../media/agents/agent-registry.png" alt-text="Screenshot showing the agent list which provides an inventory of agent in the Microsoft 365 admin center." lightbox="../../media/agents/agent-registry.png":::

To view the agent registry:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. In the left navigation pane, select **Agents** > **All Agents** > **Registry**.

:::image type="content" source="../../media/agents/agent-registry.png" alt-text="Screenshot showing a list of available agents for a tenant." lightbox="../../media/agents/agent-registry.png":::

You can filter the agent list based on the following criteria:
- **Status** - 
- **Publisher** -
- **Channel** -
- **Platform** -
- **Data source** -

> [!TIP]
> If you don't see the agents that you expect to see in the agent registry list, check to make sure you don't have an existing filter set.

The agent registry provides the following actions:
- **Refresh** -
- **Export to Excel** -
- **Upload custom agent** -
- **Manage pinned agents** -
- **Search** -

In addition, you can change the view of the list from **Normal list** to **Compact list** by selecting the *list* icon next to the **Search** box.

## Agents without owners

Shared agents can become ownerless when you delete the user who created them from the organization.

To help administrators manage these scenarios, the Microsoft 365 admin center now enables you to identify and manage ownerless shared agents. The dashboard displays the total count of such agents, a one-click filter to quickly isolate them, and real-time updates that reflect user deletions. When administrators use these features, they can efficiently review and address ownership gaps by blocking or deleting affected agents.

:::image type="content" source="../../media/agents/ownerless-shared-agents.png" alt-text="Screenshot of the ownerless shared agents view." lightbox="../../media/agents/ownerless-shared-agents.png":::

### Key features

- **Ownerless agent count** - Administrators can view the total number of agents without a valid owner directly from the dashboard. For example, the dashboard shows 20 ownerless agents, which indicates that users who left the organization created these agents.

- **One-click filter** - Selecting the dashboard pane instantly filters the agent inventory to display only shared agents missing an owner. This feature allows for quick triage and action.

- **Real-time updates** - The ownerless agent count automatically updates when you hard delete a user from the organization. This feature ensures that the dashboard reflects the current state without requiring manual refreshes.

### Steps to view and manage ownerless shared agents

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. In the **All agents** page, locate the **Missing an Owner** tab.

1. Select the tab to filter **Agent inventory**.

1. Review the list of ownerless agents and take appropriate actions such as [blocking](agent-actions.md#block-or-unblock-agents) or [deleting](agent-actions.md#delete-agents) the agent.

## Export to Excel

Export the list of shared agents to an Excel file. This feature is essential for detailed analysis and reporting.

> [!NOTE]
>
> If the export process reaches one minute, the exported file includes only the data up to that point.

The exported file includes comprehensive information about each shared agent, such as:

- Name.
- Host products.
- Created date.
- Developer user ID.
- Description.
- Status.
- Version.

With this information, you can efficiently manage and review the shared agents within your organization, ensuring compliance and optimizing resource allocation.

## Upload custom agent


## Microsoft Graph API for Agent Registry and Agent Details (preview)

You can also access Agent Registry data programmatically through Microsoft Graph APIs, which gives you scalable and programmatic control over agent management. By using the new Microsoft Graph API endpoints, now in preview, administrators can integrate the following tasks into existing workflows across agents in Microsoft 365:

- Automate bulk agent management.
- Streamline onboarding.
- Integrate governance.

Beyond manual UX-driven agent management, the Microsoft Graph API helps you accelerate agent management, maintain security and compliance, and ensure agents are available to the right users at the right time.

- **Get all agents in your inventory** - By using the [GET packages API](/microsoft-365-copilot/extensibility/api/admin-settings/package/copilotpackages-list), administrators can retrieve a comprehensive list of all agents in their tenant to support compliance and reporting needs.

- **Get details of a particular agent in your inventory** - The [GET package details API](/microsoft-365-copilot/extensibility/api/admin-settings/package/copilotpackagedetail-get) provides rich metadata and details for any agent, making it easier to audit, manage, and optimize agent management.

The API works with the **AI Admin Role**.

For more information, see [Agent and app Package Management API overview (preview)](/microsoft-365-copilot/extensibility/api/admin-settings/package/overview).

## Risks column in the Microsoft 365 admin center All agents page

The **Risks** column on the Microsoft 365 admin center **All agents** page provides a unified view of aggregated high severity risks across Microsoft security platforms such as Entra, Microsoft Defender, and Purview. It closes a critical visibility gap for IT administrators responsible for governing AI agents. The **Risks** column is only available when a tenant has a [Microsoft 365 E7](https://microsoftpartners.microsoft.com/abs/Blog/?title=Introducing%20Microsoft%20365%20E7:%20The%20Frontier%20Suite) license.

:::image type="content" source="../../media/agents/all-agents-page.png" alt-text="Screenshot of the All agents page in the Microsoft 365 admin center." lightbox="../../media/agents/all-agents-page.png":::

To access the **All agents** page in the Microsoft 365 admin center and view the **Risks** column, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Agents** to expand it.

1. Under **Agents**, select [**All agents**](https://admin.cloud.microsoft/?#/agents/all).

1. In the **All agents** page, make sure **Registry** is selected.

1. The **Risks** column appears in the table in the **All agents** page. If the **Risks** column doesn't appear, the tenant might not have a Microsoft 365 E7 license.

When an administrator selects the risk count for an agent from the **Risks** column, they're taken directly to the Security tab within the agent's flyout details pane. This flyout provides a focused and actionable view of the total aggregated risk counts across all supported detection platforms for the selected agent. From this view, the administrator can further investigate risks and take mitigation actions, such as using the **Block** option to prevent the agent from operating if necessary. Additionally, the **Enabled policies and protection** sections display the default security protections applied to the agent by Microsoft Entra and Microsoft Purview.

:::image type="content" source="../../media/agents/agent-risks-flyout.png" alt-text="Screenshot of the agent risks flyout pane in the Microsoft 365 admin center." lightbox="../../media/agents/agent-risks-flyout.png":::

If the agent has multiple instances associated with it, the flyout initially displays a breakdown of aggregated risks by instance. From here, the admin can proceed to view the total aggregated risk counts across all detection platforms for the selected agent.

:::image type="content" source="../../media/agents/agent-instances-risks-flyout.png" alt-text="Screenshot of the agent instances risks flyout pane in the Microsoft 365 admin center." lightbox="../../media/agents/agent-instances-risks-flyout.png":::

To support further investigation, admins can select the **Review** link. The **Review** link redirects to the respective security portals where further action can be taken.

> [!IMPORTANT]
>
> - The **Risks** column only shows high severity risks flagged by the respective platforms. Zero risks is an indication that there are no high risks presently for the agent. However, there could be other types of risks, such as low or medium, in the respective security platforms.
>
> The **Risks** column shows Microsoft Entra alerts from the past 90 days, following Microsoft Entra's retention policy. If agents no longer return active alerts because the underlying alerts are older than 90 days, the column appears as blank. As a result, some agents might continue to be marked **at risk** within Microsoft Entra even if no corresponding alert appears in Microsoft 365 admin center's **Risks** column. The column supports all blueprint IDs and their associated instances. Any other agent types appear as blank in the **Risks** column.

