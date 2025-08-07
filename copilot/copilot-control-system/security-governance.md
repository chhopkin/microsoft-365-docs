---
title: "Security and governance in Copilot Control System"
description: "Use the security and governance framework of Copilot Control System to handle data security, compliance, and risks associated with Microsoft 365 Copilot, Copilot Chat, Microsoft Copilot Studio, and agents."
author: aczechowski
ms.author: aaroncz
manager: dansimp
ms.reviewer: bensum
ms.service: microsoft-365-copilot
ms.topic: solution-overview
ms.date: 08/06/2025
---

# Security and governance in Copilot Control System

When you implement AI, you face challenges related to data security, compliance, and specific risks associated with AI applications. The Copilot Control System security and governance framework helps you mitigate these issues in Microsoft 365 Copilot, Copilot Chat, Copilot Studio, and agents.

To enhance AI responses while controlling access to AI applications, you also need to:

- Audit AI interactions
- Adhere to regulatory requirements
- Manage the use of web search data

This article refers to *foundational* and *optimized* controls. In general, those terms refer to the following products and services:

- The Microsoft 365 admin center provides many *foundational* controls for security and governance.
- When you use [Microsoft Purview](/purview/ai-microsoft-purview) and [Microsoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps), they provide further *optimized* controls.


***temporary image***

:::image type="content" source="media/security-governance.png" alt-text="A diagram of the Copilot Control System framework highlighting the Security and Governance pillar.":::

> [!NOTE]
> Three main pillars make up the [Copilot Control System](overview.md):
>
> - **Security and governance** (this article)
> - [Management controls](management-controls.md)
> - [Measurement and reporting](measurement-reporting.md)

The security and governance pillar of the Copilot Control System focuses on the following key capabilities:

- Data security
- AI security
- Compliance and privacy

## Data security

[SharePoint Advanced Management](/sharepoint/advanced-management) is a foundational component for managing your organization's data. For example:

- Use the SharePoint admin center to [initiate site access reviews for data access governance reports](/sharepoint/site-access-review).

- Use SharePoint Advanced Management built-in site governance tools to identify and reduce potential oversharing with [Data access governance reports for SharePoint sites](/sharepoint/data-access-governance-reports).

- Protect Copilot responses and created documents with automatic inheritance of data classification.

[Microsoft Purview](/purview/ai-microsoft-purview) provides an optimized experience by adding greater visibility and control. For example:

- Use Microsoft Purview to mitigate and manage the risks associated with AI usage, and implement protection and governance controls.

  - Manage data and apply encryption with [Purview sensitivity labels](/purview/encryption-sensitivity-labels).

  - To exclude Copilot from processing specific files, use [Microsoft Purview Data Loss Prevention (DLP) policy locations](/purview/dlp-microsoft365-copilot-location-learn-about).

  - To restrict or block a user if the system detects a pattern of risky behavior, use [Microsoft Purview Insider Risk Management policy templates](/purview/insider-risk-management-policy-templates).

## AI security

Copilot already includes built-in protections against AI-based attacks, which include, but aren't limited to, the following protections:

- [Block prompt injection attacks](../microsoft-365-copilot-privacy.md#does-copilot-block-prompt-injections-jailbreak-attacks)
- [Block harmful content](../microsoft-365-copilot-privacy.md#how-does-copilot-block-harmful-content)
- [Detect protected material](../microsoft-365-copilot-privacy.md#does-copilot-provide-protected-material-detection)

Microsoft also provides foundational controls in Microsoft Entra to restrict which AI apps your users can access. For more information, see [Restrict a Microsoft Entra app to a set of users](/entra/identity-platform/howto-restrict-your-app-to-a-set-of-users).

[Microsoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps) provides further optimized controls. These controls can help you detect suspicious interactions with Copilot. For example, is Copilot accessing sensitive data from a risky IP address. If necessary, Defender also provides highly detailed alerts to support investigations.

## Compliance and privacy

Copilot provides foundational controls and visibility over web-grounded search. For more information, see [Data, privacy, and security for web search in Microsoft 365 Copilot and Microsoft 365 Copilot Chat](../manage-public-web-access.md).

Purview has both foundational and optimized controls to support your organization's compliance needs.

- Purview *foundational* controls:
  - To investigate user activity, [search the audit log](/purview/audit-search).
  - Enforce [retention policies](/purview/retention-policies-copilot).
  - Respond to litigation holds.
  - Support defensible [eDiscovery](/purview/edisc) of AI interactions.

- Purview *optimized* controls:
  - Provide alerts and [investigative tools for potential compliance and ethical violations](/purview/communication-compliance).
  - Compliance templates to help you adhere to applicable regulations.

## Zero Trust

Microsoft provides detailed documentation for implementing the principles of *Zero Trust* in your organization, and specific considerations for Microsoft 365 Copilot and Copilot Chat. Zero Trust isn't a product or service, but an approach in designing and implementing the following set of security principles:

- Verify explicitly
- Use least privileged access
- Assume breach

For more information, see [Use Zero Trust security to prepare for Copilot](/security/zero-trust/copilots/apply-zero-trust-copilots-overview).

## Related content

- [Data, Privacy, and Security for Microsoft 365 Copilot](../microsoft-365-copilot-privacy.md)

- [SharePoint Advanced Management](/sharepoint/advanced-management)

- [Copilot Control System - Microsoft Adoption](https://adoption.microsoft.com/copilot/control-system/)
