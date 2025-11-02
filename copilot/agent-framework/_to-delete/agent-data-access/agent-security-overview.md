---
title: Agent security, compliance, and governance overview
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
description: Learn about controlling data access for agent security, compliance, and governance.
customer-intent: As an administrator or business decision maker, I want to understand the measures I should implement so that I can ensure my organization's data is protected while leveraging AI capabilities of Microsoft 365 Copilot agents.
---

# Control data access for agents

When you implement Microsoft 365 Copilot agents, you might face new and amplified risks related to security, compliance, privacy, and governance. To help ensure that the data agents access is appropriate, data access should be controlled and limited to only those agents that need it. //To help you protect your organization while still applying AI capabilities of Microsoft 365 Copilot agents, this article provides guidance on key areas to consider and actions to take to protect data, enforce policy, and meet regulatory obligations for agents at scale.//


## Control agent access to third-party systems

[Microsoft 365 Copilot connectors](/microsoft-365-copilot/extensibility/overview-copilot-connector) allow you to ingest external content into Microsoft Graph so that Copilot agents can access and use that content. When you use Copilot connectors to connect to third-party systems, it's important to control agent access to those systems to help ensure that only appropriate data is shared with the agents. When using Copilot Connectors you should consider the following:
- **Limit connector scope**: When configuring a Copilot connector, limit the scope of data that the connector can access. Only include the specific data that agents need to perform their tasks.


#### Control Graph Connector agent access to on-premises data 



## Control oversharing SharePoint content

Preventing oversharing data helps ensure that sensitive data remains protected, and access is limited to only those users who need it, including Copilot agents. The following combination assists you with controlling oversharing:
- [Microsoft Purview Data Security Posture Management (DSPM) for AI](/purview/dspm-for-ai)
- [SharePoint Advanced Management](/sharepoint/advanced-management)
- Deployment blueprint


## Auditing and reporting


## Data security



## Data compliance

