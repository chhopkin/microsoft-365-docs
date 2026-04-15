---
title: Agent requests in Microsoft 365 admin center
description: Agent requests in Microsoft 365 admin center.
#customer intent: Learn about agent requests in Microsoft 365 admin center.
f1.keywords:
- NOCSH
ms.author: erikre
author: ErikRe
manager: scotv
ms.date: 04/07/2026
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

# Manage agent requests in Microsoft 365 admin center

The **Requests** list of agents provides a view of agents that require your review and action. Members of your organizaton can request specific agents that need your review before an agent can be made available. For example, agents that have been created by members of your organization using Agent Builder or Copilot Studio can be submitted for admin approval. When an agent is submitted for admin approval, all metadata about an agent’s definition is provided in Microsoft 365 admin center. From the **Requests** list, you can select the agent to see the details about the agent to better understand the agent’s capabilities, data sources, and custom actions before allowing the agent to be published to your organization.

:::image type="content" source="../../media/agents/agent-requests.png" alt-text="Screenshot showing agent requests, which provides an list of agents that need admin review." lightbox="../../media/agents/agent-requests.png":::

### Agent registry filters

The agent **Requests** can contain a large list of agents that new your approval. You can filter the agent **Requests** list based on the following criteria:
- **State** - You can filter the agent list based on state of the requested agent. 
- **Publisher** - The publisher filter indicates who owns and distributes the agents that are listed.
- **Channel** - The channel filter is the location where the agent has been deployed. It is the surface through which members of your organization can discover and interact with the agent. Channel values include **Copilot**, **Office**, **Outlook**, **Teams**.

> [!TIP]
> If you don't see the agents that you expect to see in the agent registry list, check to make sure you don't have an existing filter set.

## Requested agents pending review

When an agent is submitted for admin approval, all metadata about an agent’s definition is provided in Microsoft 365 admin center. Select the available tab to confirm the agent’s capabilities, data sources, and custom actions before allowing the agent to be published to your organization.

Use the following steps to view pending agent requests and act on those requests:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
2. Select **Agents** > **All agents** > **Requests**.
3. Select the requested agent and view the agent’s details.<br>
   Confirm the capabilities, data sources, and custom actions that the agent can invoke.
4. Select the **Requests** tab within the agent details pane to view who requested the agent and when they requested it. 
5. Select the name of the member of your organization that requested the agent.
6. Choose either **Approval request and activate** or **Reject request**.

> [!NOTE]
> As an alternative, within the **Requests** list, you can select the ellipses to the right of the agent name, then select **Publish to store** or **Reject submission**.

## Publish agents

To ensure governance for new agents, when a user requests an agent, it requires your approval before becoming available to members of your tenant. You can review the agent's details, such as the description, owner, data, and tools, and then publish or reject it. On publishing, administrators can also scope its audience to specific users or groups, or everyone, ensuring a controlled rollout.

For more information about publishing requested agents, see [Publish agents](agent-actions.md).

## Reject agents


For more information about rejecting requested agents, see [Reject agents](agent-actions.md).

## Activate agents

A governance step for new agents: when a user requests an agent to activate to create instances, it requires AI admin approval before they can create instances. Administrators can review the agent's details, such as the description, owner, data, and tools, and then approve the request and activate or reject it. When an administrator activates an agent, they can also scope its audience, such as specific users, groups, or everyone, ensuring a controlled rollout.

The Microsoft 365 admin center activation process for agents ensures governance, security, and quality of custom applications.

For more information about activating requested agents, see [Activate agents](agent-actions.md).
