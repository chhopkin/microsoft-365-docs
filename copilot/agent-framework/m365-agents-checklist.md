---
title: Microsoft 365 Agents Checklist
f1.keywords:
ms.author: erikre
author: ErikRe
manager: dansimp
ms.date: 10/08/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Learn about Microsoft 365 Agents.
---

# Microsoft 365 agents deployment checklist

This checklist is intended to assist admins with the successful deployment of Copilot agent governance. It is structured in a checklist format, providing a comprehensive guide for a streamlined setup process.

**Required administrators for the engagement**:

1. **Microsoft 365 admin** - Setup Copilot agent and connectors settings.
2. **Microsoft Power Platform admin** - Setup Copilot Studio policies and settings.
3. **Microsoft 365 Search admin** - Setup Microsoft 365 Graph connector configurations. 
4. **Microsoft Azure admin** - Setup Azure subscription configurations. 

**Deployment phases**:

  :::image type="content" source="/copilot/microsoft-365/agent-framework/media/m365-agents-checklist/agent-deployment-phases.png" alt-text="Diagram of the Copilot agent deployment phases."  lightbox="/copilot/microsoft-365/agent-framework/media/m365-agents-checklist/agent-deployment-phases.png":::
  
**Downloadable resources**:

- [Visual Checklist and deployment mind map](m365-agents-visual-map.md)
- [Microsoft 365 Copilot agents blueprint](m365-agents-blue-print.md)

## Manage Microsoft 365 Copilot agent access and availability policies

