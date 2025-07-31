---
title: "Security & governance in Copilot Control System"
description: "Use the security and governance framework of Copilot Control System to handle data security, compliance, and risks associated with Microsoft 365 Copilot, Copilot Chat, Microsoft Copilot studio, and agents."
author: aczechowski
ms.author: aaroncz
manager: dansimp
ms.reviewer: bensum
ms.service: microsoft-365-copilot
ms.topic: solution-overview
ms.date: 07/29/2025
---

# Security & governance in Copilot Control System

When you implement AI, you face challenges related to data security, compliance, and specific risks associated with AI applications. To mitigate these issues, use a security and governance framework such as the Copilot Control System. It provides foundational controls and integrates with tools like [Microsoft Purview](/purview/ai-microsoft-purview) and [Microsoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps). To enhance AI responses while controlling access to AI applications, you also need to audit AI interactions, adhere to regulatory requirements, and manage the use of web search data.

:::image type="content" source="media/security-governance.png" alt-text="A diagram of the Copilot Control System framework highlighting the Security & Governance pillar.":::

> [!NOTE]
> Three main pillars make up the [Copilot Control System](overview.md):
>
> - **Security and governance** (this article)
> - [Management controls](management-controls.md)
> - [Measurement & reporting](measurement-reporting.md)

## Data security

- Use SharePoint Advanced Management to [Initiate site access reviews for data access governance reports](/sharepoint/site-access-review) in the SharePoint admin center.

- Use SharePoint Advanced Management built-in site governance tools to identify and reduce potential oversharing with [Data access governance reports for SharePoint sites](/sharepoint/data-access-governance-reports).

- [Microsoft Purview data security and compliance protections for generative AI apps](/purview/ai-microsoft-purview): Use Microsoft Purview to mitigate and manage the risks associated with AI usage, and implement corresponding protection and governance controls.

  - Manage data and apply encryption with [Purview sensitivity labels](/purview/encryption-sensitivity-labels).

  - To exclude Copilot from processing specific files, use [Microsoft Purview Data Loss Prevention (DLP) policy locations](/purview/dlp-microsoft365-copilot-location-learn-about).

  - To restrict or block a user if the system detects a pattern of risky behavior, use [Microsoft Purview Insider Risk Management policy templates](/purview/insider-risk-management-policy-templates).

## AI security

Copilot already includes built-in protection against [prompt injection attacks](/copilot/microsoft-365/microsoft-365-copilot-privacy) and [harmful content protection](/copilot/microsoft-365/microsoft-365-copilot-privacy). Microsoft also provides foundational controls in [Entra to restrict which AI apps your users can access](/entra/identity-platform/howto-restrict-your-app-to-a-set-of-users). Further optimization controls are found in Defender for Cloud Apps, which can help security teams detect suspicious interactions with Copilot (e.g., sensitive data access from risky IP), and provide highly detailed alerts to support investigations. We are making significant investments in this AI security, with more innovation on the way.

## Compliance & privacy

Copilot provides foundational [controls and visibility over web-grounded search](/copilot/microsoft-365/manage-public-web-access). Purview's foundational controls include the ability to [audit activity](/purview/audit-search). These controls also include enforcement of [retention policies](/purview/retention-policies-copilot), the ability to respond to litigation holds, and support defensible [eDiscovery](/purview/ediscovery-content-search-overview) of AI interactions. Optimized controls, found in Purview, provide alerts and [investigative tools for potential compliance and ethical violations](/purview/communication-compliance). They also include compliance templates to help you adhere to applicable regulations.

## Related content

- [Data, Privacy, and Security for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-privacy)

- [SharePoint Advanced Management](/sharepoint/advanced-management)

- [Copilot Control System - Microsoft Adoption](https://adoption.microsoft.com/copilot/control-system/)
