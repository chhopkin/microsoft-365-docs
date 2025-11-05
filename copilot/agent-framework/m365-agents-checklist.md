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

This checklist is intended to assist admins with the successful deployment of Copilot agent governance. It's structured in a checklist format, providing a comprehensive guide for a streamlined setup process.

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
| 1  | [Manage access to M365 Copilot agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json#manage-access-to-copilot-agents)  | Control how your users interact with agents:<ul><li>Choose who can access agents</li><li>Choose which type of agents users are allowed to install</li></ul>  |  |
| 2  | [Share and publish M365 Copilot agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps)  | Agent sharing methods:<ul><li>[Sideload agents for personal use](/copilot/microsoft-365/agent-framework/agent-policies/agent-sideload)</li><li>[Shared agent with others](/microsoft-365/admin/manage/manage-shared-agents?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json)</li><li>[Publish custom agents to your organization](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json#publish-agents)</li><li>[Submit agents to the marketplace](/copilot/microsoft-365/agent-framework/agent-policies/agent-submit-marketplace)</li></ul>  |  |

## Choose the right Copilot Studio experience

As an admin, you can configure and deploy out-of-the-box agents without having to create and publish a new agent. However, when your organization needs to customize Copilot functionality, members of your organization can create agents. Understand the different types of agents that can be created, shared, and deployed at your organization based on the method your organization uses to create agents. For more information, see [Choose the right Copilot Studio experience](/microsoft-365-copilot/extensibility/copilot-studio-experience).

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | Create SharePoint agents  | For more information, see [Create a SharePoint agent](/office/create-a-sharepoint-agent-d16c6ca1-a8e3-4096-af49-67e1cfdddd42?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json).  |  |
| 2  | Use Copilot Studio (lite) to create declarative agents  | For more information, see [Use Copilot Studio to build declarative agents](/microsoft-365-copilot/extensibility/copilot-studio-lite).  |  |
| 3  | Use Copilot Studio (full) to create agents  | For more information, see [Extend Microsoft 365 Copilot with agents](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext).  |  |
| 4  | Use Microsoft 365 Agents Toolkit to create agents  | For more information, see [Microsoft 365 Agents Toolkit](/microsoft-365/developer/overview-m365-agents-toolkit?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json).  |  |

## Create agents in Copilot Studio (lite)

Using Copilot Studio (lite), members of your organization can create declarative agents that they can share across your organization. For more information, see [Create agents in Copilot Studio (lite)](/microsoft-365-copilot/extensibility/agents-overview).

| Step  | Task  | Description  | Administrator  |
|---|---|---|---|
| 1  | Share and manage agents  | End users can share and manag agents they create using Copilot Studio (lite). For more information, see [Share and manage agents](/microsoft-365-copilot/extensibility/copilot-studio-lite-share-manage-agent).  |  |
| 2  | Download agent ZIP file and provide to admin  | Copilot Studio (lite) provides an option to download a Zip file for manual deployment. For more information, see [Deploy an agent via ZIP package](/microsoft-365-copilot/extensibility/copilot-studio-lite-share-manage-agent#deploy-an-agent-via-zip-package).  |  |
| 3  | Understand Copilot Studio (lite) creation process  | Quickly build declarative agents using natural language or by configuring the agent. For more information, see [Build agents with Copilot Studio](/microsoft-365-copilot/extensibility/copilot-studio-lite-build)  |  |
| 4  | Add knowledge sources to an agent  | Copilot Studio (lite) allows end users to configure knowledge sources for the agent to reference. For more information, see [Add knowledge sources](/microsoft-365-copilot/extensibility/copilot-studio-lite-build#add-knowledge-sources).  |  |
| 5  | Add capabilities to an agent  | Copilot Studio (lite) allows end users to add and configure capabilities, such as the Code interpreter and Image generator. For more information, see [Add capabilities](/microsoft-365-copilot/extensibility/copilot-studio-lite-build#add-capabilities).  |  |