---
title: Create Word, Excel, and PowerPoint files with Claude in Copilot (Frontier)
description: Create Word, Excel, and PowerPoint files with Claude in Copilot (Frontier).
f1.keywords:
- NOCSH
ms.author: smbhardwaj
author: smritib17
manager: scotvidican
ms.date: 11/12/2025
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

# Get started with Word, Excel, and PowerPoint (Frontier) agents in Microsoft 365 Copilot

> [!IMPORTANT]
> Word, Excel, and PowerPoint (Frontier) agents in Microsoft 365 Copilot is currently only available in the Frontier early access program for eligible Microsoft 365 plans. Frontier includes early access to experimental features, which means features may change as Microsoft improves them. Early Frontier features are initially available in English for U.S.-based subscribers. Availability will expand over time. For more information about the Frontier program, see [What is Frontier?](https://support.microsoft.com/topic/what-is-frontier-17c671e0-1906-4d9d-892c-68e11fbff4c7).

Microsoft 365 is expanding its integration with Anthropic's Claude AI within Copilot, allowing users to create Word, Excel, and PowerPoint files using advanced AI-driven creation agents.

## Before you begin

To use Word, Excel, and PowerPoint Agents, you require a Microsoft 365 Copilot license with Frontier features enabled. Additionally, Administrators should be opted in to the Frontier program.

## Admin Enablement  

A global administrator must enable Claude models in the Microsoft 365 admin center, agreeing to Anthropic's terms for users to access creation agents.

### Connect to Anthropic in the Microsoft 365 admin center

For detailed steps on how to connect to Anthropic's AI models, see [Connect to Anthropic's AI models](connect-to-ai-models.md#connect-to-anthropic-in-the-microsoft-365-admin-center).

## Data Privacy and Security

> [!IMPORTANT]
> When your organization chooses to use an Anthropic model, your organization is choosing to share your data with Anthropic to power the features. This data is processed outside all Microsoft‑managed environments and audit controls, therefore Microsoft's customer agreements, including the [Product Terms](https://www.microsoft.com/licensing/terms?msockid=344e0e6ad66c6b3e19441848d7416abd) and [Data Processing Addendum](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA?lang=18&msockid=344e0e6ad66c6b3e19441848d7416abd) don't apply.
> In addition, Microsoft's data‑residency commitments, audit and compliance requirements, service level agreements, and Customer Copyright Commitment don't apply to your use of Anthropic services. Instead, use of Anthropic's services is governed by Anthropic's [Commercial Terms of Service](https://www.anthropic.com/legal/commercial-terms) and Anthropic's [Data Processing Addendum](https://www.anthropic.com/legal/data-processing-addendum).

## Enterprise Data

Word, Excel, and PowerPoint Agents support implicit enterprise grounding for users with a Copilot license. Implicit enterprise data grounding means that these Agents can use your organization's data (files emails, meetings, sites you have access to) through Microsoft Graph, like other Copilot experiences.  

With respect to our Claude integration, this access is controlled by Microsoft. Microsoft conducts the search and passes relevant context to Claude, ensuring that only data the user has access to is provided; sensitivity labels are respected, and so on.

All generated documents are saved to the user's OneDrive. This process ensures the final content resides within your tenant's environment for proper governance.

## User awareness and consent

Users receive clear notice before first use, informing them that data is being processed by Claude with a link to detailed data handling information.

The Copilot interface displays a clear notice to users before they first send data to Claude. The notice informs users that Anthropic's Claude will process their request and includes a **Learn more** link to a support article for details on data handling.

## Admin Controls

Administrators, after enabling, can disable access to Anthropic models at any time. If your organization decides to stop using Claude, you can block the provider via the admin center, which removes the option for users.

If Claude usage is blocked, users are prevented from using the new Word, Excel, and PowerPoint Agents.  

## Disable connection to Anthropic

For detailed steps on how to disable the connection to Anthropic's AI models, see [Connect to Anthropic's AI models](connect-to-ai-models.md#disable-connection-to-anthropic).

## Limitations and support

The feature is in preview, English-only, and users should review AI-generated content for accuracy.

Feedback mechanisms exist for reporting inaccuracies or inappropriate content; support articles provide further guidance.

## Related content

- [Word, Excel, and PowerPoint agents (Frontier) in Microsoft 365 Copilot FAQs](faq-office-agents.yml)
- [Connect to Anthropic's AI models](connect-to-ai-models.md)
- [What is Frontier?](https://support.microsoft.com/topic/what-is-frontier-17c671e0-1906-4d9d-892c-68e11fbff4c7)
- Support article. Need to add a link.