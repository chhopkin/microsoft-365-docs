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

# Microsoft 365 Agents Checklist

This checklist is intended to assist admins with the successful deployment of Copilot agent governance. It's structured in a checklist format, providing a comprehensive guide for a streamlined setup process.

Required administrators for the engagement:

1. **Microsoft 365 admin** - Setup Copilot agent and connectors settings.
2. **Microsoft Power Platform admin** - Setup Copilot Studio policies and settings.
3. **Microsoft 365 Search admin** - Setup Microsoft 365 Graph connector configurations. 
4. **Microsoft Azure admin** - Setup Azure subscription configurations. 

Deployment phases:

  :::image type="content" source="/copilot/microsoft-365/agent-framework/media/m365-agents-checklist/agent-deployment-phases.png" alt-text="Diagram of the Copilot agent deployment phases."  lightbox="/copilot/microsoft-365/agent-framework/media/m365-agents-checklist/agent-deployment-phases.png":::
  

Downloadable resources:

- [Visual Checklist and deployment mind map](m365-agents-visual-map.md)
- [Microsoft 365 Copilot agents blueprint](m365-agents-blue-print.md)

## Deployment checklist

### Control user access to agents using administrative controls

| Step  | Task  | Owner  | Status  |
|---|---|---|---|
| 1  | Choose the right Copilot Studio experience  | Copilot Administrator<br>SharePoint administrator<br>Copilot Studio Administrator  |  |
| 2  | Control access to Copilot agents<br>Admins can enable/disable copilot extensibility by setting who can access to agents. Following roles applies to manage agents: AI Admin, Global Admin and Global Readers can manage Agents in Microsoft 365 admin center.<br>Choose whether:<ul><li>**All users**: [*Default*] meaning all users in the organization can access agent, subject to the existing app policies and user assignments.</li><li>**No users**: No users in the organization can access agents, and external agents are disabled in the agents flyout. This option also hides agents from the list of available and deployed apps.</li><li>**Specific users/groups**: Admins can specify users or groups in their organization to have access to agents.<p>For more information, see Manage access to Copilot agents.  | Copilot Administrator<br>Microsoft 365 Administrator  |  |

