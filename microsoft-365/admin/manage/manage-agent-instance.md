---
title: Manage agent instances in Microsoft 365 Admin Center
description: Manage agent instances in Microsoft 365 Admin Center.
#customer intent: As an IT admin, I want to manage agents for Microsoft 365 Copilot so that I can control their availability and functionality within my organization.
f1.keywords:
- NOCSH
ms.author: frankroj
author: frankroj
manager: scotv
ms.date: 11/12/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
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

# Manage agent instances in Microsoft 365 Admin Center

Once an admin activates an agent, requestor can create instances of that agent. The Microsoft 365 admin center provides a centralized view for managing these instances:

- **Agent Inventory Page** - Navigate to **Agents** > **Agent Inventory** to see how many instances are created for a specific agent.

- **Agent Details Flyout** - Selecting an agent opens a flyout panel displaying the total count of instances associated with that agent in the **Overview** tab.

- **See Instance Details** - Selecting **See Details** brings up a detailed list of all instances created under that agent. From this screen, administrators can:

  - **Manage individual instances** - Access and update settings for each instance.
  - **Review security and compliance status** - Ensure every instance meets organizational standards.
  - **Apply and customize licenses** - Assign licenses and configure options at the instance level.

This streamlined experience helps administrators maintain control, compliance, and flexibility across all agent instances.

## Block agent instances

You can block or unblock agent instances for the entire organization using the same controls available for any other app in the Microsoft 365 admin center. Blocking an instance stops it and any actions it's performing.

To block or unblock an agent:

1. In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Agents** > **All Agents**.
1. Select an agent from the list.
1. A panel opens. Under the **Overview** tab, **Instance availability** is displayed.
1. Select **See details** to see all instances created by that agent. From here, administrators can manage individual instances.
1. Select an instance and choose **Block**.

To restore functionality, the administrator can **Unblock** the instance at any time.

## Delete agent instances

Administrators can delete an instance from the Microsoft 365 admin center when it's no longer needed.

1. In the left navigation pane, select **Agents** > **All agents**.
1. Choose the agent that owns the instance you want to delete.
1. A panel opens. Under the **Overview** tab, **Instance availability** is displayed.
1. Select **See details** to see all instances created by that agent.
1. Select the instance you want to delete, then select **Delete**.
1. Confirm the deletion when prompted.
1. Notify the Hiring Manager of Deletion.
1. Provide access to Instance's OneDrive and Outlook data for 30 days (about 4 and a half weeks).
1. Remove or reassign Microsoft 365 licenses tied to the instance.
1. After 30 days, all instance accounts and data are permanently deleted. Audit logs are kept.
1. Once deleted, the instance no longer appears in the list.

## Ownerless shared agent management

Shared agents might become ownerless when the user who created them is deleted from the organization.

To help administrators manage these scenarios, the Microsoft 365 admin center now enables you to identify and manage ownerless shared agents. The dashboard displays the total count of such agents, a one-click filter to quickly isolate them, and real-time updates that reflect user deletions. With these features, administrators can efficiently review and address ownership gaps by blocking or deleting affected agents.

:::image type="content" source="../../media/agents/ownerless-shared-agents.png" alt-text="Screenshot showing ownerless shared agents." lightbox="../../media/agents/unblock.png":::

### Key features

- **Ownerless agent count** - Administrators can now view the total number of agents without a valid owner directly from the dashboard. For example, the dashboard shows 20 ownerless agents indicating that users who left the organization created these agents.

- **One-click filter** - Selecting the dashboard pane instantly filters the agent inventory to display only shared agents missing an owner. This feature allows for quick triage and action.

- **Real-time updates** - The ownerless agent count automatically updates when a user is hard deleted from the organization. This feature ensures that the dashboard reflects the current state without requiring manual refreshes.

### Steps to view and manage ownerless shared agents

1. In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Copilot** > **Agents**.
1. Locate the **Missing an Owner** tab.
1. Select the tab to filter **Agent inventory**.
1. Review the list of ownerless agents and take appropriate actions such as blocking or deleting the agent.

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
