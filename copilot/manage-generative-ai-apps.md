---
title: Manage generative AI apps for your organization
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.reviewer: 
ms.date: 10/21/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- trust-pod
- magic-ai-copilot
description: Learn how to discover, monitor, and manage the generative AI apps your organization uses. 
appliesto:
- ✅ Microsoft 365 Copilot
---

# Manage generative AI apps for your organization

As people embrace and incorporate [generative AI apps](/ai/playbook/technology-guidance/generative-ai/), such as Microsoft 365 Copilot and non-Microsoft AI apps into daily work, it's important for your organization's security team to be able to manage those apps. Microsoft applies a multi-layered, defense-in-depth strategy to secure Microsoft 365 Copilot at every level (see [What Microsoft does to secure Microsoft 365 Copilot](microsoft-365-copilot-ai-security.md#what-microsoft-does-to-secure-microsoft-365-copilot)). 

But what about non-Microsoft AI apps? 

Using capabilities in [Microsoft Defender XDR](/defender-xdr/microsoft-365-defender), which includes Microsoft Defender for Cloud Apps and Microsoft Defender for Endpoint, your security team can enable people in your organization to use generative AI apps more securely, including Microsoft and non-Microsoft AI apps.

Discovering, monitoring, and managing AI apps is essential to prevent data leaks, maintain compliance, enforce governance, and uphold trust in enterprise AI adoption.

## Before you begin

- **Make sure you have appropriate permissions assigned** to perform the tasks in this article.
   - See [Microsoft 365 and Microsoft Entra roles with access to Defender for Cloud Apps](/defender-cloud-apps/manage-admins#microsoft-365-and-microsoft-entra-roles-with-access-to-defender-for-cloud-apps)


- **[Set up Microsoft Defender XDR](/defender-xdr/pilot-deploy-overview)**, which includes these components:
   - [Microsoft Defender for Identity](/defender-xdr/pilot-deploy-defender-identity)
   - [Microsoft Defender for Office 365](/defender-xdr/pilot-deploy-defender-office-365)
   - [Microsoft Defender for Endpoint](/defender-xdr/pilot-deploy-defender-endpoint)
   - [Microsoft Defender for Cloud Apps](/defender-xdr/pilot-deploy-defender-cloud-apps)

<!---
- **Configure Purview**. Select one or more of the [Microsoft Purview deployment models](/purview/deploymentmodels/depmod-overview), which include:
   - [Secure by default](/purview/deploymentmodels/depmod-securebydefault-intro)
   - [Address internal oversharing concerns for Microsoft 365 Copilot deployment](https://aka.ms/Copilot/OversharingBlueprintLearn)
   - [Prevent data leak to shadow AI with Microsoft](/purview/deploymentmodels/depmod-data-leak-shadow-ai-intro)
   - [Lightweight guide to mitigate data leakage](https://aka.ms/Purview_LightweightGuide_PDF)
   - [Secure agents in Microsoft 365 with Purview](https://aka.ms/PurviewDeploymentModels/SecureAgents-pdf)
   - [Purview Data Security Posture Management](https://aka.ms/DSPMBlueprintPDF)
--->
## Discover generative AI apps that are in use in your organization

Use the Microsoft Defender portal to see a list of AI apps your organization is using. Defender for Cloud Apps provides a catalog of apps with security and compliance risk scores.

1. Go to the [Microsoft Defender portal](https://security.microsoft.com) and sign in.

2. In the navigation pane, expand **Cloud apps**, and then select **Cloud app catalog**.

3. In the **Category** filter, select **Generative AI**. 

4. Review the list of apps, along with their risk scores. For more information, see [Find your cloud app and calculate risk scores](/defender-cloud-apps/risk-score).

## Set up a policy to create an alert for new generative AI apps

> [!NOTE]
> Before you begin, review the [prerequisites](/defender-cloud-apps/governance-discovery#prerequisites).

1. Go to the [Microsoft Defender portal](https://security.microsoft.com) and sign in.

2. In the navigation pane, select **Cloud apps** > **Cloud discovery**.

3. 

## Block specific generative AI apps

PROCEDURE

## Quick reference table: AI app risk mitigation and Microsoft solutions

| Risk of unmanaged AI apps | Recommendations  |
|--|--|--|
| Data leakage and intellecutal property (IP) exposure | Discover unscanctioned AI apps using [Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps)<br/><br/>Apply DLP policies using [Purview DLP](/purview/dlp-learn-about-dlp) |
| Compliance violations | Using [Purview Data Security Posture Management for AI](/purview/dspm-for-ai?tabs=m365): <br/>- Monitor AI interactions<br/>- Log prompts and outputs<br/>-Enforce governance |
| Prompt injection and model abuse | Apply Zero Trust principles |
| Shadow AI and blind spots | Using Defender for Cloud Apps and [Purview DSPM for AI](/purview/dspm-for-ai?tabs=m365): <br/>- Continuous discovery<br/>- Block risky apps |
| Untracked AI agent identities | Using Microsoft Entra ID Governance, set up  Multifactor authentication (MFA) and Just-in-Time (JIT) access |
| Incident response gaps | Using Defender XDR and Defender for Cloud Apps: <br/>- Real-time alerts<br/>- Anomaly detection |

## See also

- [Tech Community blog: Discover, monitor and protect the use of Generative AI apps](https://techcommunity.microsoft.com/blog/microsoftthreatprotectionblog/discover-monitor-and-protect-the-use-of-generative-ai-apps/3999228)

