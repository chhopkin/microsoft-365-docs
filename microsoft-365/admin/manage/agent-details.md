---
title: Understand agent details in Microsoft 365 admin center
description: Understand agent details in Microsoft 365 admin center.
#customer intent: Learn about the agent details that are provided in Microsoft 365 admin center.
f1.keywords:
- NOCSH
ms.author: erikre
author: ErikRe
manager: scotv
ms.date: 04/13/2026
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

You can view and manage agent details for each agent listed in the agent registry within [Microsoft 365 admin center](https://admin.microsoft.com/). When you select an agent from the list, you can view these details in a fly-out pane. These details are provided based on tabs. Each tab is provided based on the selected agent's capabilities. For example, if an agent is designed to provide information and answers from another agents, the **Connected Agents** tab may be provided. In addition to providing information about an agent in the details fly-out pane, you can also select actions for the agent, such as **Install** or **Block**.

:::image type="content" source="../../media/agents/agent-details-02.png" alt-text="Screenshot showing the details for a specific agent." lightbox="../../media/agents/agent-details-02.png":::

## View agent details

To access the details available for an agent, use the following steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).
2. Navigate to **Agents** > **All agents**.
  The agent **Registry** tab will be selected.
3. Select an agent from the **Registry** list.
  The agent details will be displayed.

When you select an agent from the **Registry**, the details fly-out pane displays common actions available for the agent directly below the agent's name. Actions, such as:
- **Install** - Deploys and installs the agent to the selected users.
- **Block** - Blocks the agent from members of your organization. They will not be able to install or use the agent. Additionally, the agent will be removed from any member of your organization who has already installed it.
- **Pin for users** - The agent will be pinned in the UI (based on channel) where the agent was deployed, so that the agent can be found more easily. Based on the users or groups where the agent was deployed, you can specify who will have the agent pinned.

For more information about agent actions, see [Agent actions available in Microsoft 365 admin center](agent-actions.md).

### Sections provided within agent details

The following table provides agent sections (tabs) that are available for agent details based on capability:

