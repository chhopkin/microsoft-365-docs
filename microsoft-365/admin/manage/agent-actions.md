---
title: Agent actions available in Microsoft 365 admin center
description: Agent actions available in the Microsoft 365 admin center.
#customer intent: Learn about the agent actions that are available in Microsoft 365 admin center.
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

# Agent actions available in Microsoft 365 admin center

Administrators in the Microsoft 365 admin center can take several actions to control the lifecycle, availability, and compliance of agents in their organization. When administrators use these controls, they can decide which agents are visible, who can access them, and how to manage them across the tenant.

## Agent actions

> [!NOTE]
> Microsoft 365 for government Community Cloud High (GCCH) and Government Community Cloud Moderate (GCCM) environments support publishing agents to the organization.

- **Install**
- **Deploy** - Automatically install an agent for users so it's ready to use without manual setup.
- **Publish** - Make an agent available for installation to specific users or groups.
- **Approve Updates** - Review and approve new versions or changes to existing agents before they're deployed.
- **Block and unblock** - Restrict access to an agent across the organization, preventing any user from using it.
- **Remove** - Remove an agent from the tenant's inventory. You can re-add it later from the store if needed.
- **Delete** - Delete agents directly from the Microsoft 365 admin center. When you delete an agent, Microsoft 365 removes the agent from the inventory and deletes all associated files.
- **Manage Ownerless Agents** - Identify agents without an active owner and take action to block or remove them. For more information, see [Manage Ownerless Agents]().
- **Reassign** - Assign a new owner to agents that are ownerless or active.
- **Export Inventory** - Download the full list of agents for reporting, audit, or compliance purposes.
- **Connect agents**

- **Create instance** - Allow only selected users or groups to install the agent and create instances.
the tenant.

> [!NOTE]
> For information about actions relate to the agent registry list, such as **Export to Excel**, **Upload custom agent**, and **Manage pinned agents**, see [Agent registry in the Microsoft 365 admin center](agent-registry.md).

## Install agents

## Deploy agents

You can deploy agents across the whole organization or for specific users or groups by using the same gestures and controls that work for any other app in the Microsoft 365 admin center.

To deploy an agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All Agents**.

1. Make sure **Registry** is selected, and then filter the list by **Availability**.

1. Select an agent from the list that isn't deployed.

1. In the agent details pane that opens, under the agent's name, select **Deploy**.

1. In the **Deploy agent to selected users** pane, decide whether to deploy the agents to everyone or to specific users or groups, and then select **Next**.

    :::image type="content" source="../../media/agents/deploy.png" alt-text="Screenshot showing the configuration screen to deploy an agent." lightbox="../../media/agents/deploy.png":::

