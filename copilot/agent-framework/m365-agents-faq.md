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

## Getting started – Foundation 

### Do I need an agent or a connector? How do I get started?

Whether you need an agent or a connector depends on your business needs. Copilot agents support specialized workflows and experiences, whereas connectors help add knowledge to Microsoft 365 intelligence experiences, including Copilot.

- Copilot agents extend the functionality of Copilot by acting as specialized AI assistants tailored to specific domains or use cases. You can use agents to extend Copilot's knowledge, automate workflows, and deliver tailored user experiences in Microsoft Teams, Outlook, SharePoint, or custom apps. You can create a declarative agent using Copilot's AI infrastructure, model, and orchestrator. Or, for complex workflows or specific language models, you can create a custom agent. For more information, see [Agents for Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/agents-overview).

- Copilot connectors enable you to ingest data, such as unstructured, line-of-business data, into the Microsoft Graph so that Copilot can reason over that data alongside other data. There are more than 100 prebuilt Copilot connectors available, and the Connectors API can be used to create custom connectors. For more information, see [Microsoft 365 Copilot Connectors](/microsoft-365-copilot/extensibility/overview-copilot-connector).

To get started, [review our planning guide](/microsoft-365-copilot/extensibility/planning-guide), which can help you define your business need, and determine whether you need an agent or a connector. Also see Based on my use cases, how do I know which accessibility option to implement?.

### What extensibility options are available for Copilot Agents?

Extensibility options include using Copilot out of the box (OOTB), agents, connectors, and Notebooks. The following table summarizes these options, including prebuilt, custom, and advanced scenarios. 

| Extensibility option | Prebuilt | Customized | Advanced |
|--|--|--|--|
| Copilot (OOTB) | Unified Copilot experience in Microsoft 365 Apps with reasoning over your work graph and citations<br/><br/>Works with admin-approved data/controls by default | Extend Copilot with agents that add knowledge (instructions + grounding) and skills (actions) surfaced directly in Copilot Chat/Teams<br/><br/>Enable via admin | Enterprise-grade controls and visibility (usage, inventory) plus expanded admin and Graph APIs (inventory/details) for app/agent governance across hosts |
| Agents <br/>(Declarative or custom) | SharePoint and other Microsoft quick-start agents that connect to site libraries to answer team questions and automate simple workflows<br/><br/>Discoverable in the Copilot experience. | Declarative or custom agents built in Copilot Studio or Teams Toolkit with instructions, knowledge sources, and actions (plugins/Power Platform connectors)<br/><br/>Publish to run inside Copilot | Autonomous & multi-agent patterns<br/><br/>Agent-to-agent collaboration<br/><br/>Computer Use (vision to operate apps)<br/><br/>Voice agents<br/><br/>Enterprise governance and admin manageability | 
| Connectors | Prebuilt Graph connectors catalog to index external systems (e.g., GitHub, Slack, Zendesk) into Microsoft Graph for grounding in Copilot and agents | Build your own<br/><br/>Create custom Graph connectors and Power Platform connectors<br/><br/>Makers can attach these as Copilot connectors to agents for knowledge and actions | Fabric AI skills + connector governance<br/><br/>Curate an org catalog<br/><br/>Manage usage in the Microsoft 365 admin center<br/><br/>Combine real-time actions with indexed knowledge in agent designs |
| Notebooks | Copilot Notebooks as a first-party space inside Copilot for structured problem-solving alongside Chat<br/><br/>Part of the unified experience with Chat, Agents, and Create | Use Notebooks to compose multi-step prompts, attach/ground with org content, and hand off to agents you (or your team) created to perform steps<br/><br/>Keeps context continuity | Pair Notebooks with advanced agents (e.g., Researcher/Analyst style reasoning) to orchestrate deeper investigations and repeatable workflows across data/connectors |

### Who can create, build, and share Copilot extensibility options?

The following table summarizes what users, makers, developers, and administrators can do across extensibility options.

