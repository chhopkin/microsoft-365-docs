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

As an admin, you can configure and deploy out-of-the-box agents without having to create and publish a new agent. However, when your organization needs to customize Copilot functionality, members of your organization can create agents. Understand the different types of agents that can be created, shared, and deployed at your organization based on the method your organization uses to create agents. For more information, see [Choose the right Copilot Studio experience](/microsoft-365-copilot/extensibility/copilot-studio-experience).

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | [Create SharePoint agents](https://support.microsoft.com/office/create-a-sharepoint-agent-d16c6ca1-a8e3-4096-af49-67e1cfdddd42)  | Agents created with Microsoft SharePoint provide a simple option to query content from specific sites, folders, or files within Microsoft SharePoint or Microsoft Teams.|  |
| 2  | [Use Copilot Studio (lite) to create declarative agents](/microsoft-365-copilot/extensibility/copilot-studio-lite)  | Members of your organization can create declarative agents using Microsoft Copilot Studio (lite) in the Microsoft 365 Copilot app. |  |
| 3  | [Use Copilot Studio (full) to create agents](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext)  | Microsoft Copilot Studio (full) empowers low-code developers (“makers”) to build declarative agents or custom engine agents.  |  |
| 4  | [Use Microsoft 365 Agents Toolkit to create agents](/microsoft-365/developer/overview-m365-agents-toolkit?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json)  | The Microsoft 365 Agents Toolkit is a suite of tools that developers within your organization can use to build enterprise-ready agents and apps.  |  |

## Create agents in Copilot Studio (lite)

Using Copilot Studio (lite), members of your organization can create declarative agents that they can share across your organization. For more information, see [Create agents in Copilot Studio (lite)](/microsoft-365-copilot/extensibility/agents-overview).

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | [Share and manage agents](/microsoft-365-copilot/extensibility/copilot-studio-lite-share-manage-agent)  | End users can share and manage agents they create using Copilot Studio (lite).   |  |
| 2  | [Download agent ZIP file and provide to admin](/microsoft-365-copilot/extensibility/copilot-studio-lite-share-manage-agent#deploy-an-agent-via-zip-package)  | Copilot Studio (lite) provides an option to download a Zip file for manual deployment. |  |
| 3  | [Understand Copilot Studio (lite) creation process](/microsoft-365-copilot/extensibility/copilot-studio-lite-build)  | Quickly build declarative agents using natural language or by configuring the agent.  |  |
| 4  | [Add knowledge sources to an agent](/microsoft-365-copilot/extensibility/copilot-studio-lite-build#add-knowledge-sources)  | Copilot Studio (lite) allows end users to configure knowledge sources for the agent to reference.  |  |
| 5  | [Add capabilities to an agent](/microsoft-365-copilot/extensibility/copilot-studio-lite-build#add-capabilities)  | Copilot Studio (lite) allows end users to add and configure capabilities, such as the Code interpreter and Image generator.  |  |

## Understand application lifecycle management with Copilot Studio (full)

Application lifecycle management (ALM) is the lifecycle management of applications and agents, which includes governance development and maintenance. You can implement ALM using Power Apps, Power Automate, Power Pages, Microsoft Copilot Studio, and Microsoft Dataverse. Key areas of ALM include governance, application development, and maintenance. For more information, see [Application lifecycle management (ALM) with Microsoft Power Platform](/power-platform/alm/).



