---
title: Agent Registry in the Microsoft 365 admin center
description: Learn how to use Agent Registry in the Microsoft 365 admin center to manage, govern, and audit agents across your organization. Get started.
#customer intent: Learn about the Agent Registry in the Microsoft 365 admin center.
f1.keywords:
- NOCSH
ms.author: frankroj
author: frankroj
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

# Agent Registry in the Microsoft 365 admin center

The Agent Registry page in the [Microsoft 365 admin center](https://admin.microsoft.com/) provides a centralized view of all agents available in your organization. This section helps administrators monitor, manage, and govern agents effectively.

## Agent Registry overview and types of agents

Agent Registry lists all agents integrated with Microsoft 365 Copilot, including:

- **Microsoft agents** - Built and maintained by Microsoft.
- **External partner-built agents** - Built by trusted non-Microsoft developers.
- **Shared by creator** - Agents created and shared by individual users or developers in your organization.
- **Published by your org** - Custom agents approved and published by your organization for broader use.

## Agent Registry list

### Manage agents with embedded file content as a knowledge source

Agent creators can use [Agent Builder in Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/agent-builder-build-agents) to upload files for the agent to use as knowledge. Copilot stores the uploaded files in tenant-owned [SharePoint Embedded](/sharepoint/dev/embedded/overview) containers. It then embeds the file content as knowledge for the agent to use in responses. For more information, see [Embedded file content](/microsoft-365-copilot/extensibility/agent-builder-add-knowledge#embedded-file-content).

> [!IMPORTANT]
>
> [Microsoft Purview Information Barriers (IB)](/purview/information-barriers) isn't supported on embedded files. Any user who can access the agent can see responses grounded in the embedded file content.

This article explains how to handle embedded files, how you can manage agents and containers, and what to expect with sensitivity labels and deletion workflows.

#### Supported file types and limits

:::image type="content" source="../../media/knowledge-agent-upload.png" alt-text="Screenshot of the file upload screen for adding a knowledge source to an agent." lightbox="../../media/knowledge-agent-upload.png":::

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

:::image type="content" source="../../media/knowledge-agent-filter.png" alt-text="Screenshot of the agents and connectors page with filters highlighted in the Microsoft 365 admin center." lightbox="../../media/knowledge-agent-filter.png":::

For each agent, the following metadata is available:

- **File name** - The name of the uploaded file.
- **File sensitivity** - The sensitivity label applied to the file.
- **SharePoint container ID** - The unique identifier for the container storing the file.

This metadata helps you track and audit the use of embedded content across agents.

#### Sensitivity labels and access control

The service applies sensitivity labels to the embedded content in the agent based on the most restrictive label from the uploaded files. The following rules determine how the service applies sensitivity labels:

- The service uses the most restrictive sensitivity label from the following options:

  - The most restrictive sensitivity label of all uploaded files. For example, the highest priority of the labels on the uploaded files.
  - If your organization configured and applied a [default sensitivity label policy](/purview/default-sensitivity-labels-policies#default-sensitivity-label-policy).

- If a default sensitivity labeling policy is in place, the service automatically assigns a label.

- The service only applies sensitivity labels if all the following conditions are true:

  - You create the agent by using Microsoft 365 Copilot Agent Builder.
  - The agent includes embedded files.

You can view the sensitivity label for each agent in the **Overview** tab of the Microsoft 365 admin center.

:::image type="content" source="../../media/knowledge-agent-idea.png" alt-text="Screenshot of an agent overview page with agent details in the Microsoft 365 admin center." lightbox="../../media/knowledge-agent-idea.png":::

#### User access and visibility

- If a user doesn't have extract rights to any of the sensitivity labels applied to the uploaded files, they can't access the agent.

- If a user has extract rights, they can view the agent's sensitivity label in the agent details pane.

For more information, see [Sensitivity labels for agent embedded content](/microsoft-365-copilot/extensibility/copilot-studio-lite-knowledge#sensitivity-labels-for-agent-embedded-content).

### Agent details

#### Researcher with Computer Use admin configuration

> [!IMPORTANT]
>
> **Researcher with Computer Use** is only for Frontier tenants.

For **Researcher with Computer Use** onboarding instructions, see the following short video:

> [!VIDEO https://www.youtube.com/embed/N3vLF9mnd8w?si=XJaYnCQYNy_CeuFc]

**Researcher with Computer Use** is a powerful extension that builds on the capabilities of the Researcher agent. By using Computer Use, the Researcher agent can securely interact with public, gated, and interactive web content through a virtual computer. By using this method, users can uncover deeper insights, take action, and generate richer reports grounded in both their work data and the web. For more information, see [Use Researcher with Computer use in Microsoft 365 Copilot](https://support.microsoft.com/topic/1f274537-6648-46e8-8264-052a49b92af4).

:::image type="content" source="../../media/agents/researcher.png" alt-text="Screenshot of Researcher with Computer Use in Microsoft 365 Copilot." lightbox="../../media/agents/researcher.png":::

##### Configure admin settings for Researcher with Computer Use

To configure admin settings for **Researcher with Computer Use**, follow these steps:

1. Go to the **Microsoft Admin Controls (Microsoft 365 admin center) Agents** page.

1. In the left navigation pane, select **Researcher under Agents**, and check if there's another tab for **Computer Use**.

1. Customize users that have access to **Researcher with Computer Use**.

    :::image type="content" source="../../media/agents/researcher-step-2.png" alt-text="Screenshot of the Researcher with Computer Use page in the Microsoft 365 admin center." lightbox="../../media/agents/researcher-step-2.png":::

   - There are three options for configuring who has access to the experience:

     1. Allow all users in your organization.
     1. Allow specific users or groups only.
     1. No users in your organization.

    :::image type="content" source="../../media/agents/researcher-step-3-a.png" alt-text="Screenshot of the Computer Use option for the Researcher agent." lightbox="../../media/agents/researcher-step-3-a.png":::

   - For users that have this option disabled, the **Computer Use** option is grayed out.

    :::image type="content" source="../../media/agents/researcher-step-3-b.png" alt-text="Screenshot of the Computer Use option shown as unavailable for the Researcher agent." lightbox="../../media/agents/researcher-step-3-b.png":::

1. Configure Work access for **Researcher with Computer Use**:

    - The **Work** option allows users to toggle on **Work in the Sources** menu, allowing Researcher agent to use a user's work content with Computer Use. For example, emails, chats, and files.

    - When enabled by admins, users must still manually toggle on Work access.
        :::image type="content" source="../../media/agents/researcher-step-4-a.png" alt-text="Screenshot of the Work option in the Sources menu for Researcher with Computer Use." lightbox="../../media/agents/researcher-step-4-a.png":::

    - When disabled, the **Work** source appears grayed out and isn't selectable.
        :::image type="content" source="../../media/agents/researcher-step-4-b.png" alt-text="Screenshot of the Work option shown as unavailable in Researcher with Computer Use." lightbox="../../media/agents/researcher-step-4-b.png":::

1. Select which websites are allowed for **Computer Use**:

   - There are three options for configuring websites the virtual device can access:

     1. All websites.

     1. Allow specific URLs or domains only.

     1. Exclude specific URLs or domains.

   - You can allow **All websites**, block some websites by using the **Exclude specified** option, or only allow certain sites by using the **Allow specified** option.

##### Learn more about Researcher with Computer Use

- [Introducing Researcher with Computer Use in Microsoft 365 Copilot](https://techcommunity.microsoft.com/blog/microsoft365copilotblog/introducing-researcher-with-computer-use-in-microsoft-365-copilot/4464766).
- [Get started using Researcher with Computer Use](https://support.microsoft.com/topic/get-started-using-researcher-with-computer-use-in-microsoft-365-copilot-frontier-1f274537-6648-46e8-8264-052a49b92af4).
- [Frequently asked questions for Researcher with Computer Use](/microsoft-365/copilot/researcher-agent-computer-use-faq).

#### Agent metadata in the Microsoft 365 admin center

:::image type="content" source="../../media/agents/career-coach.png" alt-text="Screenshot of the Career Coach agent details page." lightbox="../../media/agents/career-coach.png":::

To access the metadata for a Copilot agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Agents** to expand it.

1. Under **Agents**, select [**All agents**](https://admin.cloud.microsoft/?#/agents/all).

1. In the **All agents** page, select an agent.

1. In the agent details pane that opens, select the **Data & tools** tab to view the agent's metadata.

The metadata includes details such as the agent's capabilities, data sources, and custom actions. Example data sources include OneDrive and SharePoint files and sites, or Graph connectors. Metadata is only for custom agents, which are designed to perform specific tasks based on predefined rules and configurations.

## Admin actions to manage agents

Administrators in the Microsoft 365 admin center can take several actions to control the lifecycle, availability, and compliance of agents in their organization. When administrators use these controls, they can decide which agents are visible, who can access them, and how to manage them across the tenant.

### Available actions

- **Publish** - Make an agent available for installation to specific users or groups.

    > [!NOTE]
    > Microsoft 365 for government Community Cloud High (GCCH) and Government Community Cloud Moderate (GCCM) environments support publishing agents to the organization.

- **Activate** - Allow only selected users or groups to install the agent and create instances.

- **Deploy** - Automatically install an agent for users so it's ready to use without manual setup.

- **Pin** - Surface key agents prominently in the Copilot interface for selected users or all users in the tenant.

- **Block** - Restrict access to an agent across the organization, preventing any user from using it.

- **Remove** - Remove an agent from the tenant's inventory. You can re-add it later from the store if needed.

- **Delete** - Delete agents directly from the Microsoft 365 admin center. When you delete an agent, Microsoft 365 removes the agent from the inventory and deletes all associated files.

- **Approve Updates** - Review and approve new versions or changes to existing agents before they're deployed.

- **Manage Ownerless Agents** - Identify agents without an active owner and take action to block or remove them.

- **Reassign** - Assign a new owner to agents that are ownerless or active.

- **Export Inventory** - Download the full list of agents for reporting, audit, or compliance purposes.

### Publish agents

To ensure governance for new agents, when a user publishes an agent, it requires AI admin approval before becoming available tenant-wide. Administrators can review the agent's details, such as the description, owner, data, and tools, and then publish or reject it. On publishing, administrators can also scope its audience to specific users or groups, or everyone, ensuring a controlled rollout.

The Microsoft 365 admin center publishing process for agents submitted through Copilot Studio ensures governance, security, and quality of custom applications.

It also reduces manual work by automating the submission and review of manifests, freeing developers and administrators from repetitive tasks. The streamlined approval workflow makes it faster and easier for administrators to review, approve, and manage custom agents in the Microsoft 365 admin center.

:::image type="content" source="../../media/agents/publish-agent.png" alt-text="Screenshot of the publish agent pane for selected users." lightbox="../../media/agents/publish-agent.png":::

#### Overview of the publishing process

The publishing process consists of the following steps:

1. **Agent creation and submission** - Developers create and test agents in Copilot Studio. When ready, they submit the agent for approval to the Microsoft 365 admin center directly from within Copilot Studio.

1. **View pending submissions** - In the **Requests** tab, you can view all submitted agents that are pending approval. This list displays:

    - **Agent name**.
    - **Publisher name**.
    - **Host products**.
    - **Status**.
    - **Date requested**.

    New submissions appear with the status of pending review.

1. **Review submission details** - Select a pending agent to view more details and metadata including:

   - **Agent description and capabilities**.
   - **Connected data sources and tools**.

    These details help administrators make informed decisions about publishing or rejecting an agent.

1. **Start the publishing wizard** - When ready, select **Start publishing** to open the publishing wizard.

1. **Select users or groups** - Choose the users or groups that the agent should be published to. Publishing makes the agent available for installation to the selected audience.

1. **(Optional) Preinstall or deploy** - Optionally, you can preinstall (deploy) the agent for the same set of users or for a specific subset of users.

1. **Apply Template** - To strengthen governance and security for agents, you can apply a template that includes predefined policies:

    - **Default Template** - Microsoft provides an out of the box template with essential security and compliance controls from Microsoft Entra, Microsoft Purview, and SharePoint.

    - **Custom Template** - If you need additional governance beyond the default, create a custom template and apply extra policies such as **Entra Access Package** to meet your organization's requirements.

1. **Review permissions and grant admin consent** - Review the permissions requested by the agent and grant admin consent if appropriate. Permissions allow the agent to access relevant data or perform actions on behalf of users. For more information, see [Understanding permissions](#understanding-permissions).

1. **Review and complete publishing** - Review all configurations and select **Finish** to publish the agent.

1. **Approve updates** - When developers publish an update to an existing agent, the update appears in the **Pending approval** list with the status **Update pending**. Until the update is approved, the previous version of the agent remains available to users.

    > [!IMPORTANT]
    >
    > Developers can [update the existing apps](/microsoft-365-copilot/extensibility/) to work with Microsoft 365 Copilot. If an admin preapproves or preinstalls the updated app, it updates for the assigned users and starts working with Copilot. If a developer updates a previously blocked app to work with Microsoft 365 Copilot, and then the administrators make the app available to the users, the app also works with Copilot.

### Activate agents

A governance step for new agents: when a user requests an agent activation to create instances, it requires AI admin approval before they can create instances. Administrators can review the agent's details, such as the description, owner, data, and tools, and then approve the request and activate or reject it. When an administrator activates an agent, they can also scope its audience, such as specific users, groups, or everyone, ensuring a controlled rollout.

The Microsoft 365 admin center activation process for agents ensures governance, security, and quality of custom applications.

#### Overview of the activation process

The activation process consists of the following steps:

1. **View pending activation request** - In the **Requests** tab, view all submitted agents that are pending activation request. This list displays:

    - **Agent name**.
    - **Publisher name**.
    - **Status**.
    - **Date requested**.

    New submissions appear with the status of allow activation.

1. **Review submission details** - Select a pending agent to view more details and metadata, including:

   - **Agent description and capabilities**.
   - **Connected data sources and tools**.

    These details help administrators make informed decisions about activating or rejecting an agent.

1. **Start with the request tab** - When ready, select the **Request** tab to open the request wizard.

1. **Select users** - Choose the users for whom you want to accept and approve activating the agent. Activating an agent makes it available for the selected audience to install and create instances.

1. **Activation Wizard** - After you accept the activation request, the wizard opens where you can select users. You can include the original requesters and add security groups that have access to create instances from the agent.

1. **Apply Template** - To strengthen governance and security for agents, you can apply a template that includes predefined policies.

    - **Default Template** - Microsoft provides an out of the box template with essential security and compliance controls from Microsoft Entra, Microsoft Purview, and SharePoint. The default template automatically assigns the Microsoft Agent 365 license to minimize manual license management. For more information, see [Default template automatic license assignment](#default-template-automatic-license-assignment).

    - **Custom Template** - If you need additional governance beyond the default, create a custom template and apply extra policies such as **Restrict External Content sharing** to meet your organization's requirements.

1. **Review permissions and grant admin consent** - Review the permissions requested by the agent and grant admin consent if appropriate. Permissions allow the agent to access relevant data or perform actions on behalf of users. For more information, see [Understanding permissions](#understanding-permissions).

1. **Review and complete activation** - Review all configurations and select **Finish** to activate the agent.

    Once activated, the agent is available for creating instances in the Microsoft Teams App Store, and the requester is notified. For future user additions, the process is simplified. The administrator only needs to approve or reject requests, using existing templates without repeating the full activation steps.

| **Service Name**     | **Policy Name**                                    | **Description of Policy** | **More Information** |
| -------------------- | -------------------------------------------------- | ------------------------- | -------------------- |
| **Microsoft Entra**  | Identity Protection                                | Detect agent identity threats by flagging anomalous activities involving agents. | [What is Microsoft Entra ID Protection?](/entra/id-protection/overview-identity-protection) |
| **Microsoft Entra**  | Network visibility                                 | Enable network visibility to agent access to external resources. | [Learn about Secure Web And AI Gateway for Microsoft Copilot Studio agents](/entra/global-secure-access/concept-secure-web-ai-gateway-agents) |
| **Microsoft Entra**  | Lifecycle management for agents                    | Govern Microsoft Entra Agent IDs at scale with lifecycle policies. | [Automate identity lifecycle management with Microsoft Entra ID Governance](/entra/id-governance/scenarios/automate-identity-lifecycle) |
| **SharePoint**       | Restrict external sharing of sites and its content | Provides capability to allow or restrict specific agents from sharing content in SharePoint sites and OneDrive with guests. | [What is SharePoint Advanced Management?](/sharepoint/advanced-management) |
| **SharePoint**       | Access Control for Sites and OneDrive              | Allows admin to specify agents and users allowed to access a given site. | [Restrict SharePoint site access with Microsoft 365 groups and Microsoft Entra security groups](/SharePoint/restricted-access-control) |
| **SharePoint**       | Agent access insights                              | Provides insights on content and sites permissioned to users. | [Data access governance reports for SharePoint and OneDrive sites](/sharepoint/data-access-governance-reports) |
| **SharePoint**       | Content Permissions Insights                       | Provides insights on agents accessing SharePoint and OneDrive sites. | [Monitor agent access to SharePoint and OneDrive](/SharePoint/insights-on-agent-access) |
| **Purview**          | Purview Audit Enabled                              | Audit trails log all activities and provide clear observability. | [Data security](/microsoft-agent-365/admin/data-security) |
| **Purview**          | Know Your Data Policy                              | Data security controls safeguard against sensitive data leaks and oversharing. | [Data security](/microsoft-agent-365/admin/data-security) |
| **Purview**          | Purview AI compliance assessment                   | Continuous monitoring evaluates agents for compliance gaps and identifies areas needing attention. | [Data security](/microsoft-agent-365/admin/data-security) |

##### Default template automatic license assignment

The default template automatically assigns the Agent 365 license during activation. This automatic license assignment eliminates manual license management and ensures that every hired agent instance is properly licensed before becoming operational. Key benefits include:

- **Faster onboarding** - Administrators don't need to manually allocate licenses for each instance.
- **Compliance assurance** - Prevents unlicensed usage and maintains entitlement integrity.
- **Scalable management** - Supports large-scale deployments without increasing administrative overhead.

### Deploy agents

You can deploy agents across the whole organization or for specific users or groups by using the same gestures and controls that work for any other app in the Microsoft 365 admin center.

To deploy an agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. Make sure **Registry** is selected, and then filter the list by **Availability**.

1. Select an agent from the list that isn't deployed.

1. In the agent details pane that opens, under the agent's name, select **Deploy**.

1. In the **Deploy agent to selected users** pane, decide whether to deploy the agents to everyone or to specific users or groups, and then select **Next**.

    :::image type="content" source="../../media/agents/deploy.png" alt-text="Screenshot of the configuration pane for deploying an agent." lightbox="../../media/agents/deploy.png":::

1. In the **Review permissions** pane, review the permissions requested by the agent and grant admin consent if appropriate. For more information, see [Understanding permissions](#understanding-permissions). When finished, select **Next**.

1. In the **Review & finish** pane, select **Finish deployment**.

Deploying an agent affects its availability and functionality in Copilot and in the other host products, such as Outlook, Teams, or Microsoft 365.

#### Understanding permissions

In the Microsoft 365 admin center, when granting permissions to agents, consider two types of permissions:

- **Application Permissions**.
- **Delegated Permissions**.

Each permission type grants different actions that agents can perform on behalf of users, depending on the scope of the access. This section explains these two types of permissions and provides an overview of the common permissions available.

##### Application Permissions

**Application Permissions** let the agent access data and perform actions without requiring a user to sign in. These permissions let agents do tasks without needing a user to be signed in, like reading directory data, managing teams, or sending messages.

Key features of application permissions:

- **No user context required** - The agent can operate without an active user session.

- **Wide-reaching capabilities** - Agents with application permissions can act at the organizational level, allowing access to a large range of data.

- **Administrator consent required** - Administrator consent is typically required for granting application permissions.

###### Common Application Permissions

| **Permission**                    | **Details**                                                   |
| --------------------------------- | ------------------------------------------------------------- |
| **Group.Read.All**                | Read all groups in the organization.                          |
| **TeamsActivity.Send**            | Send a teamwork activity to any user.                         |
| **RoleManagement.Read.Directory** | Read all directory role-based access control (RBAC) settings. |
| **User.Read.All**                 | Read all users' full profiles.                                |
| **Team.ReadBasic.All**            | Get a list of all teams in the organization.                  |

##### Delegated Permissions

**Delegated Permissions** allow the agent to act on behalf of a user when the user is signed in. These permissions provide access to user-specific data and allow agents to perform actions in the context of a particular user.

Use delegated permissions for applications where the agent interacts directly with the user's data or takes actions on their behalf.

###### Key features of delegated permissions

- **User context required** - The agent performs actions with the signed-in user's permission.

- **Granular access** - These permissions typically restrict access to only the user's data.

- **User consent might be required** - Depending on the permissions, users might need to grant consent for the application to act on their behalf.

###### Common delegated permissions

| Permission | Details |
| --- | --- |
| **User.ReadBasic.All** | Read all users' basic profiles. |
| **TeamsActivity.Send** | Send a teamwork activity to any user. |
| **RoleManagement.Read.Directory** | Read all directory role-based access control (RBAC) settings. |
| **User.Read.All** | Read all users' full profiles. |
| **Team.ReadBasic.All** | Get a list of all teams. |

##### Where can administrators see all permissions of an agent

Administrators can find the details of all types of permissions in the **Permissions** tab on the agent details page.

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. Select a deployed agent from the list.

1. In the agent details pane that opens, select the **Permissions** tab to view all the permissions granted to the agent.

    :::image type="content" source="../../media/agents/agent-permissions.png" alt-text="Screenshot of the Permissions tab on an agent details page in the Microsoft 365 admin center." lightbox="../../media/agents/agent-permissions.png":::

### Manage pinning of agents

> [!NOTE]
>
> After an administrator pins an agent, it might take up to six hours for end-users to see the agent pinned.

This section explains how administrators can pin, unpin, or manage agents for everyone or specific groups by using the Microsoft 365 admin center. It also covers related actions like ranking the list of pinned agents and editing the scope of pinned agents.

Pinning agents is a feature that enables administrators to preselect and pin agents for end-users by using Microsoft 365 Copilot. The administrator pins the agent to ensure that the agent automatically appears in the end user's Copilot interface without requiring any user action. The agent is now readily accessible to the user in the Copilot interface.

#### Prerequisites

##### For end users

- Microsoft 365 work account.
- Access to Microsoft 365 Copilot Chat, for example, via Teams, web, or the Microsoft 365 Copilot app.
- The agent you want to pin must be discoverable to you.

##### For administrators

- AI Administrator.
- Access to the Microsoft 365 admin center.
- (Optional) Power Platform admin center access if you use Pay-as-you-go for agents.

#### Pinned agents

:::image type="content" source="../../media/agents/copilot-chat-pinned-agents.png" alt-text="Screenshot of pinned agents in Microsoft 365 Copilot Chat." lightbox="../../media/agents/copilot-chat-pinned-agents.png":::

#### Microsoft-pinned agents

- These agents are agents that Microsoft pins by default for all users.
- Ensures essential or high-value agents, like core Copilot features, are always visible.
- End users can't unpin these agents. They're fixed in the pinned list.

#### Administrator-pinned agents

- Pinned by your organization's administrator through the Microsoft 365 admin center.
- Can be pinned for:
  - **All users**.
  - **Specific groups**.
  - **Specific users**.
- End users usually can't unpin these agents. They're fixed in the pinned list.

#### User-pinned agents

- Pinned by individual users in their own Microsoft 365 Copilot Chat experience.
- Users can:
  - Pin agents they frequently use.
  - Unpin them anytime.
- This list is fully under the user's control, except for Microsoft-pinned or administrator-pinned agents, which remain locked.

#### Features

- Administrator-pinned agents appear by default for end-users, making them easier to discover and helping highlight new or important agents.
- Administrators can view the Microsoft-pinned agents in Microsoft 365 admin center.
- Administrators can pin up to three agents in Microsoft 365 admin center for end-users using Microsoft 365 Copilot in the organization.
- Administrators can choose to pin an agent for all users in the tenant or for specific users or groups. For example:
  - Pin **Sales Coach** agent only for the sales department.
  - Pin **HR Q&A** agent for all users.
- The end-user can't unpin the Administrator-pinned and Microsoft-pinned agents.

#### How to pin agents

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. In the **All agents** page, select the **Manage pinned agents** icon.

    :::image type="content" source="../../media/agents/manage-pinned-agents.png" alt-text="Screenshot of the Manage pinned agents setting in the Microsoft 365 admin center." lightbox="../../media/agents/manage-pinned-agents.png":::

1. In the **Pinned agents** pane, view the agents pinned by Microsoft under the **Pinned by Microsoft** list. Initially, the **Pinned by your org** section has no agents.

1. Select **Pin agent** to pin new agents.

1. In the **Select an agent to pin** pane, find the agent you want to pin from the list of agents. You can search the list to find a specific agent by name.

    :::image type="content" source="../../media/agents/select-an-agent.png" alt-text="Screenshot of the agent selection list in the Microsoft 365 admin center." lightbox="../../media/agents/select-an-agent.png":::

1. When you find the desired agent, select it and then select **Next**.

1. In the **Choose who will have this agent pinned** pane, choose the scope for the agent that you want to pin.

    - **All users the agent is deployed to** - Pin the agent for all users that the agent is deployed to in the tenant.

        >[!NOTE]
        >
        > If you don't see this option, the selected agent probably isn't deployed.

    - **Specific users or groups the agent is deployed to** - Pin for one or more groups or individual accounts.

    :::image type="content" source="../../media/agents/scope-agent.png" alt-text="Screenshot of the scope selection pane for pinning agents in the Microsoft 365 admin center." lightbox="../../media/agents/scope-agent.png":::

1. If you select **Specific users or groups the agent is deployed to**, select the specific users or groups to pin the agent.

    :::image type="content" source="../../media/agents/choose-specific-users-groups.png" alt-text="Screenshot of the user and group selection list for pinning an agent." lightbox="../../media/agents/choose-specific-users-groups.png":::

1. Select **Save**.

1. After you save the configuration, the system records which agent is pinned for the selected audience.

    :::image type="content" source="../../media/agents/pinned-agents.png" alt-text="Screenshot of the pinned agents list in the Microsoft 365 admin center." lightbox="../../media/agents/pinned-agents.png":::

#### Can any agent be pinned

You can only pin deployed agents. If the agent isn't deployed, you see a banner with a message to first deploy the agent.

:::image type="content" source="../../media/agents/deploy-agents.png" alt-text="Screenshot of the message that asks you to deploy the agent first." lightbox="../../media/agents/deploy-agents.png":::

If the agent is blocked, unblock the agent before you pin it.

:::image type="content" source="../../media/agents/unblock-agent.png" alt-text="Screenshot of the message that asks you to unblock the agent first." lightbox="../../media/agents/unblock-agent.png":::

#### Rank the list of pinned agents

- The administrator has three slots reserved for the pinned agents for each user.

- The administrator can use the **Move up** and **Move down** buttons to reorder the list of pinned agents by priority to control what is shown to the user.

#### How to unpin an agent

From the list of pinned agents, find the agent that you want to unpin and select **Unpin**. When you remove the pin, the agent is no longer available under the **Pinned by your org** section.

#### How to edit the pinning scope of an agent

Select the agent and choose **Edit users** to modify the scope of users for which an agent is pinned.

:::image type="content" source="../../media/agents/edit-user.png" alt-text="Screenshot of the Edit users option for pinning agents in the Microsoft 365 admin center." lightbox="../../media/agents/edit-user.png":::

#### Alternate entry point for pinning

You can also pin an agent from the agent details pane. Select the pin for the user icon. The icon is only enabled if the agent is deployed.

:::image type="content" source="../../media/agents/agent-details.png" alt-text="Screenshot of the agent details pane in the Microsoft 365 admin center." lightbox="../../media/agents/agent-details.png":::

### Block or unblock agents

Block or unblock agents for the entire organization by using the same controls that work for any other app in the Microsoft 365 admin center.

To block or unblock an agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. In the **All agents** page, choose an agent from the list of agents.

1. In the agent details pane that opens, under the agent name, select either **Block** or **Unblock**.

1. In the **Block agent** or **Unblock agent** pane that opens, select either **Block agent** or **Unblock agent**, and then select **Save**.

    :::image type="content" source="../../media/agents/block.png" alt-text="Screenshot of the pane used to block an agent." lightbox="../../media/agents/block.png":::

Blocking or unblocking an agent that you created by using Microsoft 365 Copilot Agent Builder and Microsoft 365 Copilot Studio affects its availability and functionality in Microsoft 365 Copilot. It also affects availability and functionality in other host products, such as Microsoft Outlook, Teams, or Microsoft 365. However, blocking an agent that you created by using SharePoint only impacts its availability in Microsoft 365 Copilot Chat.

> [!NOTE]
>
> For the [Researcher](https://support.microsoft.com/topic/e63ab760-f3de-4c47-ae87-dad601b0e9c4) and [Analyst](https://support.microsoft.com/topic/ff505b9c-a06c-4be9-b855-69d89b1d25d2) agents, the **Edit users** panel is disabled. To manage their availability, block the agent for the entire tenant by using the **Block** action in the Microsoft 365 admin center.

### Remove agents

You can remove first-party and external agents across the whole organization or for specific users or groups by using the same controls that work for any other app in the Microsoft 365 admin center.

To remove an agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. In the **All agents** page, filter the list by **Availability**.

1. Select a deployed agent from the list.

1. In the agent details pane that opens, under the agent name, select **Remove**.

    >[!NOTE]
    >
    > If you don't see the **Remove** option, the selected agent might not be deployed.

1. In the **Remove agent** pane, select the **Remove agent** option, and then select the **Remove agent** button.

Removing an agent affects its availability and functionality in Copilot and in the other host products, such as Microsoft Outlook, Teams, or Microsoft 365.

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

## Ownerless shared agent management

Shared agents can become ownerless when you delete the user who created them from the organization.

To help administrators manage these scenarios, the Microsoft 365 admin center now enables you to identify and manage ownerless shared agents. The dashboard displays the total count of such agents, a one-click filter to quickly isolate them, and real-time updates that reflect user deletions. When administrators use these features, they can efficiently review and address ownership gaps by blocking or deleting affected agents.

:::image type="content" source="../../media/agents/ownerless-shared-agents.png" alt-text="Screenshot of the ownerless shared agents view." lightbox="../../media/agents/ownerless-shared-agents.png":::

### Key features

- **Ownerless agent count** - Administrators can view the total number of agents without a valid owner directly from the dashboard. For example, the dashboard shows 20 ownerless agents, which indicates that users who left the organization created these agents.

- **One-click filter** - Selecting the dashboard pane instantly filters the agent inventory to display only shared agents missing an owner. This feature allows for quick triage and action.

- **Real-time updates** - The ownerless agent count automatically updates when you hard delete a user from the organization. This feature ensures that the dashboard reflects the current state without requiring manual refreshes.

### Steps to view and manage ownerless shared agents

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. In the **All agents** page, locate the **Missing an Owner** tab.

1. Select the tab to filter **Agent inventory**.

1. Review the list of ownerless agents and take appropriate actions such as [blocking](#block-or-unblock-agents) or [deleting](#delete-agents) the agent.

### Reassign ownership of shared agents

IT administrators can reassign ownership of shared agents that they create within the organization by using Agent Builder.

> [!IMPORTANT]
>
> Reassigning ownership of shared agents is only supported with Agent Builder agents.

#### How it works

To reassign ownership of a shared agent, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).

1. In the left navigation pane, select **Agents** > **All agents**.

1. In **All agents**, select the agent you want to reassign.

1. In the agent details pane, under the agent name, select **Assign new owner**.

    :::image type="content" source="../../media/agents/assign-new-shared-agent-owner.png" alt-text="Screenshot of the option to assign a new owner to a shared agent." lightbox="../../media/agents/assign-new-shared-agent-owner.png":::

1. In **Assign a new owner**, select a new owner from your organization. You can only reassign agents to users with a Copilot license.

    :::image type="content" source="../../media/agents/select-new-shared-agent-owner.png" alt-text="Screenshot of the page where you select a new owner for a shared agent." lightbox="../../media/agents/select-new-shared-agent-owner.png":::

#### What changes after reassignment

- The new owner gets full edit and delete permissions, plus access to any files the previous owner uploaded.

- The previous owner loses all access, including read rights.

When you reassign an agent created in Agent Builder, the new owner sees the agent listed here.

## Export to Excel

Export the list of shared agents to an Excel file. This feature is essential for detailed analysis and reporting.

> [!NOTE]
>
> If the export process reaches one minute, the exported file includes only the data up to that point.

The exported file includes comprehensive information about each shared agent, such as:

- Name.
- Host products.
- Created date.
- Developer user ID.
- Description.
- Status.
- Version.

With this information, you can efficiently manage and review the shared agents within your organization, ensuring compliance and optimizing resource allocation.

## Microsoft Graph API for Agent Registry and Agent Details (preview)

You can also access Agent Registry data programmatically through Microsoft Graph APIs, which gives you scalable and programmatic control over agent management. By using the new Microsoft Graph API endpoints, now in preview, administrators can integrate the following tasks into existing workflows across agents in Microsoft 365:

- Automate bulk agent management.
- Streamline onboarding.
- Integrate governance.

Beyond manual UX-driven agent management, the Microsoft Graph API helps you accelerate agent management, maintain security and compliance, and ensure agents are available to the right users at the right time.

- **Get all agents in your inventory** - By using the [GET packages API](/microsoft-365-copilot/extensibility/api/admin-settings/package/copilotpackages-list), administrators can retrieve a comprehensive list of all agents in their tenant to support compliance and reporting needs.

- **Get details of a particular agent in your inventory** - The [GET package details API](/microsoft-365-copilot/extensibility/api/admin-settings/package/copilotpackagedetail-get) provides rich metadata and details for any agent, making it easier to audit, manage, and optimize agent management.

The API works with the **AI Admin Role**.

For more information, see [Agent and app Package Management API overview (preview)](/microsoft-365-copilot/extensibility/api/admin-settings/package/overview).

## Risks column in the Microsoft 365 admin center All agents page

The **Risks** column on the Microsoft 365 admin center **All agents** page provides a unified view of aggregated high severity risks across Microsoft security platforms such as Entra, Microsoft Defender, and Purview. It closes a critical visibility gap for IT administrators responsible for governing AI agents. The **Risks** column is only available when a tenant has a [Microsoft 365 E7](https://microsoftpartners.microsoft.com/abs/Blog/?title=Introducing%20Microsoft%20365%20E7:%20The%20Frontier%20Suite) license.

:::image type="content" source="../../media/agents/all-agents-page.png" alt-text="Screenshot of the All agents page in the Microsoft 365 admin center." lightbox="../../media/agents/all-agents-page.png":::

To access the **All agents** page in the Microsoft 365 admin center and view the **Risks** column, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Agents** to expand it.

1. Under **Agents**, select [**All agents**](https://admin.cloud.microsoft/?#/agents/all).

1. In the **All agents** page, make sure **Registry** is selected.

1. The **Risks** column appears in the table in the **All agents** page. If the **Risks** column doesn't appear, the tenant might not have a Microsoft 365 E7 license.

When an administrator selects the risk count for an agent from the **Risks** column, they're taken directly to the Security tab within the agent's flyout details pane. This flyout provides a focused and actionable view of the total aggregated risk counts across all supported detection platforms for the selected agent. From this view, the administrator can further investigate risks and take mitigation actions, such as using the **Block** option to prevent the agent from operating if necessary. Additionally, the **Enabled policies and protection** sections display the default security protections applied to the agent by Microsoft Entra and Microsoft Purview.

:::image type="content" source="../../media/agents/agent-risks-flyout.png" alt-text="Screenshot of the agent risks flyout pane in the Microsoft 365 admin center." lightbox="../../media/agents/agent-risks-flyout.png":::

If the agent has multiple instances associated with it, the flyout initially displays a breakdown of aggregated risks by instance. From here, the admin can proceed to view the total aggregated risk counts across all detection platforms for the selected agent.

:::image type="content" source="../../media/agents/agent-instances-risks-flyout.png" alt-text="Screenshot of the agent instances risks flyout pane in the Microsoft 365 admin center." lightbox="../../media/agents/agent-instances-risks-flyout.png":::

To support further investigation, admins can select the **Review** link. The **Review** link redirects to the respective security portals where further action can be taken.

> [!IMPORTANT]
>
> - The **Risks** column only shows high severity risks flagged by the respective platforms. Zero risks is an indication that there are no high risks presently for the agent. However, there could be other types of risks, such as low or medium, in the respective security platforms.
>
> - There might be a delay of up to an hour for the risks count in the Microsoft 365 admin center when compared to what is shown in the security portals.

### Role-based access for the Review link

The following table shows what each role can access when they select the **Review** link:

| **Role**          | **Microsoft Entra** | **Purview**         | **Defender**        |
| ----------------- | ------------------- | ------------------- | ------------------- |
| **Global Reader** | Can view            | Can view            | Can view            |
| **AI Admin role** | Can view            | No view permissions | No view permissions |

> [!IMPORTANT]
>
> To access Purview alerts, users must be assigned an **Insider Risk Management** (IRM) role within Purview. This role is required to sign in to Purview to view Insider Risk Management alerts. For more information, see [Assign permissions in Insider Risk Management](/purview/insider-risk-management-permissions).
