---
title: Understand agent details in Microsoft 365 admin center
description: Understand agent details in Microsoft 365 admin center.
#customer intent: Learn about the agent details that are provided in Microsoft 365 admin center.
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

# Understand agent details in Microsoft 365 admin center

You can monitor, manage, and govern your inventory of agents available for your organization from [Microsoft 365 admin center](https://admin.microsoft.com/). The **All agents** list provides key information related to agents in your tenant, including such information as platform, status, and high risks.

The **All agents** list provides tabs to help you view agent details:
- **Registry** - This provides a list of all agents available to your organization. You can filter this list to help you manage specific agents. Select individual agents to view agent details and manage agent actions.
- **Map** - This provides a visualization of agents available for your organization. This map allows you to filter and select groups of agents. Use this map to better manage and understand the agents available in your tenant.
- **Requests** - This provides a list of agents that require your review and action. Members of your organizaton can request agents to be made available to members of your organization.

The agent **Registry** lists all agents that are available to your organization, including:
- **Microsoft agents** - Built and maintained by Microsoft.
- **External partner-built agents** - Built by trusted non-Microsoft developers.
- **Shared by creator** - Agents created and shared by individual users or developers in your organization.
- **Published by your org** - Custom agents approved and published by your organization for broader use.

## Agent details

### Manage agents with embedded file content as a knowledge source

Agent creators can use [Agent Builder in Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/agent-builder-build-agents) to upload files for the agent to use as knowledge. Copilot stores the uploaded files in tenant-owned [SharePoint Embedded](/sharepoint/dev/embedded/overview) containers. It then embeds the file content as knowledge for the agent to use in responses. For more information, see [Embedded file content](/microsoft-365-copilot/extensibility/agent-builder-add-knowledge#embedded-file-content).

> [!IMPORTANT]
>
> [Microsoft Purview Information Barriers (IB)](/purview/information-barriers) isn't supported on embedded files. Any user who can access the agent can see responses grounded in the embedded file content.

This article explains how to handle embedded files, how you can manage agents and containers, and what to expect with sensitivity labels and deletion workflows.

#### Supported file types and limits

:::image type="content" source="../../media/knowledge-agent-upload.png" alt-text="Screenshot showing the screen to upload a file as a knowledge source for an agent." lightbox="../../media/knowledge-agent-upload.png":::

Embedded knowledge agents support uploading files as knowledge sources. Copilot only uses the text content of these files for grounding.

#### Supported file types

- .doc, .docx
- .ppt, .pptx
- .xls, .xlsx
- .pdf
- .txt

#### Maximum file size

| File type | Maximum file size |
| --- | --- |
| .doc, .ppt, .xls, .xlsx, .txt | 150 MB |
| .docx, .pptx, and .pdf | 512 MB |

Files that exceed these limits aren't accepted.

#### Maximum number of files

Users can upload up to 20 files per agent.

#### SharePoint Embedded containers

When you upload a file to an agent, Copilot stores the file in a SharePoint Embedded container. The Microsoft 365 service automatically creates this container and your organization owns it. The container appears in the SharePoint admin center and PowerShell under the application name Declarative Agent.

> [!IMPORTANT]
>
> Don't delete these containers. Deleting these containers might break the functionality of agents that rely on them.

#### View agent metadata

In the **All agents** page in the Microsoft 365 admin center, you can filter the agent inventory to view only agents that use embedded files as knowledge sources.

:::image type="content" source="../../media/knowledge-agent-filter.png" alt-text="Screenshot showing the agents and connectors page in the Microsoft 365 admin center with the filters highlighted." lightbox="../../media/knowledge-agent-filter.png":::

For each agent, the following metadata is available:

- **File name** - The name of the uploaded file.
- **File sensitivity** - The sensitivity label applied to the file.
- **SharePoint container ID** - The unique identifier for the container storing the file.

This metadata helps you track and audit the use of embedded content across agents.

#### Sensitivity labels and access control

The service applies sensitivity labels to the embedded content in the agent based on the most restrictive label from the uploaded files. The following rules determine how the service applies sensitivity labels:

- Whichever of the following labels are more restrictive:

  - Most restrictive sensitivity label of all files uploaded. For example, the highest priority of the labels on the uploaded files.
  - If your organization configured and applied a [default sensitivity label policy](/purview/default-sensitivity-labels-policies#default-sensitivity-label-policy).

- If a default sensitivity labeling policy is in place, the service automatically assigns a label.

- The service only applies sensitivity labels if:

  - You create the agent by using Microsoft 365 Copilot Agent Builder.
  - The agent includes embedded files.

You can view the sensitivity label for each agent in the **Overview** tab of the Microsoft 365 admin center.

:::image type="content" source="../../media/knowledge-agent-idea.png" alt-text="Screenshot showing the overview details of an agent." lightbox="../../media/knowledge-agent-idea.png":::

#### User access and visibility

- If a user doesn't have extract rights to any of the sensitivity labels applied to the uploaded files, they can't access the agent.

- If a user has extract rights, they can view the agent's sensitivity label in the agent details pane.

For more information, see [Sensitivity labels for agent embedded content](/microsoft-365-copilot/extensibility/copilot-studio-lite-knowledge#sensitivity-labels-for-agent-embedded-content).



#### Researcher with Computer Use admin configuration

> [!IMPORTANT]
>
> **Researcher with Computer Use** is only for Frontier tenants.

For **Researcher with Computer Use** onboarding instructions, see the following short video:

> [!VIDEO https://www.youtube.com/embed/N3vLF9mnd8w?si=XJaYnCQYNy_CeuFc]

**Researcher with Computer Use** is a powerful extension that builds on the capabilities of the Researcher agent. By using Computer Use, the Researcher agent can securely interact with public, gated, and interactive web content through a virtual computer. By using this method, users can uncover deeper insights, take action, and generate richer reports grounded in both their work data and the web. For more information, see [Use Researcher with Computer use in Microsoft 365 Copilot](https://support.microsoft.com/topic/1f274537-6648-46e8-8264-052a49b92af4).

:::image type="content" source="../../media/agents/researcher.png" alt-text="Screenshot showing Researcher with Computer Use." lightbox="../../media/agents/get-started.png":::

##### Configure admin settings for Researcher agent with Computer Use

To configure admin settings for **Researcher agent with Computer Use**, follow these steps:

1. Go to the **Microsoft Admin Controls (Microsoft 365 admin center) Agents** page.

1. In the left navigation pane, select **Researcher under Agents**, and check if there's another tab for **Computer Use**.

1. Customize users that have access to **Researcher with Computer Use**.

    :::image type="content" source="../../media/agents/researcher-step-2.png" alt-text="Screenshot showing the Researcher for Computer Use page." lightbox="../../media/knowledge-agent-idea.png":::

   - There are three options for configuring who has access to the experience:

     1. Allow all users in your organization.
     1. Allow specific users or groups only.
     1. No users in your organization.

    :::image type="content" source="../../media/agents/researcher-step-3-a.png" alt-text="Screenshot showing the Computer Use option." lightbox="../../media/knowledge-agent-idea.png":::

   - For users that have this option disabled, the **Computer Use** option is grayed out.

    :::image type="content" source="../../media/agents/researcher-step-3-b.png" alt-text="Screenshot showing the Computer Use option greyed out." lightbox="../../media/knowledge-agent-idea.png":::

1. Configure Work access for **Researcher with Computer Use**:

    - The **Work** option allows users to toggle on **Work in the Sources** menu, allowing Researcher agent to use a user's work content with Computer Use. For example, emails, chats, and files.

    - When enabled by admins, users must still manually toggle on Work access.
        :::image type="content" source="../../media/agents/researcher-step-4-a.png" alt-text="Screenshot showing the Work option." lightbox="../../media/knowledge-agent-idea.png":::

    - When disabled, the **Work** source appears grayed out and isn't selectable.
        :::image type="content" source="../../media/agents/researcher-step-4-b.png" alt-text="Screenshot showing the Work option greyed out." lightbox="../../media/knowledge-agent-idea.png":::

1. Select which websites are allowed for **Computer Use**:

   - There are three options for configuring websites the virtual device can access:

     1. All websites.

     1. Allow specific URLs or domains only.

     1. Exclude specific URLs or domains.

   - You can allow **All websites**, block some websites by using the **Exclude specified** option, or only allow certain sites by using the **Allow specified** option.

##### Learn more about Researcher with Computer Use

- [Introducing Researcher with Computer Use in Microsoft 365 Copilot](https://techcommunity.microsoft.com/blog/microsoft365copilotblog/introducing-researcher-with-computer-use-in-microsoft-365-copilot/4464766).
- [Get started using Researcher with Computer Use](https://support.microsoft.com/topic/get-started-using-researcher-with-computer-use-in-microsoft-365-copilot-frontier-1f274537-6648-46e8-8264-052a49b92af4).
- [Frequently asked questions for Researcher with Computer Use](/copilot/microsoft-365/researcher-agent-computer-use-faq).

#### Agent metadata in the Microsoft 365 admin center

:::image type="content" source="../../media/agents/career-coach.png" alt-text="Screenshot showing the Career Coach for an agent." lightbox="../../media/agents/details.png":::

You can access key metadata for Copilot agents in **Agents** > **All Agents**. When you select an agent, you see the metadata in the **Data & tools** tab.

The metadata includes details such as the agent's capabilities, data sources, and custom actions. Example data sources include OneDrive and SharePoint files and sites, or Graph connectors. Metadata is only for custom agents, which are designed to perform specific tasks based on predefined rules and configurations.

