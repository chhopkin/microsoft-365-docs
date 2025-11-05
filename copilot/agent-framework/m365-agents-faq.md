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

- Copilot agents extend the functionality of Copilot by acting as specialized AI assistants tailored to specific domains or use cases. You can use agents to extend Copilot's knowledge, automate workflows, and deliver tailored user experiences in Microsoft Teams, Outlook, SharePoint, or custom apps. You can create a declarative agent using Copilot's AI infrastructure, model, and orchestrator. Or, for complex workflows or specific language models, you can create a custom agent. For more information, see Agents for Microsoft 365 Copilot.
- Copilot connectors enable you to ingest data, such as unstructured, line-of-business data, into the Microsoft Graph so that Copilot can reason over that data alongside other data. There are more than 100 prebuilt Copilot connectors available, and the Connectors API can be used to create custom connectors. For more information, see Microsoft 365 Copilot Connectors.

To get started, review our planning guide, which can help you define your business need, and determine whether you need an agent or a connector. Also see Based on my use cases, how do I know which accessibility option to implement?.

### What extensibility options are available for Copilot Agents?

Extensibility options include using Copilot out of the box (OOTB), agents, connectors, and Notebooks. The following table summarizes these options, including prebuilt, custom, and advanced scenarios. 

| Extensibility option | Prebuilt | Customized | Advanced |
|--|--|--|--|
| Copilot (OOTB) | Unified Copilot experience in Microsoft 365 Apps with reasoning over your work graph and citations<br/><br/>Works with admin-approved data/controls by default | Extend Copilot with agents that add knowledge (instructions + grounding) and skills (actions) surfaced directly in Copilot Chat/Teams<br/><br/>Enable via admin | Enterprise-grade controls and visibility (usage, inventory) plus expanded admin and Graph APIs (inventory/details) for app/agent governance across hosts |
| Agents <br/>(Declarative or custom) | SharePoint and other Microsoft quick-start agents that connect to site libraries to answer team questions and automate simple workflows<br/><br/>Discoverable in the Copilot experience. | Declarative/custom agents built in Copilot Studio or Teams Toolkit with instructions, knowledge sources, and actions (plugins/Power Platform connectors)<br/><br/>Publish to run inside Copilot | Autonomous & multi-agent patterns<br/><br/>Agent-to-agent collaboration<br/><br/>Computer Use (vision to operate apps)<br/><br/>Voice agents<br/><br/>Enterprise governance and admin manageability | 
| Connectors | Prebuilt Graph connectors catalog to index external systems (e.g., GitHub, Slack, Zendesk) into Microsoft Graph for grounding in Copilot and agents | Build your own<br/><br/>Create custom Graph connectors and Power Platform connectors<br/><br/>Makers can attach these as Copilot connectors to agents for knowledge and actions | Fabric AI skills + connector governance<br/><br/>Curate an org catalog<br/><br/>Manage usage in the Microsoft 365 admin center<br/><br/>Combine real-time actions with indexed knowledge in agent designs |
| Notebooks | Copilot Notebooks as a first-party space inside Copilot for structured problem-solving alongside Chat<br/><br/>Part of the unified experience with Chat, Agents, and Create | Use Notebooks to compose multi-step prompts, attach/ground with org content, and hand off to agents you (or your team) created to perform steps<br/><br/>Keeps context continuity | Pair Notebooks with advanced agents (e.g., Researcher/Analyst style reasoning) to orchestrate deeper investigations and repeatable workflows across data/connectors |

