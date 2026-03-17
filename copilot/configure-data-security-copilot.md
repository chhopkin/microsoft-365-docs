---
title: Configure data security for Microsoft 365 Copilot
description: Get your data ready for Microsoft 365 Copilot.
f1.keywords:
- NOCSH
manager: dansimp
ms.author: deniseb
author: denisebmsft
ms.date: 03/17/2026
ms.update-cycle: 180-days
ms.reviewer: cabailey, ruihu
audience: Admin
customer-intent: As an IT admin, I want to prepare my organization with for Microsoft 365 Copilot with Microsoft 365 E3 or E5.
ms.topic: get-started
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
- essentials-overview
- trust-pod
ms.custom: [copilot-learning-hub]
appliesto:
- ✅ Microsoft 365 Copilot
---

# Configure a secure and governed foundation for Microsoft 365 Copilot

> Applies to: Microsoft 365 Copilot, Microsoft Purview, and SharePoint Advanced Management

[Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-overview) uses Work IQ to enhance responses to user prompts using data that the user already has permission to access. When your organization's data is well governed, current, and appropriately shared, Copilot can deliver accurate, relevant, and secure responses. 

This article guides you through preparing, securing, and managing Microsoft 365 Copilot. By following these steps, you can help Copilot deliver accurate and relevant results while supporting your organization's security, compliance, and regulatory requirements.

This guidance is intended for IT administrators and security administrators who are either preparing their organization for Microsoft 365 Copilot or making necessary adjustments to security and governance conrols after Copilot is enabled.

## What this article helps you achieve

By completing the steps in this article, you can:

- Establish guardrails to ensure that users have appropriate access to SharePoint, OneDrive, and Exchange, and that Copilot only references accurate, up-to-date information in line with your organization's policies

- Make informed choices about how Copilot can and cannot interact with your organization's sensitive data, ensuring control and flexibility in data usage and access

- Monitor changes and Copilot activity to identify and remediate risk.

### Licensing

