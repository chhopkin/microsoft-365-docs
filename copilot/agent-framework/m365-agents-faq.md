---
title: Microsoft 365 agents FAQ
f1.keywords:
ms.author: erikre
author: ErikRe
manager: dansimp
ms.date: 11/04/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Get answers to frequently asked questions about Microsoft 365 agents governance.
---

# Microsoft 365 agents FAQ

## Do I need an agent or a connector? How do I get started?

Whether you need an agent or a connector depends on your business needs. Copilot agents support specialized workflows and experiences, whereas connectors help add knowledge to Microsoft 365 intelligence experiences, including Copilot.

- **Copilot agents** extend the functionality of Copilot by acting as specialized AI assistants tailored to specific domains or use cases. You can use agents to extend Copilot's knowledge, automate workflows, and deliver tailored user experiences in Microsoft Teams, Outlook, SharePoint, or custom apps. You can create a declarative agent using Copilot's AI infrastructure, model, and orchestrator. Or, for complex workflows or specific language models, you can create a custom agent. For more information, see [Agents for Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/agents-overview).

- **Copilot connectors** enable you to ingest data, such as unstructured, line-of-business data, into the Microsoft Graph so that Copilot can reason over that data alongside other data. There are more than 100 prebuilt Copilot connectors available, and the Connectors API can be used to create custom connectors. For more information, see [Microsoft 365 Copilot Connectors](/microsoft-365-copilot/extensibility/overview-copilot-connector).

To get started, [review our planning guide](/microsoft-365-copilot/extensibility/planning-guide), which can help you define your business need, and determine whether you need an agent or a connector. 

## What options are available for Copilot Agents?

There are two main types of Copilot agents you can create: 

