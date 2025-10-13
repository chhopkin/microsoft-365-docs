---
title: Microsoft 365 Copilot agents admin guide
f1.keywords:
ms.author: erikre
author: ErikRe
manager: dansimp
ms.date: 10/13/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Learn about administering and deploying Microsoft 365 Copilot agents.
---

# Microsoft 365 Copilot agents admin guide

When you add [Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-overview) to your qualifying Microsoft 365 for business subscription, you provide generative AI capabilities to your organization. With these capabilities, you help enhance your organization’s productivity, improve accuracy, and provide personalized assistance. 

In addition to the generative AI capabilities provided by Microsoft 365 (Microsoft 365) Copilot, you can extend your AI implementation to include agents. Agents allow you to customize your Copilot experience. You can connect agents to your organization’s knowledge and data sources to help members of your organization answer questions, automate tasks, and run business processes. These AI-driven agents can perform various tasks, working alongside you to offer suggestions, automate repetitive tasks, and provide insights to help you and your organization make more informed decisions.

This guide:
- Helps you determine which Copilot agent capabilities your organization needs
- Helps you understand where members of your organization view agents
- Provides guidance to help you understand how to create agents and the different capabilities each development environment offers for agents
- Recommends options for organization-wide agent access and sharing policies
- Helps you understand how to manage, assign, and deploy agents
- Provides details about Copilot and agent security, compliance, and privacy

> [!NOTE]
> You must have specific permissions for your tenant to configure, manage, assign, and deploy agents in Copilot Control System within Microsoft 365 admin center. For more information, see [Admin permissions](m365-agents-admin-guide.md).

## Identify your Copilot licensing scenario

Organizations typically deploy a combination of Microsoft 365 Copilot Chat and Microsoft 365 Copilot. Before you get started, it's important to understand the differences between these two offerings when it comes to deploy and using agents.

Microsoft 365 Copilot Chat is available at no additional cost for all Microsoft Entra account users with a Microsoft 365 or Office 365 subscription. Members of your organization can use agents that are available at no additional cost from the Agent Store. You, as the administrator of your organization, would also need to enable these agents. If your organization requires agents that incorporate your organization’s data, you can provide access to [agents](/copilot/agents) that are billed based on metered consumption. For more information about Microsoft 365 Copilot Chat, see [Requirements and considerations for Microsoft 365 Copilot Chat admins]().

Microsoft 365 Copilot, which includes Microsoft 365 Copilot Chat, requires a Microsoft 365 [Business](/microsoft-365/business/with-copilot-plans-and-pricing) or [Enterprise](/microsoft-365/enterprise/microsoft365-plans-and-pricing) plan. It includes AI-powered chat grounded in both web-based and work-based data, as well as the capabilities of Microsoft 365 Copilot Chat. In addition, Microsoft 365 Copilot unlocks embedded Copilot features in Word, Excel, Outlook, and Teams. Additionally, your organization can use [custom agents](/microsoft-365-copilot/extensibility/overview-custom-engine-agent). For more information about deploying Microsoft 365 Copilot, including setting up a Microsoft 365 Copilot rollout plan, see [Minimum requirements to deploy Microsoft 365 Copilot in your organization](/copilot/microsoft-365/microsoft-365-copilot-min-reqs?branch=kwekua-copilot-min-reqs).