| Agent section (tab) | Description |
|---|---|
| **[Overview](#agent-overview-details)** | This tab provides a description, instructions, publish status, availability, publisher, deployment, agent type, coannel, platform, last   updated, sensitivity, and version. |
| **[Users](#agent-users)** | This tab allows you to view and select the allowed users that the agent has been publish to. |
| **[Permissions](#agent-permissions)** | This tab allows you to review and grant permission to data the agent can access and perform actions on. For more information, see [Agent permissions](#agent-permissions). |
| **[Data & Tools](#agent-data--tools)** |  This tab provides details about Microsoft Purview proections, such as capabilities, knowledge sources, and tools available to the agent. Also, provides Microsoft Entry   protection details, such as Agent User ID and Agent ID. |
| **[Security](#agent-security)** | This tab provides details about monitoring agent activity, protecting sensitive   data, and evaluating compliance gaps. |
| **[Connect Agents](#agent-with-connected-agents)** | This tab allows you to connect the selected agent with other agents. When using the selected agent, users can get additional information and answers from the connected agents. You can connect up to 10 agents to the selected agent, excluding those added by the agent's maker. Depending on how the agent maker connected the agents, you may be able to remove them as well. You must make sure the connected agents are available to everyone who needs access. |
| **[Custom tools & knowledege](#agent-custom-tools--knowledge)** | This tab helps you extend the selected agent by copying the skills and knowledge from up to one other agent. When you select an agent to extend from, the skills and knowledge from   that agent will be available in the selected agent. |
| **[Computer use](#agent-computer-use)** | This tab is used to allow the selected agent to perform action on behalf of the users and also access work data. Additionally, you can choose which websites are   allowed for **Computer use**. Note that Web search is required for **Computer use**. |

## Agent overview details

The **Overview** tab provides a description, instructions, publish status, availability, publisher, deployment, agent type, channel, platform, last updated, sensitivity, and version.

## Agent users



## Agent permissions

In the Microsoft 365 admin center, when granting permissions to agents, consider two types of permissions:

- **Application Permissions**
- **Delegated Permissions**

Each permission type grants different actions that agents can perform on behalf of users, depending on the scope of the access. This section explains these two types of permissions and provides an overview of the common permissions available.

### Application Permissions

**Application Permissions** let the agent access data and perform actions without requiring a user to sign in. These permissions let agents do tasks without needing a user to be signed in, like reading directory data, managing teams, or sending messages.

Key features of application permissions:

- **No user context required** - The agent can operate without an active user session.
- **Wide-reaching capabilities** - Agents with application permissions can act at the organizational level, allowing access to a large range of data.
- **Administrator consent required** - Administrator consent is typically required for granting application permissions.

#### Common Application Permissions

| Permission | Details |
| --- | ---|
| **Group.Read.All** | Read all groups in the organization. |
| **TeamsActivity.Send** | Send a teamwork activity to any user. |
| **RoleManagement.Read.Directory**| Read all directory role-based access control (RBAC) settings. |
| **User.Read.All** | Read all users' full profiles. |
| **Team.ReadBasic.All** | Get a list of all teams in the organization. |

### Delegated Permissions

**Delegated Permissions** allow the agent to act on behalf of a user when the user is signed in. These permissions provide access to user-specific data and allow agents to perform actions in the context of a particular user.

Use delegated permissions for applications where the agent interacts directly with the user's data or takes actions on their behalf.

#### Key features of delegated permissions

- **User context required** - The agent performs actions with the signed-in user's permission.
- **Granular access** - These permissions are typically more restricted, limiting access to only the user's data.
- **User consent might be required** - Depending on the permissions, users might need to grant consent for the application to act on their behalf.

#### Common delegated permissions

| Permission | Details |
| --- | --- |
| **User.ReadBasic.All** | Read all users' basic profiles. |
| **TeamsActivity.Send** | Send a teamwork activity to any user. |
| **RoleManagement.Read.Directory** | Read all directory role-based access control (RBAC) settings. |
| **User.Read.All** | Read all users' full profiles. |
| **Team.ReadBasic.All** | Get a list of all teams. |

### Where can administrators see all permissions of an agent

You can find the details of all types of permissions in the **Permissions** tab on the agent details page.

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. In the left navigation pane, select **Agents** > **All Agents**.
1. Select a deployed agent from the list.
1. In the agent details pane that opens, select the **Permissions** tab to view all the permissions granted to the agent.

    :::image type="content" source="../../media/agents/agent-permissions.png" alt-text="Screenshot showing the Permissions tab on the agent details page in the Microsoft 365 admin center." lightbox="../../media/agents/agent-permissions.png":::

## Agent data & tools

The **Data & tools** tab, displayed in the fly-out pane of a selected agent in the agent **Registry**, provides details about the selected agent can access and do within your organization. This tab surfaces three categories of agent metadata:
- **Capabilities** - How the agent can perform specific tasks and access data sources to provide accurate, contextual responses.
- **Knowledge sources** - Data that the agent uses to answer questions accurately.
- **Tools** - Processes that the agent uses to handle requests.

You can use this information to understand the data the agent has access to, the external sources it references, and the actions it can perform. By understanding these categories, you can make informed governance decisions about the agents deployed in your tenant.

> [!IMPORTANT]
> Admins with the **AI Administrator** or **Global Administrator** role have full access to view **Data & tools** for all agents. Use roles with the fewest permissions. Accounts with lower permissions help improve security for your organization. Global Administrator is a highly privileged role. Limit its use to emergency scenarios when you can't use an existing role. For more information, see [About admin roles in the Microsoft 365 admin center](/microsoft-365/admin/add-users/about-admin-roles).

To access the **Data and tools** tab for an agent, use the following steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).
2. Navigate to **Agents** > **All agents**.
  The agent **Registry** tab will be selected.
3. Select an agent from the **Registry** list.
4. In the agent details panel, select the **Data & tools** tab.

The **Data & tools** tab is read-only and shows metadata reported by the agent platform. To change an agent's data sources or tools, the agent developer must update the agent configuration in the authoring platform, such as Copilot Studio, or Foundry. 

Some agents may have an empty **Data & tools** tab. This occurs based on the following conditions: 
- The agent developer did not configure knowledge sources or tools for the agent.
- The agent type does not support these metadata fields. 
- The agent's metadata has not yet synced to Microsoft 365 admin center.

### Capabilities

The **Capabilities** section of the **Data & tools** tab shows the types of content and data sources the agent can access to provide accurate, contextual responses. 

The **Can read** section indicates the categories of content the agent has been granted read access to. The following table provides examples of content that can be included: 

| Category | Description | 
|---|---| 
| Public sites | Agent can read publicly accessible web content | 
| Organization files | Agent can read files within your Microsoft 365 tenant (SharePoint, OneDrive) | 
| Email | Agent can read user email content | 
| Calendar | Agent can read calendar events | 

> [!NOTE]
> The capabilities shown depend on the permissions configured for the agent and may vary by agent type and platform.
> 
> **Public sites** means the agent can access publicly available web content. This does not mean the agent has unrestricted internet access — it can read public web pages as a knowledge source to inform its responses.

### Knowledge sources

The **Knowledge sources** section provides data sources and URLs that the agent uses to answer questions accurately. These knowledge sources are the external or internal references the agent draws from when responding to user queries. 

The following table provides knowledge sources and examples that can included with the agent: 

| Source type | Examples | 
|---|---| 
| Web URLs | `https://bing.com/`, `https://contoso.com/docs/` | 
| SharePoint sites | `https://contoso.sharepoint.com/sites/hr-policies` | 
| Files and folders | Specific documents or folder paths configured as the agent's knowledge base | 
| Graph connectors | Data indexed via Microsoft Graph connectors | 

> [!NOTE]
> Review knowledge source URLs to verify the agent is only referencing approved, trusted sources. Unfamiliar or external URLs may indicate the agent has access to data outside your organization's boundaries.

### Tools

The **Tools** section provides the processes, connectors, and actions that the agent uses to handle requests. Tools represent what the agent can do, not just what it can read.

The following table provides tool types and examples that can included with the agent: 

| Tool type | Examples | 
|---|---| 
| Microsoft 365 connectors | `shared_office365_ContactGetItem_V2` (reads contact data from Office 365) | 
| MCP servers | Third-party or customer-hosted MCP servers connected to the agent | 
| Work IQ tools | `Work IQ Mail (Preview)` (email-related actions) | 
| Custom actions | API actions defined by the agent developer | 

> [!NOTE]
> Each tool listed represents an action the agent can invoke at runtime. Review the tool list to understand the scope of what the agent can do on behalf of users. Tools that access external services or write data (send email, update records) warrant closer review.

### Data & tools by agent type

The metadata surfaced in the **Data & tools** tab varies depending on the agent type and platform. The table below summarizes the capabilities for each type of agent.

| Agent type | Can read | Typical knowledge sources | Typical tools | 
|---|---|---|---| 
| **MCS DA** (Declarative Agent) | Organization files, Public sites | SharePoint sites, web URLs, Graph connectors | Microsoft 365 connectors, custom API actions | 
| **MCS CEA** (Custom Engine Agent) | Public sites, Organization files | Web URLs, custom knowledge bases | Office 365 connectors (e.g., ContactGetItem), Work IQ tools | 
| **MCS BP** (Business Process) | Organization files, Email | SharePoint sites, business system URLs | Workflow connectors, Office 365 connectors | 
| **Foundry LOB** | Organization files, LOB data | SharePoint sites, LOB system endpoints | Foundry-managed connectors, custom API actions | 
| **Foundry non-LOB** | Public sites, Organization files | Web URLs, SharePoint sites | Foundry-managed connectors | 
| **Foundry hosted** | Organization files | SharePoint sites, hosted data endpoints | Foundry-managed connectors, hosted service actions | 
| **Agent Builder** | Public sites, Organization files | Web URLs, SharePoint sites, uploaded files | Microsoft 365 connectors, custom actions | 
| **SharePoint** | Organization files | SharePoint sites, document libraries | SharePoint connectors | 
| **Agent Toolkit** | Organization files, Public sites | Web URLs, SharePoint sites | Custom-developed tools, Microsoft 365 connectors | 
| **A365 SDK** | Varies by implementation | Varies by implementation | Custom tools defined via SDK | 

## Agent security

## Agent with connected agents

## Agent custom tools & knowledge

## Agent computer use

## Manage agents with embedded file content as a knowledge source

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