Agent policies refer to the tenant settings you can make as an administrator in the Copilot Control System within Microsoft 365 admin center. Agent policies relate to the available settings for all agents in your tenant. 

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | [Manage access to Microsoft 365 Copilot agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json#manage-access-to-copilot-agents)  | Control how your users interact with agents:<ul><li>Choose who can access agents</li><li>Choose which type of agents users are allowed to install</li></ul>  |  |
| 2  | [Share and publish Microsoft 365 Copilot agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps)  | Agent sharing methods:<ul><li>[Sideload agents for personal use](/copilot/microsoft-365/agent-framework/agent-policies/agent-sideload)</li><li>[Shared agent with others](/microsoft-365/admin/manage/manage-shared-agents?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json)</li><li>[Publish custom agents to your organization](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json#publish-agents)</li><li>[Submit agents to the marketplace](/copilot/microsoft-365/agent-framework/agent-policies/agent-submit-marketplace)</li></ul>  |  |

## Choose the right Copilot Studio experience

As an admin, you can configure and deploy out-of-the-box agents without having to create and publish a new agent. However, when your organization needs to customize Copilot functionality, members of your organization can create agents. Understand the different types of agents that can be created, shared, and deployed at your organization based on the method your organization uses to create agents. 

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | [Choose the right Copilot Studio experience](/microsoft-365-copilot/extensibility/copilot-studio-experience)  | Agent development tools:<ul><li>[Create SharePoint agents](https://support.microsoft.com/office/create-a-sharepoint-agent-d16c6ca1-a8e3-4096-af49-67e1cfdddd42)</li><li>[Use Copilot Studio (lite) to create declarative agents](/microsoft-365-copilot/extensibility/copilot-studio-lite)</li><li>[Use Copilot Studio (full) to create agents](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext)</li><li>[Use Microsoft 365 Agents Toolkit to create agents](/microsoft-365/developer/overview-m365-agents-toolkit?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json)</li></ul>  |  |
| 2  | [Plan your agent](/microsoft-365-copilot/extensibility/planning-guide)  | Define your objectives, technical requirements, costs, RAI considerations, and development approach. |  |
| 3  | [Consider licensing and cost options](/microsoft-365-copilot/extensibility/cost-considerations)  | Before you create an agent, consider the associcated licensing and consumption costs.  |  |
| 4  | [Set up your development environment](/microsoft-365-copilot/extensibility/prerequisites)  | If you creating a custom agent, consider how you will set up your development environment.  |  |

## Create agents in Copilot Studio (lite)

Using Copilot Studio (lite), members of your organization can create declarative agents that they can share across your organization. For more information, see [Create agents in Copilot Studio (lite)](/microsoft-365-copilot/extensibility/agents-overview).

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | [Understand Copilot Studio (lite) creation process](/microsoft-365-copilot/extensibility/copilot-studio-lite-build)  | Quickly build declarative agents using natural language or by configuring the agent.  |  |
| 2  | [Add knowledge sources to an agent](/microsoft-365-copilot/extensibility/copilot-studio-lite-build#add-knowledge-sources)  | Copilot Studio (lite) allows end users to configure knowledge sources for the agent to reference.  |  |
| 3  | [Add capabilities to an agent](/microsoft-365-copilot/extensibility/copilot-studio-lite-build#add-capabilities)  | Copilot Studio (lite) allows end users to add and configure capabilities, such as the Code interpreter and Image generator.  |  |
| 4  | [Share and manage agents](/microsoft-365-copilot/extensibility/copilot-studio-lite-share-manage-agent)  | End users can share and manage agents they create using Copilot Studio (lite). |  |
| 5  | [Download agent ZIP file and provide to admin](/microsoft-365-copilot/extensibility/copilot-studio-lite-share-manage-agent#deploy-an-agent-via-zip-package)  | Copilot Studio (lite) provides an option to download a Zip file for manual deployment. |  |

## Understand application lifecycle management with Copilot Studio (full)

Application lifecycle management (ALM) is the lifecycle management of applications and agents, which includes governance development and maintenance. You can implement ALM using Power Apps, Power Automate, Power Pages, Microsoft Copilot Studio, and Microsoft Dataverse. Key areas of ALM include governance, application development, and maintenance. For more information, see [Application lifecycle management (ALM) with Microsoft Power Platform](/power-platform/alm/).

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | [Plan your environment strategy for your agent]( /power-platform/alm/environment-strategy-alm)  | Understand environment principles related to ALM.  |  |
| 2  | [Understand solution concepts related to your agent]( /power-platform/alm/solution-concepts-alm)  | Understand solution concepts related to ALM.  |  |
| 3  | Consider agent related change management and versioning  | Understand agent related version control, changelog, and rollback procedures for agent deployments.  |  |
| 4  | [Understand key concepts for Copilot Studio security and governance](/microsoft-copilot-studio/security-and-governance)  | Understand security and governance controls and processes.  |  |
| 5  | [Understand key Copilot Studio configuration settings](/microsoft-copilot-studio/guidance/sec-gov-config-settings)  | Review tenant-level, environment-level, and agent-level settings in Copilot Studio.  |  |

## Create agents in Copilot Studio (full)

When you need to provide powerful AI assistants that retrieve real-time insights and act on behalf of users, as well as create specialized workflows, you can use Copilot Studio to create custom agents.

| Step  | Task  | Description  |  |
|---|---|---|---|
| 1  | [Understand how to extend Microsoft 365 Copilot with agents](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext)  | Learn how to create and configure a custom Agent.  |  |
| 2  | [Add knowledge sources](/microsoft-copilot-studio/knowledge-copilot-studio)  | Knowledge sources allow your agents to provide relevant information and insights for your customers.  |  |
| 3  | [Add tools](/microsoft-copilot-studio/advanced-plugin-actions)  | Tools expand the functionality of your agent, allowing it to perform various actions in response to user requests or autonomous triggers. |  |
| 4  | [Add other agents](/microsoft-copilot-studio/authoring-add-other-agents)  | Copilot Studio lets you enhance your agents by connecting them to other agents, allowing them to hand off user interactions or respond to autonomous triggers. |  |
| 5  | [Add topics](/microsoft-copilot-studio/authoring-create-edit-topics)  | A topic defines how an agent conversation progresses.  |  |
| 6  | [Add triggers](/microsoft-copilot-studio/authoring-triggers-about)  | Event triggers allow your agent to act autonomously in response to the defined event occurring.  |  |
| 7  | [Publish an agent](/microsoft-copilot-studio/publication-fundamentals-publish-channels)  | You can publish agents to engage with your customers on multiple platforms or channels, such as live websites, mobile apps, Microsoft 365 Copilot or messaging platforms like Teams and Facebook.  |  |