Each Copilot option offers different capabilities. For a list of these capabilities, see [Agent capabilities for Microsoft 365 users](/microsoft-365-copilot/extensibility/prerequisites#agent-capabilities-for-microsoft-365-users).

> [!IMPORTANT]
> IMPORTANT:
If you’re already using Copilot, view your [license plan](/copilot/microsoft-365/microsoft-365-copilot-licensing) to confirm whether your organization is using Microsoft 365 Copilot Chat or Microsoft 365 Copilot. If you're new to Microsoft 365 Copilot, see the [Microsoft 365 Copilot adoption guide and overview for IT admins](/copilot/microsoft-365/microsoft-365-copilot-enablement-resources).

### Understand available agent options

To best understand your overall Copilot deployment, you must understand the options available for Copilot agents. Different agent capabilities are available based on whether you choose to deploy Microsoft 365 Copilot Chat without usage billing, deploy Microsoft 365 Copilot Chat with usage billing, or deploy Microsoft 365 Copilot.

> [!NOTE]
> Agents that access shared tenant data, such as SharePoint or Graph Connector content, are billed based on metered consumption. Agents utilizing metered consumption are off by default for users in Microsoft 365 Copilot Chat.

✅ **Task: Task: Determine which of the following Copilot options your organization needs:**
- **Microsoft 365 Copilot Chat (no usage billing)**
- **Microsoft 365 Copilot Chat (usage billing)**
- **Microsoft 365 Copilot (licensed)**

#### Option 1 – Agents with Microsoft 365 Copilot Chat (no usage billing)

Microsoft 365 Copilot Chat is included in your Microsoft 365 subscription at no additional charge for all [Microsoft Entra](/entra/fundamentals/what-is-entra) account users with a Microsoft 365 subscription.  It provides access to public web-based Copilot Chat. This option also provides access to [declarative agents](/microsoft-365-copilot/extensibility/overview-declarative-agent), grounded in instructions and public websites, at no additional cost. These agents are available in the [Agent Store in Microsoft 365 Copilot](/microsoft365dev/introducing-the-agent-store-build-publish-and-discover-agents-in-microsoft-365-copilot/) based on your organization’s store settings for Teams and Microsoft 365 apps. This option is ideal for occasional users of Copilot and agents.

#### Option 2 – Agents with Microsoft 365 Copilot Chat (usage billing)

Microsoft 365 Copilot Chat can also be used with a flexible plan for organizations to access Copilot services. You can choose an optional [pay-as-you-go access](/copilot/microsoft-365/pay-as-you-go/overview) to work-based chat and deploy declarative and custom agents. Custom agents are those that use Microsoft Graph grounding (tenant data). To enable agents that utilize metered consumption for users in Copilot Chat, admins need to set up or use an existing Copilot Studio subscription. For more information, see [Using agents in Microsoft 365 Copilot Chat](/copilot/agents).

This option gives you and your organization a method to understand your organization’s usage patterns. By understanding how your organization uses the capabilities of Microsoft 365 Copilot Chat, along with pay-as-you-go work-based chat and advanced agents, you can determine if prepaid licenses make financial sense for your business.

#### Option 3 – Agents with Microsoft 365 Copilot (licensed)

Microsoft 365 Copilot offers chat grounded in both web-based and work-based data, as well as the capabilities of Microsoft 365 Copilot Chat. In addition, Microsoft 365 Copilot unlocks embedded Copilot features in Word, Excel, Outlook, and Teams. Also, with your Microsoft 365 Copilot license, your organization can use [custom agents](/microsoft-365-copilot/extensibility/overview-custom-engine-agent). Microsoft 365 Copilot allows you to create, deploy, use, and share agents to extend Microsoft 365 Copilot capabilities. This includes all agents from simple prompt-based agents to more advanced, autonomous agents. Additionally, when you purchase a license for Microsoft 365 Copilot, your organization has access to use additional capabilities, such as [Researcher](https://go.microsoft.com/fwlink/?linkid=2329838) and [Analyst](https://go.microsoft.com/fwlink/?linkid=2329729).

> [!NOTE]
> To purchase Microsoft 365 Copilot, your organization must have a qualifying [Microsoft 365 plan for enterprise or business](/copilot/microsoft-365/microsoft-365-copilot-licensing#microsoft-365-copilot-license). Microsoft 365 Copilot is available as an [add-on plan](/microsoft-365/copilot#plans). Your organization can choose which license best meets your organization’s requirements. If your organization’s account doesn't have the right plan, you can purchase a new plan or potentially [upgrade your existing plan](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan?view=o365-worldwide).

## View available agents

By default, Microsoft and Microsoft partners provide ready-to-use agents that you can quickly integrate and deploy when Microsoft 365 Copilot Chat and Microsoft 365 Copilot. In addition, you can integrate and deploy agents created by members of your organization.

When using a Microsoft 365 subscription, you have agents available with your Microsoft 365 apps, such as Word and Excel. You can also view agents directly in the Microsoft 365 Copilot app.

✅ **Task: Understand how to view agents in Microsoft 365 Copilot and Microsoft Teams.**

### View agents in Microsoft 365 Copilot

Examples of Microsoft agents that are available at no additional cost and are included with Microsoft 365 Copilot Chat include Writing Coach, Idea Coach, Prompt Coach, Career Coach, and Learning Coach. To view additional examples, see [Microsoft 365 Copilot Chat agent demo videos](https://www.youtube.com/playlist?list=PLXPr7gfUMmKyJpxEJ_kGOjOumENieobXC).

To view prebuilt agents in Microsoft 365 Copilot Chat:  

1. Open Microsoft 365 Copilot by selecting the Microsoft 365 Copilot app from your taskbar. Alternatively, navigate to [https://m365.cloud.microsoft](https://m365.cloud.microsoft/) in your browser.
2. In the Microsoft 365 Copilot app, select **Agents** > **All agents** to view the **Agent Store**. Alternatively, in the browser under **Agents**, select **All agents** to view the **Agent Store**. 

In the **Agent Store** you can view the agents available to you. You can view agents built by Microsoft, those built by your organization, as well as those that are popular within your organization.

:::image type="content" source="/media/m365-agents-admin-guide/agent-store-explore.png" alt-text="Screenshot of exploring the Agent Store in Microsoft 365 Copilot." lightbox="/media/m365-agents-admin-guide/agent-store-explore.png":::

> [!NOTE]
> If members of your organization don’t see any options to view agents, and their work or school account has a qualifying Microsoft 365 subscription, there may be no agents that have been deployed to your tenant. Additionally, all or some of the Copilot features may have been turned off, or Copilot might not be available in your market.

### View agents in Microsoft Teams

To view prebuilt agents in Microsoft Teams:  

1. Open the Microsoft Teams app and select **Copilot**.
2. Select **All agents** to view the **Agent Store**.

:::image type="content" source="/media/m365-agents-admin-guide/agent-store-all.png" alt-text="Screenshot of all agents in the Agent Store in Microsoft 365 Copilot." lightbox="/media/m365-agents-admin-guide/agent-store-all.png":::

## Create agents

As an admin, you can configure and deploy out-of-the-box agents without having to create and publish a new agent. However, when your organization needs to customize Copilot functionality, such extending Copilot’s knowledge, automate workflows, or deliver tailored user experiences, users, and developers at your organization can build agents that you can manage and deploy. 

✅ **Task: Determine whether your organization requires the capability to create agents. Understand the different types of agents that can be created, shared, and deployed at your organization.**

There are two types of approaches to building agents for Microsoft 365 Copilot. Users and developers at your organization can use the [declarative](/microsoft-365-copilot/extensibility/agents-overview#declarative-agents) approach or the [custom engine agents](/microsoft-365-copilot/extensibility/agents-overview#custom-engine-agents). Because both approaches use Copilot's AI infrastructure, model, and orchestrator, they adhere to the security, compliance, and Responsible AI (RAI) requirements for Microsoft 365.

Declarative agents enable members of your organization to configure Copilot for specific scenarios. These agents are designed to be used by individuals. Also, these agents are limited to Copilot's orchestrator and models, where they use your instructions. Declarative agents rely on user-initiated interactions. Members of your organization can create declarative agents using Microsoft SharePoint and Copilot Studio (lite). Also, a [Copilot agent](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions#what-are-copilot-agents-tools-knowledge-and-suggested-prompts), created in [Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) (full), is equivalent to a declarative agent created in Microsoft 365 Copilot (lite). For more information, see [declarative agents](/microsoft-365-copilot/extensibility/agents-overview#declarative-agents).

Custom engine agents are fully customized AI assistants. When members of your organization build a custom engine agent, they can collaborate with a group or create these type of agents on their own. They can choose the AI models and orchestration as well. Custom engine agents also allow members of your organization to enable triggering actions automatically, even without direct user input. Custom engine agents must be published and approved by your organization, such as an admin, before they're available to your organization.  Members of your organization can create custom engine agents using [Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) (full) and  Microsoft 365 Agents Toolkit. For more information, see [custom engine agents](/microsoft-365-copilot/extensibility/agents-overview#custom-engine-agents).

✅ **Task: Understand the environments and tools available when creating agents, as well as the capabilities that each offer your organization. Understand these environment allows you to better understand how different agents can be managed and deployed.**

### Prerequisites

Before your organization creates a new agent, first consider your organization’s objectives, technical requirements, costs, Responsible AI (RAI) considerations, and compliance factors. For more information, see Microsoft 365 Copilot extensibility planning guide.

When Copilot itself doesn’t fully address your organization’s requirements out-of-the-box, consider building an agent. Agents allow you and your end users to extend Copilot’s knowledge, automate complex workflows, and deliver tailored user experiences.

Your organization can create agents for Microsoft Copilot using several different methods involving tools and environments:

- Microsoft SharePoint
- Microsoft Copilot Studio (lite)
- Microsoft Copilot Studio (full)
- Microsoft 365 Agents Toolkit

For information related to extending Microsoft 365 Copilot, see [Set up your development environment for Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/prerequisites) and [Validation guidelines for agents](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/review-copilot-validation-guidelines#description?context=/microsoft-365-copilot/extensibility/context).

### Microsoft SharePoint

Members of your organization (end users) can create agents using Microsoft SharePoint. Agents created with SharePoint provide a simple option to query content from specific sites, folders, or files within SharePoint or Teams chats. Members of your organization can build SharePoint agents if they have access to SharePoint and the tenant has been enabled as pay-as-you-go for SharePoint, or they have a Microsoft 365 Copilot license.

The agents members of your organization create with SharePoint can be accessed using SharePoint and Teams Chat. These agents can be shared based on existing user permissions and security settings. 

For more information, see [Get started with SharePoint agents](/sharepoint/get-started-sharepoint-agents) and [Manage access to SharePoint agents](/sharepoint/manage-access-agents-in-sharepoint).

### Copilot Studio (lite)

Using Copilot Studio (lite) in Microsoft 365 Copilot Chat and SharePoint, members of your organization (end users) can create declarative agents. This out-of-the-box solution works with your existing data and can be made available to end users at your organization. End users can query organization knowledge contained in SharePoint sites, folders, and files, as well as search general web content. Data can also be made available using Microsoft Graph connectors.

Copilot Studio (lite) is available through Microsoft 365 Copilot Chat if your organization’s tenant has enabled pay-as-you-go for Copilot Studio, or if your organization has a Microsoft 365 Copilot license.

In addition, agents created with Copilot Studio (lite) are shareable across your organizations by end users. The capabilities of agents vary depending on your billing model. Your consumption model might allow agents available at no additional cost, pay-as-you-go agents, or agents licensed with Microsoft 365 Copilot.

To get started quickly, view the following step-by-step walkthrough video:

[Create and publish your first agent](https://youtu.be/_aJAOTOvWxI)

> [!TIP]
> End users can get started quickly using templates included with Copilot Studio (lite). These templates apply design guidelines and industry best practices. For more information, see [Copilot Studio agent templates](/microsoft-365-copilot/extensibility/agent-builder-templates).

For more information, see [Build agents with Copilot Studio (lite)](/microsoft-365-copilot/extensibility/copilot-studio-agent-builder-build).

### Microsoft Copilot Studio (full)

Microsoft Copilot Studio (full) empowers low-code developers (“makers”) to build declarative agents or custom engine agents. Declarative agents created in Copilot Studio are called [Copilot agents](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions#what-are-copilot-agents-tools-knowledge-and-suggested-prompts) and follow a specific development path within Copilot Studio. [Custom engine agents](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions#what-are-copilot-agents-tools-knowledge-and-suggested-prompts) (also known as Custom agents) integrate with custom data, other agents, decision paths, data source connectors, and [automation](/microsoft-copilot-studio/flows-overview). These agents can be deployed internally or externally and used with Microsoft 365 Copilot licenses or pay-as-you-go models. Critically, leveraging Microsoft Graph connectors to expose shared organizational data enables Copilot agents to reason over enterprise-wide information, unlocking deeper insights and driving transformational productivity outcomes. Additionally, these agents can be designed to use generative orchestration and generative answers. Agents created using Copilot Studio (full) can be used within Microsoft 365 Copilot Chat and Microsoft 365 Copilot based on Microsoft 365 Copilot licenses, as well as a pay-as-you-go scenario. 

> [!NOTE]
> Microsoft Copilot Studio is part of the Power Platform product set. Using the [Power Platform admin center](/power-platform/admin/admin-documentation?tabs=new), admins can manage agent development settings and agent governance controls for Custom Engine Agents for your organization. For related information, see [Track, manage, and scale Copilot adoption in the Power Platform](/power-platform/admin/copilot/copilot-hub?tabs=new) and [Key Copilot configuration settings](/microsoft-copilot-studio/guidance/sec-gov-config-settings).

For more information, see [Copilot Studio overview](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio), [Copilot Studio documentation](/microsoft-copilot-studio/), and [Microsoft Copilot Studio](/microsoft-copilot/microsoft-copilot-studio).

### Microsoft 365 Agents Toolkit

[Microsoft 365 Agents Toolkit](https://aka.ms/M365AgentsToolkit) is a suite of tools that developers within your organization can use to build enterprise-ready agents and apps. Agents developed using the Toolkit have a greater capability to be [shared and published](m365-agents-admin-guide.md). These agents work across Microsoft 365 Copilot, Teams, Office, web, and other third-party messaging channels. It streamlines the development of production AI agents and apps with built-in project scaffolding, testing, deployment, and integration with AI tools including Microsoft 365 Agents SDK, Azure AI Foundry, and TypeSpec for Copilot.

For more information about developing agents, see [Microsoft 365 Agents Toolkit](/microsoft-365/developer/overview-m365-agents-toolkit?toc=%2Fmicrosoftteams%2Fplatform%2Ftoc.json&bc=%2Fmicrosoftteams%2Fplatform%2Fbreadcrumb%2Ftoc.json).
