| Extensibility option | Who Can Create | Who Can Build (Customize) | Who Can Share |
|--|--|--|--|
| Copilot (OOTB) | End users with a Microsoft 365 Copilot license (no extra steps required) | Not applicable (OOTB Copilot is prebuilt; customization happens via agents or connectors) | End users can share Copilot outputs (documents, chats) using standard Microsoft 365 sharing permissions; governed by existing Microsoft 365 policies |
| Agents | End users: Create declarative agents in Copilot Studio (lite) or SharePoint if enabled by tenant settings (requires Copilot license or subscription)<br/><br/>Makers: Use Copilot Studio (lite or full) for low-code agents<br/><br/>Developers: Use Copilot Studio SDK or Agents Toolkit for pro-code agents | Makers and developers can add actions, connectors, and advanced logic in Copilot Studio or via the Microsoft 365 Agents Toolkit | 
Members of your organization can [sideload agents](/copilot/microsoft-365/agent-framework/agent-policies/agent-sideload), [share agents](/microsoft-365/admin/manage/manage-shared-agents), and [publish agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps#publish-agents). Additionally, developers can [submit agents to the marketplace](/copilot/microsoft-365/agent-framework/agent-policies/agent-submit-marketplace). These capabilities are governed by tenant policies and admin controls in Microsoft 365 admin center | 
| Connectors | Admins/Makers: Create custom connectors in Power Platform or Graph API; requires appropriate environment roles and DLP compliance | Developers can build advanced connectors and integrate with external APIs; subject to security reviews for enterprise use | Sharing connectors is controlled by Power Platform environment policies and admin governance (Managed Environments, DLP) |
| Notebooks  | Any user with access to Microsoft 365 Copilot can create and use notebooks for structured workflows; no extra license beyond Copilot | Advanced orchestration possible when paired with agents and connectors; typically by makers or developers | Sharing follows standard Microsoft 365 file-sharing permissions (OneDrive/SharePoint) |

### What tools do I need to create, build, implement, and use Copilot extensibility options?

The following table summarizes tools that users, makers, developers, and admins can use with Copilot, agents, connectors, notebooks, and supporting tools.

| Extensibility option | Users | Makers | Developers | Admins |
|--|--|--|--|--|
| Copilot (OOTB) | Use Copilot in Microsoft 365 apps (Word, Excel, PowerPoint, Outlook, Teams) | N/A | N/A | Enable Copilot in Microsoft 365 Admin Center; manage tenant settings |
| Agents <br/>(declarative or custom) | Interact with agents in Copilot Chat <br/><br/>Build low-code declarative agents in Copilot Studio (lite) | Build low-code agents in Copilot Studio (full); add actions/connectors | Create pro-code agents using Teams Toolkit or Agents SDK | Control agent creation/sharing in Admin Center; apply governance policies |
| Connectors | Use connectors indirectly via Copilot | Create custom connectors in Power Platform or Copilot Studio | Build advanced connectors via Graph Connector APIs or REST/OpenAPI | Approve connectors; enforce DLP and compliance in Power Platform Admin Center |
| Notebooks | Create and use Copilot Notebooks for structured workflows | Pair notebooks with agents/connectors for orchestration | Extend notebooks with advanced logic and integrations | Manage sharing and compliance via Microsoft 365 Admin Center |
| Supporting Tools | Access Copilot features in apps | Use Copilot Studio, Power Platform for extensibility | Use Teams Toolkit, Azure AI Studio, SDKs for advanced builds | Govern extensibility with Microsoft Purview, Copilot Control System, and Admin Centers |

### What governance or controls does each extensibility option have?

For all extensibility options, your organization has the following governance tools available:

- [Copilot Control System](/copilot/microsoft-365/copilot-control-system/overview): Unified dashboard for managing Copilot and agents
- [Microsoft Purview](/purview/ai-microsoft-purview): Compliance, audit, and eDiscovery across all extensibility options
- Admin Centers: [Microsoft 365 Admin Center](/microsoft-365/admin/admin-overview/admin-center-overview) and [Power Platform Admin Center](/microsoft-365/admin/admin-overview/admin-center-overview) for configuration and enforcement.

The following table summarizes governance and control features for extensibility options:
