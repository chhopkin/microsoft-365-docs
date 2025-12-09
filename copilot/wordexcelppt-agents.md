---
title: Create files with Word, Excel, and PowerPoint Agents (Frontier) in Microsoft 365 Copilot
description: Create files with Word, Excel, and PowerPoint Agents (Frontier) in Microsoft 365 Copilot.
f1.keywords:
- NOCSH
ms.author: smbhardwaj
author: smritib17
manager: scotvidican
ms.date: 11/18/2025
audience: Admin
ms.reviewer: HollyPollock
ms.topic: overview
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- trust-pod
ms.custom: [copilot-learning-hub]
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Get started with Word, Excel, and PowerPoint Agents (Frontier) in Microsoft 365 Copilot

> [!IMPORTANT]
> Word, Excel, and PowerPoint Agents (Frontier) in Microsoft 365 Copilot is currently only available in the [Frontier early access program](https://adoption.microsoft.com/copilot/frontier-program/) with a Microsoft 365 Copilot subscription. Frontier includes early access to experimental features, which means features may change as Microsoft improves them. [Learn about Frontier?](https://support.microsoft.com/topic/what-is-frontier-17c671e0-1906-4d9d-892c-68e11fbff4c7).

Microsoft 365 is expanding its integration with reasoning models within Copilot, allowing users to create Word, Excel, and PowerPoint files using advanced AI-driven creation agents.

## Before you begin

To use Word, Excel, and PowerPoint Agents, you require a Microsoft 365 Copilot license with Frontier features enabled. Additionally, Administrators should be opted in to the Frontier program.

## Admin enablement and controls  

These agents use Anthropic reasoning models. A global administrator must enable the reasoning models in the Microsoft 365 admin center, agreeing to the model's terms for users to access creation agents. In addition, Frontier must be enabled for the tenant or specific users, the Anthropic model toggle must be turned on, and the user needs a Microsoft 365 Copilot license assigned. These requirements are mandatory for Word, Excel, and PowerPoint Agents to function.

Administrators, after enabling, can disable access to reasoning models at any time. If your organization decides to stop using the reasoning model, you can block the provider via the admin center, which removes the option for users. Word, Excel, and PowerPoint Agents are installed by Microsoft and will appear in the Tools menu and left navigation pane for Microsoft 365 Copilot licensed users (in the Agents list in the Frontier section and in the All Agents section), assuming both Anthropic and Frontier have been enabled for the tenant. Admins can manage these agents similar to other agents that were installed by [Microsoft](copilot-agent-install.md).

If the reasoning model's usage is blocked, users are prevented from seeing the agents (in the Tools menu and in the left rail of the Microsoft 365 Copilot app) and using the new Word, Excel, and PowerPoint Agents.

### Connect to reasoning models in the Microsoft 365 admin center

For detailed steps on how to connect to Anthropic's AI models, see [Connect to Anthropic's AI models](connect-to-ai-models.md#connect-to-anthropic-in-the-microsoft-365-admin-center).

### Disable connection to reasoning models

For detailed steps on how to disable the connection to Anthropic's AI models, see [Connect to Anthropic's AI models](connect-to-ai-models.md#disable-connection-to-anthropic).

## Data Privacy and Security

> [!IMPORTANT]
> Until January 7th, 2026, when your organization chooses to share data with Anthropic (as an independent data processor) to power Claude for Microsoft 365 Copilot, this data is processed outside all Microsoft managed environments and audit controls, therefore Microsoft's customer agreements, including the [Product Terms](https://www.microsoft.com/licensing/terms?msockid=344e0e6ad66c6b3e19441848d7416abd) and [Data Processing Addendum](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA?lang=18&msockid=344e0e6ad66c6b3e19441848d7416abd) don't apply. In addition, Microsoft's data residency commitments, audit and compliance requirements, service level agreements, and Customer Copyright Commitment don't apply to your use of Anthropic services. Instead, use of Anthropic's services is governed by Anthropic's [Commercial Terms of Service](https://www.anthropic.com/legal/commercial-terms) and Anthropic's [Data Processing Addendum](https://www.anthropic.com/legal/data-processing-addendum).

Starting on January 7th, as a subprocessor, Anthropic will operate under Microsoft’s direction and contractual safeguards. This includes coverage under the [Microsoft Data Protection Addendum (DPA)](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA?lang=18&msockid=344e0e6ad66c6b3e19441848d7416abd) and [Product Terms](https://www.microsoft.com/licensing/terms?msockid=344e0e6ad66c6b3e19441848d7416abd) with Microsoft remaining accountable for Anthropic’s compliance under our contractual commitments. In addition, use of Anthropic models in Microsoft 365 Copilot falls under our [Enterprise Data Protection](enterprise-data-protection.md). For more information on Anthropic as a subprocessor, see [Anthropic as a subprocessor for Microsoft Online Services](connect-to-ai-subprocessor.md).

## Enterprise Data

Word, and PowerPoint Agents can access organizational data for users with a Copilot license. These agents use Microsoft Graph to retrieve information from files, emails, meetings, and sites that you personally have permission to access, similar to other Copilot experiences.

Microsoft ensures secure handling of data, when integrating with reasoning models. Microsoft performs all searches, and only relevant context is shared with the reasoning model. So the data provided is limited to what you are authorized to view, with sensitivity labels and compliance policies fully respected.

Generated content is stored securely in OneDrive. All documents created by these agents are saved within your organization's tenant, maintaining governance and compliance standards.

## Limitations and support

The feature is in preview, English-only, and users should review AI-generated content for accuracy.

Feedback mechanisms exist for reporting inaccuracies or inappropriate content; support articles provide further guidance.

## Related content

- [Connect to Anthropic's AI models](connect-to-ai-models.md)
- [What is Frontier?](https://support.microsoft.com/topic/what-is-frontier-17c671e0-1906-4d9d-892c-68e11fbff4c7)
- [Support article](https://support.microsoft.com/topic/76691f5e-bb19-4029-a34d-33a00e0a0c4f)
- [Word, Excel, and PowerPoint Agents FAQ](faq-wordexcelppt-agents.yml)