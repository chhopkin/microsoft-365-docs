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
 
# Use agent map in the Microsoft 365 admin center 

The agent map is a feature within the Microsoft 365 admin center that provides you with an intuitive visualization of agents available for your organization.

The agent map serves as an interactive interface for viewing, organizing, and managing agents registered within your tenant. It presents agents spatially that provides a view for an overall understanding of your agents within your tenant. 

:::image type="content" source="../../media/agents/agent-map.png" alt-text="Screenshot showing the agent map, which provides an inventory of agents in the Microsoft 365 admin center." lightbox="../../media/agents/agent-map.png":::

You can use the agent map you can do the following actions:

- Identify clusters of agent
- Review agent metrics
- Access information for each agent, such as the following details:
  - Publisher
  - Type
  - Platform
  - Version
  - Connectivity

The Map complements the Registry by offering a more visual and scalable solution for environments with large numbers of agents. The data reflected in Agent Map is the same data available in the Registry tab.
 
## Who can access Agent Map?

Agent Map is available to all Microsoft 365 Copilot administrators with an E7 (Agent 365) license. To access the Agent Map, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) with an account that has the AI Administrator role, and then go to **Agents** > **All Agents**.
 
## Navigating the Agent Map
 
### Locating the Agent Map
 
To access the Agent Map, sign in to the Microsoft 365 admin center and go to **Agents** > **All Agents**. Select the **Agent Map** tab. When you select the tab, the map loads agents from your tenant and displays them as icons grouped by platform and other metrics.
 
### Clustering
 
By default, the Agent Map clusters agents by the platform or builder they were created with. Each cluster appears as its own group on the map, so you can quickly see how agents are distributed across your environment.
 
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
 
You can search agents by name using the search bar at the top of the Agent Map. You can also apply filters to narrow the visualization. Available filters include:
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
 
- **Zoom in/out**: Adjust the map view for closer inspection or broader visualization.
- **Fit to view**: Automatically scales the map to display all agents present in your environment.
- **Full screen mode**: Enables a larger display, ideal for IT teams monitoring agents in shared spaces.
 
The map is designed for ease of use, particularly in large environments where list-based views might be overwhelming.
 
## Agent details
 
When you select an agent icon, you can see more details about the agent, including:
 
- Details:
  - Description
  - Publisher
  - Agent type
  - Platform
  - Last updated
  - Version
- Users
- Data and tools
- Security and compliance
- Agent activity
 
## Taking action on agents
 
From the Agent Map, you can take administrative actions directly on agents without leaving the map view. When you select an agent, the details pane opens and provides available actions based on the agent's current state.
 
Available actions include:
 
- **Assign owner** – Assign an owner to an agent that currently has no active owner. You can only assign ownership to users with a Copilot license.
- **Block** – Restrict access to the agent across the organization, preventing any user from using it.
- **Unblock** – Restore access to a previously blocked agent.
 
These actions are reflected in both the Agent Map and the Registry tab. For a full list of available admin actions, see [Agent Registry in the Microsoft 365 admin center](agent-registry.md).
 
## Known issues
 
- **Filter counts by platform not yet available**: Filtered agent counts broken down by platform are not currently available. This feature is coming soon.
 
For direct support, contact your Microsoft account representative. Feedback on the Agent Map is actively encouraged to inform future development.

