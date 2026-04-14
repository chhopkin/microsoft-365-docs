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

The **Requests** list of agents provides a view of agents that require your review and action. Members of your organizaton can request specific agents that need your review before they can be made available to members of your organization.

:::image type="content" source="../../media/agents/agent-requests.png" alt-text="Screenshot showing agent requests, which provides an list of agents that need admin review." lightbox="../../media/agents/agent-requests.png":::

## Publish agents

To ensure governance for new agents, when a user publishes an agent, it requires AI admin approval before becoming available tenant-wide. Administrators can review the agent's details, such as the description, owner, data, and tools, and then publish or reject it. On publishing, administrators can also scope its audience to specific users or groups, or everyone, ensuring a controlled rollout.

The Microsoft 365 admin center publishing process for agents submitted through Copilot Studio ensures governance, security, and quality of custom applications.

It also reduces manual work by automating the submission and review of manifests, freeing developers and administrators from repetitive tasks. The streamlined approval workflow makes it faster and easier for administrators to review, approve, and manage custom agents in the Microsoft 365 admin center.

:::image type="content" source="../../media/agents/publish-agent.png" alt-text="Screenshot showing publish agent to selected users." lightbox="../../media/agents/publish-agent.png":::

### Overview of the publishing process

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

1. **Review permissions and grant admin consent** - Review the permissions requested by the agent and grant admin consent if appropriate. Permissions allow the agent to access relevant data or perform actions on behalf of users. For more information, see [Understanding permissions](agent-actions.md#understanding-permissions).

1. **Review and complete publishing** - Review all configurations and select **Finish** to publish the agent.

1. **Approve updates** - When developers publish an update to an existing agent, the update appears in the **Pending approval** list with the status **Update pending**. Until the update is approved, the previous version of the agent remains available to users.

    > [!IMPORTANT]
    >
    > Developers can [update the existing apps](/microsoft-365-copilot/extensibility/) to work with Microsoft 365 Copilot. If an admin preapproves or preinstalls the updated app, it updates for the assigned users and starts working with Copilot. If a developer updates a previously blocked app to work with Microsoft 365 Copilot, and then the administrators make the app available to the users, the app also works with Copilot.

## Activate agents

A governance step for new agents: when a user requests an agent to activate to create instances, it requires AI admin approval before they can create instances. Administrators can review the agent's details, such as the description, owner, data, and tools, and then approve the request and activate or reject it. When an administrator activates an agent, they can also scope its audience, such as specific users, groups, or everyone, ensuring a controlled rollout.

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

1. **Review permissions and grant admin consent** - Review the permissions requested by the agent and grant admin consent if appropriate. Permissions allow the agent to access relevant data or perform actions on behalf of users. For more information, see [Understanding permissions](agent-actions.md#understanding-permissions).

1. **Review and complete activation** - Review all configurations and select **Finish** to activate the agent.

    Once activated, the agent is available for creating instances in the Microsoft Teams App Store, and the requester is notified. For future user additions, the process is simplified. The administrator only needs to approve or reject requests, using existing templates without repeating the full activation steps.

| Service Name | Policy Name | Description of Policy | More Information |
| --- | --- | --- | --- |
| Microsoft Entra | Identity Protection  | Detect agent identity threats by flagging anomalous activities involving agents. | [What is Microsoft Entra ID Protection?](/entra/id-protection/overview-identity-protection) |
| Microsoft Entra | Network visibility | Enable network visibility to agent access to external resources. | [Learn about Secure Web And AI Gateway for Microsoft Copilot Studio agents](/entra/global-secure-access/concept-secure-web-ai-gateway-agents) |
| Microsoft Entra | Lifecycle management for agents | Govern Microsoft Entra Agent IDs at scale with lifecycle policies. | [Automate identity lifecycle management with Microsoft Entra ID Governance](/entra/id-governance/scenarios/automate-identity-lifecycle) |
| SharePoint | Restrict external sharing of sites and its content | Provides capability to allow or restrict specific agents from sharing content in SharePoint sites and OneDrive with guests. | [What is SharePoint Advanced Management?](/sharepoint/advanced-management) |
| SharePoint | Access Control for Sites and OneDrive | Allows admin to specify agents and users allowed to access a given site. | [Restrict SharePoint site access with Microsoft 365 groups and Microsoft Entra security groups](/SharePoint/restricted-access-control) |
| SharePoint | Agent access insights | Provides insights on content and sites permissioned to users. | [Data access governance reports for SharePoint and OneDrive sites](/sharepoint/data-access-governance-reports) |
| SharePoint | Content Permissions Insights | Provides insights on agents accessing SharePoint and OneDrive sites. | [Monitor agent access to SharePoint and OneDrive](/SharePoint/insights-on-agent-access) |
| Purview | Purview Audit Enabled | Audit trails log all activities and provide clear observability. | [Data security](/microsoft-agent-365/admin/data-security) |
| Purview | Know Your Data Policy | Data security controls safeguard against sensitive data leaks and oversharing. | [Data security](/microsoft-agent-365/admin/data-security) |
| Purview | Purview AI compliance assessment | Continuous monitoring evaluates agents for compliance gaps and identifies areas needing attention. | [Data security](/microsoft-agent-365/admin/data-security) |

##### Default template automatic license assignment

The default template automatically assigns the Agent 365 license during activation. This automatic license assignment eliminates manual license management and ensures that every hired agent instance is properly licensed before becoming operational. Key benefits include:

- **Faster onboarding** - Administrators don't need to manually allocate licenses for each instance.
- **Compliance assurance** - Prevents unlicensed usage and maintains entitlement integrity.
- **Scalable management** - Supports large-scale deployments without increasing administrative overhead.