1. In the **Review permissions** pane, review the permissions requested by the agent and grant admin consent if appropriate. For more information, see [Understanding permissions](#understanding-permissions). When finished, select **Next**.

1. In the **Review & finish** pane, select **Finish deployment**.

Deploying an agent affects its availability and functionality in Copilot and in the other host products, such as Outlook, Teams, or Microsoft 365.

### Understanding permissions

In the Microsoft 365 admin center, when granting permissions to agents, consider two types of permissions:

- **Application Permissions**.
- **Delegated Permissions**.

Each permission type grants different actions that agents can perform on behalf of users, depending on the scope of the access. This section explains these two types of permissions and provides an overview of the common permissions available.

#### Application Permissions

**Application Permissions** let the agent access data and perform actions without requiring a user to sign in. These permissions let agents do tasks without needing a user to be signed in, like reading directory data, managing teams, or sending messages.

Key features of application permissions:

- **No user context required** - The agent can operate without an active user session.

- **Wide-reaching capabilities** - Agents with application permissions can act at the organizational level, allowing access to a large range of data.

- **Administrator consent required** - Administrator consent is typically required for granting application permissions.

##### Common Application Permissions

| Permission | Details |
| --- | ---|
| **Group.Read.All** | Read all groups in the organization. |
| **TeamsActivity.Send** | Send a teamwork activity to any user. |
| **RoleManagement.Read.Directory**| Read all directory role-based access control (RBAC) settings. |
| **User.Read.All** | Read all users' full profiles. |
| **Team.ReadBasic.All** | Get a list of all teams in the organization. |

#### Delegated Permissions

**Delegated Permissions** allow the agent to act on behalf of a user when the user is signed in. These permissions provide access to user-specific data and allow agents to perform actions in the context of a particular user.

Use delegated permissions for applications where the agent interacts directly with the user's data or takes actions on their behalf.

##### Key features of delegated permissions

- **User context required** - The agent performs actions with the signed-in user's permission.

- **Granular access** - These permissions are typically more restricted, limiting access to only the user's data.

- **User consent might be required** - Depending on the permissions, users might need to grant consent for the application to act on their behalf.

##### Common delegated permissions

| Permission | Details |
| --- | --- |
| **User.ReadBasic.All** | Read all users' basic profiles. |
| **TeamsActivity.Send** | Send a teamwork activity to any user. |
| **RoleManagement.Read.Directory** | Read all directory role-based access control (RBAC) settings. |
| **User.Read.All** | Read all users' full profiles. |
| **Team.ReadBasic.All** | Get a list of all teams. |

#### Where can administrators see all permissions of an agent

You can find the details of all types of permissions in the **Permissions** tab on the agent details page.

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All Agents**.

1. Select a deployed agent from the list.

1. In the agent details pane that opens, select the **Permissions** tab to view all the permissions granted to the agent.

    :::image type="content" source="../../media/manage-agents-permissions/agent-permissions.png" alt-text="Screenshot showing the Permissions tab on the agent details page in the Microsoft 365 admin center." lightbox="../../media/manage-agents-permissions/agent-permissions.png":::



## Block or unblock agents

Block or unblock agents for the entire organization by using the same controls that work for any other app in the Microsoft 365 admin center.

To block or unblock an agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All Agents**.

1. In the **All agents** page, choose an agent from the list of agents.

1. In the agent details pane that opens, under the agent name, select either **Block** or **Unblock**.

1. In the **Block agent** or **Unblock agent** pane that opens, select either **Block agent** or **Unblock agent**, and then select **Save**.

    :::image type="content" source="../../media/agents/block.png" alt-text="Screenshot showing the panel to block an agent." lightbox="../../media/agents/block.png":::

Blocking or unblocking an agent that you created by using Microsoft 365 Copilot Agent Builder and Microsoft 365 Copilot Studio affects its availability and functionality in Microsoft 365 Copilot. It also affects availability and functionality in other host products, such as Outlook, Teams, or Microsoft 365. However, blocking an agent that you created by using SharePoint only impacts its availability in Microsoft 365 Copilot Chat.

> [!NOTE]
>
> For the [Researcher](https://support.microsoft.com/topic/e63ab760-f3de-4c47-ae87-dad601b0e9c4) and [Analyst](https://support.microsoft.com/topic/ff505b9c-a06c-4be9-b855-69d89b1d25d2) agents, the **Edit users** panel is disabled. To manage their availability, block the agent for the entire tenant by using the **Block** action in the Microsoft 365 admin center.

## Remove agents

You can remove first-party and external agents across the whole organization or for specific users or groups by using the same controls that work for any other app in the Microsoft 365 admin center.

To remove an agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All Agents**.

1. In the **All agents** page, filter the list by **Availability**.

1. Select a deployed agent from the list.

1. In the agent details pane that opens, under the agent name, select **Remove**.

    >[!NOTE]
    >
    > If you don't see the **Remove** option, the selected agent might not be deployed.

1. In the **Remove agent** pane, select the **Remove agent** option, and then select the **Remove agent** button.

Removing an agent affects its availability and functionality in Copilot and in the other host products, such as Outlook, Teams, or Microsoft 365.



## Delete agents

You can delete agents directly from the Microsoft 365 admin center. **Delete** permanently removes the agent and its data from the tenant, while **Remove** makes the agent unavailable to users.

When you delete an agent, the following actions occur:

1. Microsoft 365 removes the agent from the inventory.
1. It deletes all associated files.
1. It deletes the underlying SharePoint Embedded container.

This deletion process is irreversible. Once you delete an agent, it might take up to 24 hours for the deletion to reach all users who had access to the agent. During this time, users might still see the agent listed, but they can't interact with it.

> [!NOTE]
>
> The deletion workflow differs slightly depending on how you created the agent:
>
> - If you created the agent by using Microsoft 365 Copilot Agent Builder or the Microsoft 365 Agents Toolkit, you can delete it from the Microsoft 365 admin center.
> - If you created the agent from Microsoft 365 Copilot Studio, you can manage and delete it from the Power Platform admin center.



