---
title: Use Agent Map in the Microsoft 365 admin center
description: Learn how to use Agent Map to visualize, manage, and take action on agents in your Microsoft 365 tenant.
ms.date: 04/07/2026
author: erikre
ms.topic: concept-article
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-description
ms.reviewer: jenniferge
ms.author: erikre
manager: scotv
ms.service: microsoft-365-copilot
---
 
# Use Agent Map in the Microsoft 365 admin center 

The Agent Map is a feature within the Microsoft 365 admin center that provides you with an intuitive visualization of agents available for your organization.

The Agent Map serves as an interactive interface for viewing, organizing, and managing agents registered within your tenant. It presents agents spatially that provides a view for an overall understanding of your agents within your tenant. The map is designed for ease of use, particularly in large environments where list-based views might be overwhelming.

:::image type="content" source="../../media/agents/agent-map.png" alt-text="Screenshot showing the Agent Map, which provides an inventory of agents in the Microsoft 365 admin center." lightbox="../../media/agents/agent-map.png":::

You can use the Agent Map you can do the following actions:

- Identify clusters of agent
- Review agent metrics
- Access information for each agent, such as the following details:
  - Publisher
  - Type
  - Platform
  - Version
  - Connectivity

The Map complements the Registry by offering a more visual and scalable solution for environments with large numbers of agents. The data reflected in Agent Map is the same data available in the Registry tab.
 
## View Agent Map

Use the following steps to view the Agent Map:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. In the left navigation pane, select **Agents** > **All Agents** > **Map**.

When you select the **Map** tab, the map loads agents from your tenant and displays them as icons grouped by platform and other metrics.

Agent Map is available to all Microsoft 365 Copilot administrators with an E7 (Agent 365) license. To access the Agent Map, you're role must be either a **Global Administrator** or an **AI Administrator**. For more information about agent management roles, see [Agent management roles and permissions](agent-365-overview.md#agent-management-roles-and-permissions).

### Clustering
 
By default, Agent Map clusters agents by the platform or by the builder the group of agents were created by. Each cluster appears as its own group on the map, so you can quickly view how agents are distributed across your environment.
 
| Cluster | What agents appear here |
|---|---|
| **Microsoft 365 Copilot Agent Builder** | Agents built using the Microsoft 365 Copilot Agent Builder tool |
| **Copilot Studio** | Agents built using Microsoft Copilot Studio |
| **Copilot Studio Legacy** | Agents built using an earlier version of Copilot Studio |
| **Microsoft 365 Agents Toolkit** | Agents built using the Microsoft 365 Agents Toolkit (formerly Teams Toolkit) |
| **SharePoint** | Agents built using SharePoint |
| **Azure AI Foundry** | Agents built using Azure AI Foundry |
| **Amazon Bedrock** | Agents built using Amazon Bedrock |
| **Google Vertex AI** | Agents built using Google Vertex AI |
| **Microsoft** | First-party agents built and maintained by Microsoft |
| **External Partners** | Third-party agents from external publishers not associated with a known builder |
| **Others** | Any agents that don't match a known platform or publisher |
 
### Searching and filtering agents
 
You can search agents by name using the search bar at the top of the Agent Map. You can also apply filters to narrow the visualization. Available filters include the following:

- **Agents at risk** – Show only agents with one or more active security risks. The count shown reflects high-severity alerts sourced from Microsoft Entra.
- **Agents without owners** – Show shared agents that no longer have an active owner, such as agents whose creator has left the organization.
- **Blocked agents** – Show only agents that are currently blocked across your organization.
- **Publisher** – Filter agents by the publisher or developer who created them.
- **Availability** – Filter by the agent's current availability status in your tenant.
- **Channel** – Filter agents by the channel or host product they're deployed to.
- **Platform** – Filter agents by the platform on which they were built. Options include:
  - Copilot Studio
  - Foundry
  - Microsoft 365 Copilot Agent Builder
  - Microsoft 365 Agents Toolkit
  - SharePoint
  - Service Now
  - Azure AI Foundry
  - Other
 
### Exporting agents
 
You can export the full list of agents displayed in the Agent Map to an Excel file. Select **Export** to download agent details for reporting, auditing, or compliance purposes.
 
## Interface features

The Agent Map provides controls to help you navigate the map.

- **Zoom In/Out**: Adjust the map view for closer inspection or broader visualization.
- **Fit to View**: Automatically scales the map to display all agents present in your environment.
- **Keyboard shortcuts**: Provides a key to **Keyboard shortcuts**. You can select this option to see navigation, zoom, selection and general keyboard shortcuts.
- **Settings**: Provides a slider to control the **Max agents per platform** in the Agent Map. 

 
## Agent details
 
When you select an icon for a specific agent, you can see more details about the agent, including:
 
- Details:
  - Description
  - Publisher
  - Agent type
  - Platform
  - Last updated
  - Version
- Users
- Data and tools
- Security
- Activity

For more information about agent details, see [Understand agent details in Microsoft 365 admin center](agent-details.md). 
 
## Taking action on agents
 
From the Agent Map, you can take administrative actions directly on agents without leaving the map view. When you select an agent, the details pane opens and provides available actions based on the agent's current state.
 
Available actions are based on the state of the agent. The action can include the following:
 
- **Assign owner** – Assign an owner to an agent that currently has no active owner. You can only assign ownership to users with a Copilot license.
- **Block** – Blocks the agent from members of your organization. They will not be able to install or use the agent. Additionally, the agent will be removed from any member of your organization who has already installed it.
- **Unblock** – Restore access to a previously blocked agent.
- **Install** - Deploys and installs the agent to the selected users.
- **Pin for users** - The agent will be pinned in the UI (based on channel) where the agent was deployed, so that the agent can be found more easily. Based on the users or groups where the agent was deployed, you can specify who will have the agent pinned.

These actions are reflected in both the Agent Map and the Registry tab. For a full list of available admin actions, see [Agent Registry in the Microsoft 365 admin center](agent-registry.md).