- [Declarative agents](/microsoft-365-copilot/extensibility/agents-overview#declarative-agents), which use Copilot's AI infrastructure, model, and orchestrator. These agents are built using low-code tools like Copilot Studio (lite) or pro-code tools like Visual Studio, Visual Studio Code, and the Microsoft 365 Agents Toolkit. Declarative agents run in Microsoft 365 Copilot and Microsoft 365 apps like Teams, Outlook, and SharePoint.
- [Custom engine agents](/microsoft-365-copilot/extensibility/agents-overview#custom-engine-agents), which are fully customized AI assistants. These agents require additional hosting outside of Microsoft 365, and are typically built using  low-code Copilot Studio or pro-code tools like Visual Studio, Visual Studio Code, and Agents Toolkit, using languages such as .NET, Python, and JavaScript, and frameworks like Semantic Kernel or LangChain.

To help decide which type of agent to build, see [Choose what type of agent to build](/microsoft-365-copilot/extensibility/agents-overview#choose-what-type-of-agent-to-build).

## Who can create, build, and share Copilot agents?

- **Users** can create declarative agents in Copilot Studio (lite) or SharePoint if enabled by tenant settings (requires Copilot license or subscription)
- **Makers** can use Copilot Studio (lite or full) for low-code agents
- **Developers** can use Copilot Studio SDK or Agents Toolkit for pro-code agents. Developers can also [submit agents to the marketplace](/copilot/microsoft-365/agent-framework/agent-policies/agent-submit-marketplace)
- Both Makers and Developers can add actions, connectors, and advanced logic in Copilot Studio or via the Microsoft 365 Agents Toolkit

Also, people in your organization can [sideload agents](/copilot/microsoft-365/agent-framework/agent-policies/agent-sideload), [share agents](/microsoft-365/admin/manage/manage-shared-agents), and [publish agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps#publish-agents), according to tenant policies and admin controls that are configured in the Microsoft 365 admin center. 

For more information, see [Manage access to Copilot agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps#manage-access-to-copilot-agents).

## What tools do I need to create, build, implement, and use Copilot agents?

- **Users** can use Copilot and in Microsoft 365 apps (Word, Excel, PowerPoint, Outlook, Teams), and interact with declarative agents in Copilot Chat. Users can also build low-code declarative agents in Copilot Studio (lite).
- **Makers** can use Copilot Studio to build low-code agents. Makers can also add actions and connectors.
- **Developers** can use the Teams Toolkit or Agents SDK to create pro-code agents.
- **Administrators** can control agent creation and sharing in the Admin Center, and apply governance policies.

Make sure to review the following resources:

- [Microsoft 365 Copilot agents admin guide](/copilot/microsoft-365/agent-framework/m365-agents-admin-guide)
- [Planning guide for Copilot extensibility options](/microsoft-365-copilot/extensibility/planning-guide)

## What governance or controls does each extensibility option have?

For all extensibility options, your organization has the following governance tools available:

- [Copilot Control System](/copilot/microsoft-365/copilot-control-system/overview): Unified dashboard for managing Copilot and agents
- [Microsoft Purview](/purview/ai-microsoft-purview): Compliance, audit, and eDiscovery across all extensibility options
- Admin Centers: [Microsoft 365 Admin Center](/microsoft-365/admin/admin-overview/admin-center-overview) and [Power Platform Admin Center](/microsoft-365/admin/admin-overview/admin-center-overview) for configuration and enforcement.

The following table summarizes governance and control features for extensibility options:

| Extensibility Option | Governance & Control Features | Resources to learn more |
|--|--|--|
| Copilot (Out-of-the-Box) | Enable/disable Copilot features in Microsoft 365 Admin Center <br/><br/> Apply Conditional Access, DLP policies, and compliance settings via Purview<br/><br/> Built-in Microsoft 365 security boundary and identity-based access controls<br/><br/>Prompt safety mechanisms (Safe Links, classifiers, grounding constraints) | [Set up Microsoft 365 Copilot and assign licenses](/copilot/microsoft-365/microsoft-365-copilot-setup)<br/><br/>[Microsoft Purview data security and compliance protections for generative AI apps](/purview/ai-microsoft-purview)<br/><br/>[Security for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-ai-security) |
| Agents<br/>(Declarative or custom) | Copilot Control System for lifecycle management, permissions, and telemetry <br/><br/>Admin review and approval of agent actions before publishing <br/><br/>Block/unblock agents in Copilot Chat via Copilot Control System dashboard <br/><br/>Usage telemetry and operational insights in Admin Center <br/><br/>Responsible AI checks and audit trails in Purview | [Manage access to Copilot agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps#manage-access-to-copilot-agents)<br/><br/>[Copilot Control System management controls](/copilot/microsoft-365/copilot-control-system/management-controls) |
| Connectors | Approve or block connectors in the [Power Platform Admin Center](/power-platform/admin/admin-documentation?tabs=new) <br/><br/>Apply DLP policies to restrict connector usage <br/><br/> Roll out connectors to specific audiences for staged deployment <br/><br/>Compliance auditing via Purview <br/><br/> Data remains within tenant boundaries and honors identity-based access | [Microsoft 365 Copilot connectors overview](/microsoft-365-copilot/extensibility/overview-copilot-connector)<br/><br/> [Copilot Control System management controls](/copilot/microsoft-365/copilot-control-system/management-controls)<br/><br/>[Data stored about user interactions with Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-privacy#data-stored-about-user-interactions-with-microsoft-365-copilot) |
| Notebooks | Admin toggle to enable/disable Copilot Notebooks <br/><br/>Sharing governed by Microsoft 365 permissions (Loop component model) <br/><br/>Lifecycle aligned with Microsoft 365 compliance posture <br/><br/>Security boundary consistent with tenant controls | [Admin policies for Copilot Pages and Copilot Notebooks](/microsoft-365/loop/cpcn-admin-configuration) <br/><br/>[Summary of governance, lifecycle, and compliance capabilities for Copilot Pages and Copilot Notebooks](/microsoft-365/loop/cpcn-compliance-summary) |

## Based on my use cases, how do I know which accessibility option to implement?

The following table summarizes use cases, extensibility options, and compliance & governance controls.

| Use case | Option | Compliance & governance controls |
|--|--|--|
| Simple retrieval, such as asking questions based on uploaded documents or links | Copilot | Data residency<br/><br/>DLP<br/><br/>Audit logs<br/><br/>Copilot admin controls |
| Comparative analysis, such as comparing features, language, or terms across documents | Copilot | Data residency<br/><br/>DLP<br/><br/>Audit logs<br/><br/>Copilot admin controls |
| Multistep reasoning, such as log chains, decision trees, or conditional flows | Custom agent | Custom logging<br/><br/>RBAC<br/><br/>Code review<br/><br/>Azure Policy<br/><br/>Agent-specific DLP |
| Workflow automation, such as structured tasks, approvals, or integrations | Custom agent | Workflow approval logs<br/><br/>RBAC<br/><br/>API permissions<br/><br/>Audit trails |
| Role-specific guidance, such as tailored responses by user role or context | Custom agent | RBAC<br/><br/>User context logging<br/><br/>Privacy review |
| External system integration, such as using data from APIs, databases, or internal tools | Custom agent/connector | API authentication<br/><br/>Consent<br/><br/>Connector certification<br/><br/>Data boundary enforcement |
| Data enrichment or transformation, such as pulling, transforming, or combining data from multiple sources | Connector/notebook | Data lineage<br/><br/>Transformation logs<br/><br/>Connector governance |
| Advanced analytics/visualization, such as custom calculations, dashboards, or visualizations | Notebook | Workspace access controls<br/><br/>Notebook versioning<br/><br/>Data masking<br/><br/>Audit logs |

## Who can create, share, or use agents, and other extensibility options?

The following table summarizes types of users, what they can do, and apps/tools they can use:

| User type | Tasks |
|--|--|
| End users who have a Microsoft 365 Copilot license  | Use Copilot to summarize, analyze, or create content <br/><br/>Create declarative agents in Copilot Studio (lite) or SharePoint (if enabled for the organization)<br/><br/>Share Copilot outputs, such as documents or chats, according to Microsoft 365 policies<br/><br/>Create and use notebooks for structured workflows |
| Makers who have access to Copilot Studio and an appropriate role assigned | Tasks users can perform, plus these:<br/><br/>Use Copilot Studio (lite or full) to create low-code agents<br/><br/>Add actions, connectors, and advanced logic in Copilot Studio or the Microsoft 365 Agents Toolkit<br/><br/>Create custom connectors in Power Platform or Graph API (requires appropriate roles and DLP compliance) |
| Developers who have access to the Copilot Studio SDK or the Microsoft 365 Agents Toolkit, and an appropriate role assigned | Tasks users and makers can perform, plus these:<br/><br/>Use the Copilot Studio SDK or the Microsoft 365 Agents Toolkit to develop custom agents<br/><br/>Build advanced connectors and integrate with external APIs (subject to security reviews for enterprise usage)<br/><br/>Pair agents and connectors in notebooks, shared according to Microsoft 365 file sharing permissions for OneDrive and SharePoint<br/><br/>Submit agents to the marketplace (according to Microsoft 365 administrator controls and tenant policies) |

Administrators can manage who can create and share agents. See the following articles:

- [Manage Microsoft 365 Copilot agents in the Microsoft 365 admin center](https://review.learn.microsoft.com/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?toc=%2Fcopilot%2Fmicrosoft-365%2Ftoc.json&bc=%2Fcopilot%2Fmicrosoft-365%2Fbreadcrumb%2Ftoc.json&view=o365-worldwide&branch=main#manage-access-to-copilot-agents)
- [Who can create, build, and share Copilot extensibility options?](#who-can-create-build-and-share-copilot-extensibility-options) (in this article)
- [Copilot Control System management controls](https://learn.microsoft.com/en-us/copilot/microsoft-365/copilot-control-system/management-controls)

## Can administrators see who does what? 

Yes. Reports are available to help administrators monitor licenses, agents, and deployments. Custom reports can also be created. See Copilot Control System measurement and reporting.

## Can administrators control data sources used by Copilot, agents, connectors, and notebooks? What can administrators regulate?

Yes, administrators can control data sources that are used. Administrators can also control Copilot features, sharing, block/unblock agents, and more. In general, here are resources administrators can use: 

- Administrators use Copilot Control System for agents and Power Platform Admin Center for connectors
- Microsoft Purview provides unified audit and compliance across all extensibility options
- Inventory and lifecycle controls help manage shared or ownerless agents