The capabilities described in this article require:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/enterprise/e3) or [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/e5) (or [Office 365 E3](https://www.microsoft.com/microsoft-365/enterprise/office-365-e3) or [Office 365 E5](https://www.microsoft.com/microsoft-365/enterprise/office-365-e5)) for core Microsoft 365 services and features, such as SharePoint, OneDrive, and Microsoft Purview features.

   This article covers both the [Microsoft Purview](/purview/) foundational capabilities that are included in Microsoft 365 E3 and the optimized features that are included in Microsoft 365 E5

- [Microsoft 365 Copilot](microsoft-365-copilot-licensing.md)

- [SharePoint Advanced Management](/sharepoint/advanced-management) (included with Copilot licenses)
    
### Admin roles

You need access to the following admin portals and permissions:

| Admin portal | Required role |
|---|---|
| [Microsoft 365 admin center](https://admin.microsoft.com/) | Global Administrator or Privileged Role Administrator |
| [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) | SharePoint Administrator |
| [Microsoft Purview portal](https://purview.microsoft.com/) | Varies by task. See [Permissions in the Microsoft Purview portal](/purview/purview-permissions) |
   
## Step 1: Remediate oversharing

First, identify and prioritize high-risk sites and sensitive content, remediate access and permissions, and apply interim protections to reduce Copilot exposure while remediation is in progress.

### Identify high-risk sites and content

Use [Microsoft Purview](/purview/purview) and [SharePoint Advanced Management](/sharepoint/get-ready-copilot-sharepoint-advanced-management) (SAM) to find sites and files that are overshared, ownerless, inactive, or contain sensitive data that could be surfaced by Copilot.

1. Review [Purview Data Security Posture Management (DSPM)](/purview/data-security-posture-management-learn-about) data risk assessments to identify sites with sensitive data and risky or overshared links accessible to Copilot.

2. Run the [SAM Content Management Assessment](/sharepoint/content-management-assessment) to identify sites with oversized audiences, Everyone except external users (EEEU) usage, broken inheritance, inappropriate sharing, and sensitive content; and to identify sites that are inactive or ownerless.

### Fix access and permissions

For sites you identify as high-risk, use Microsoft Purview and SAM recommendations to remove excessive access, correct broken inheritance, and ensure accountable ownership.

1. Review [Purview DSPM data risk assessment](/purview/data-security-posture-management-oversharing?tabs=m365) recommendations for high-risk sites (for example, apply site sensitivity labels to reflect data sensitivity and restrict oversharing).

1. Initiate [SAM site access reviews](/sharepoint/site-access-review) for high-risk sites so site owners can manage access (down to the file level) and:

   1. Remove **excess users, groups, and company-wide sharing links** (including EEEU), and re-scope sharing links to approved users or groups.
   
   1. Correct **broken permission inheritance_** on libraries and folders.
   
   1. Assign or confirm **site ownership** for all remediated sites using SAM site lifecycle management.
   
### Apply interim Copilot protections

While sites are in remediation, apply temporary controls to reduce exposure and validate that Copilot is no longer surfacing restricted content.

1. Enable [SAM Restricted Content Discovery (RCD)](/sharepoint/restricted-content-discovery) to exclude sensitive sites from Copilot discovery.

2. Configure [Purview Data Loss Prevention (DLP) for Copilot](/purview/dlp-microsoft365-copilot-location-learn-about) to exclude sensitive content from Copilot grounding.

3. Validate via audit and reports that **Copilot no longer surfaces restricted content**.

4. Remove these restrictions once site access and permissions are fully remediated.

## Step 2: Set up guardrails

Next, establish secure defaults and durable guardrails with Microsoft Purview and SAM so new sites and content are protected at creation, and continuously enforce and optimize these controls over time.

### Establish secure defaults

Use tenant and provisioning defaults to prevent oversharing from being introduced in new sites and sharing links.

1. Enforce [Restricted Access Control (RAC) by default](/sharepoint/restricted-access-control) for business-critical sites at provisioning time.

1. Disable or restrict use of **company-wide sharing groups** and **Anyone** links at the tenant level.

1. **Require site sensitivity labels at provisioning** to enforce correct site privacy and sharing controls by default.

### Establish secure guardrails

Configure classification and enforcement controls with Microsoft Purview so Copilot interactions and new content are protected by policy, not by manual remediation.

1. Configure **default sensitivity labels** to ensure new content is protected.

2. Set up a [Purview DLP for Copilot](/purview/dlp-microsoft365-copilot-location-learn-about) policy to restrict Copilot processing of labeled sensitive content.

3. Enable a [Purview DLP for Copilot prompt](/purview/dlp-microsoft365-copilot-location-learn-about) policy to restrict Copilot from responding to prompts that contain sensitive information.

4. Enable [Purview Insider Risk Management (IRM)](/purview/insider-risk-management-solution-overview) policies to detect potentially inappropriate or non-compliant AI usage.

### Continuously enforce and optimize guardrails

Use Microsoft Purview reporting, risk assessments, and alerts to continuously validate protection and investigate risky AI usage.

1. Use [DSPM Activity Explorer](/purview/data-security-posture-management-learn-about) to review Copilot interactions (prompts and responses), web search keywords, and sensitive data activity.

2. Use [DSPM data risk assessments](/purview/data-security-posture-management-oversharing?tabs=m365) to continuously validate that sensitive data remains protected from Copilot access.

3. Review **Purview IRM and DLP alerts** to detect and investigate risky AI usage or potential data loss.

## Step 3: Meet regulations

Finally, assess and close AI compliance gaps, define audit and retention requirements for Copilot interactions, and improve ongoing data hygiene with Microsoft Purview to support responsible AI governance at scale.

### Identify and address gaps against AI regulations

1. Use [Purview Compliance Manager](/purview/compliance-manager) to assess your tenant against AI-related regulatory requirements and Microsoft recommended actions.

2. Review **Compliance Manager improvement actions** related to data protection, auditability, and AI usage controls.

3. Assign and track remediation work to close **identified compliance gaps**.

4. Validate improvements using **Purview DSPM** reports.

### Define regulatory requirements

1. Decide [how long to keep audit logs](/purview/audit-log-retention-policies) in accordance with regulatory and internal requirements.

2. Decide how to keep or when to delete **Copilot interactions** based on legal risk or regulatory requirements with [Purview Data Lifecycle Management](/purview/retention-policies-copilot).

3. Use [Purview eDiscovery](/purview/edisc-search-copilot-data) to search, preserve, and produce Copilot-related content for audits or legal requests.

### Improve data hygiene

Reduce ongoing risk and improve Copilot answer quality by continuously cleaning up inactive content and applying retention and deletion policies.

**For sites**:

- Maintain lifecycle hygiene by identifying and addressing inactive or obsolete sites using [SAM inactive site policies](/sharepoint/site-lifecycle-management).

- Use [Microsoft 365 Archive](/microsoft-365/archive/archive-overview?view=o365-worldwide&preserve-view=true) to store inactive but high-value content at a lower cost while preventing Copilot from processing or reasoning over it.

**For files**: 

- Apply [Purview retention and deletion policies](/purview/create-retention-policies?tabs=teams-retention) to reduce data exposure while meeting record-keeping obligations.

## Next steps

After completing the steps in this article:

1. Use the [Microsoft Purview portal](/purview/purview-portal) and the [Content Governance Agent](/sharepoint/content-governance-agent) to view information and run reports on a scheduled basis.

2. Educate site owners and users on labeling, sharing, and responsible Copilot use. See [Microsoft 365 Copilot data and compliance readiness](/copilot/microsoft-365/microsoft-365-copilot-minimum-requirements-data-compliance).

