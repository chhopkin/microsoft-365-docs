---
title: Configure data security for Microsoft 365 Copilot
description: Get your data ready for Microsoft 365 Copilot.
f1.keywords:
- NOCSH
manager: dansimp
ms.author: deniseb
author: denisebmsft
ms.date: 03/06/2026
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

# Configure a Secure and Governed Data Foundation for Microsoft 365 Copilot

> Applies to: Microsoft 365 Copilot, Microsoft Purview, and SharePoint Advanced Management

[Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-overview) (Copilot) responds to user prompts using data that the user already has permission to access. When your organization's data is well governed, current, and appropriately shared, Copilot can deliver accurate, relevant, and secure responses. This article explains how to prepare, secure, and govern your data, so Copilot can provide high quality results while respecting your organization's security and compliance requirements.

This guidance is intended for IT administrators and security administrators who are preparing their organization for Microsoft 365 Copilot or tightening controls after Copilot is enabled.

## What this article helps you achieve

By completing the steps in this article, you can:

- Reduce oversharing and stale content that can negatively affect Copilot responses.
- Ensure sensitive data is correctly classified and protected.
- Control how SharePoint and OneDrive content is discovered by Copilot.
- Monitor changes and Copilot activity to identify and remediate risk.

### Licensing

The capabilities described in this article require:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/enterprise/e3) or [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/e5) (or [Office 365 E3](https://www.microsoft.com/microsoft-365/enterprise/office-365-e3) or [Office 365 E5](https://www.microsoft.com/microsoft-365/enterprise/office-365-e5)) for core Microsoft 365 services and features, such as SharePoint, OneDrive, and Microsoft Purview features.

- [Microsoft 365 Copilot](microsoft-365-copilot-licensing.md)
   - Depending on your subscription plan, you might be able to purchase Microsoft 365 Copilot licenses through the [Microsoft 365 admin center Marketplace page](https://go.microsoft.com/fwlink/p/?linkid=868433), Microsoft partners, or your Microsoft account team.
   - Microsoft 365 Copilot licenses are available as an add-on to other licensing plans. To learn more, see [Understand licensing for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-licensing).

- [SharePoint Advanced Management](/sharepoint/advanced-management) (included with Copilot licenses)

- [Microsoft Purview](/purview/) (varies by feature, with foundational capabilities in E3 licenses and optimized features in E5 licenses)

### Admin roles

You need access to the following admin portals and permissions:

| Admin portal | Required role |
|---|---|
| [Microsoft 365 admin center](https://admin.microsoft.com/) | Global Administrator or Privileged Role Administrator |
| [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) | SharePoint Administrator |
| [Microsoft Purview portal](https://purview.microsoft.com/) | Varies by task. See the following articles: <br/>- [Permissions required to create and manage sensitivity labels](/purview/get-started-with-sensitivity-labels#permissions-required-to-create-and-manage-sensitivity-labels)<br/>- [Roles and role groups in Microsoft Defender for Office 365 and Microsoft Purview](/defender-office-365/scc-permissions) |
   
## Step 1: Remediate oversharing

First, identify and contain high-risk sites and sensitive content, remediate access and permissions, and apply interim protections to reduce Copilot exposure while remediation is in progress.

### Identify high-risk sites and content

Use [SharePoint Advanced Management](/sharepoint/get-ready-copilot-sharepoint-advanced-management) (SAM) and [Microsoft Purview](/purview/purview) to find sites and files that are overshared, ownerless, inactive, or contain sensitive data that could be surfaced by Copilot.

- Run the __[SAM Content Management Assessment](/sharepoint/content-management-assessment)__ to identify sites with oversized audiences, Everyone except external users (EEEU) usage, broken inheritance, inappropriate sharing, and sensitive content; and to identify sites that are inactive or ownerless.

- Review __[Purview Data Security Posture Management (DSPM)](/purview/data-security-posture-management-learn-about)__ data risk assessments to identify sites with sensitive data and risky or overshared links accessible to Copilot.

- __Prioritize remediation__ for sites and content that are highly shared or accessed and contain sensitive content and broken inheritance, especially if the site is Public; and for sites that are ownerless or inactive.

### Fix access and permissions

For sites flagged as high-risk, use SAM and Purview recommendations to remove excessive access, correct broken inheritance, and ensure accountable ownership.

1. Initiate [SAM site access reviews](/sharepoint/site-access-review) for high-risk sites so site owners can manage access (down to the file level) and:

- Remove __excess users, groups, and company-wide sharing links__ (including EEEU), and re-scope sharing links to approved users or groups.
   
   - Correct __broken permission inheritance__ on libraries and folders.
   
   - Assign or confirm __site ownership__ for all remediated sites using SAM site lifecycle management.
   
1. Review __[Purview DSPM data risk assessment](/purview/data-security-posture-management-oversharing?tabs=m365)__ recommendations for high-risk sites (for example, apply site sensitivity labels to reflect data sensitivity and restrict oversharing).

### Apply interim Copilot protections

While sites are in remediation, apply temporary controls to reduce exposure and validate that Copilot is no longer surfacing restricted content.

- Enable __[SAM Restricted Content Discovery (RCD)](/sharepoint/restricted-content-discovery)__ to exclude sensitive sites from Copilot discovery.

- Configure __[Purview Data Loss Prevention (DLP) for Copilot](/purview/dlp-microsoft365-copilot-location-learn-about)__ to exclude sensitive content from Copilot grounding.

Validate via audit and reports that __Copilot no longer surfaces restricted content__.

Remove these restrictions once site access and permissions are fully remediated.

## Step 2: Setup guardrails

Next, establish secure defaults and durable guardrails so new sites and content are protected at creation—and continuously enforce and optimize these controls over time.

### Establish secure defaults

Use tenant and provisioning defaults to prevent oversharing from being introduced in new sites and sharing links.

1. Enforce __[Restricted Access Control (RAC) by default](/sharepoint/restricted-access-control)__ for business-critical sites at provisioning time.

1. Disable or restrict use of __company-wide sharing groups__ and __Anyone__ links at the tenant level.

1. __Require site sensitivity labels at provisioning__ to enforce correct site privacy and sharing controls by default.

### Establish secure guardrails

Configure classification and enforcement controls so Copilot interactions and new content are protected by policy, not by manual remediation.

- Configure __default sensitivity labels__ to ensure new content is protected.

- Set up a __[Purview DLP for Copilot](/purview/dlp-microsoft365-copilot-location-learn-about)__ policy to restrict Copilot processing of labeled sensitive content.

- Enable a __[Purview DLP for Copilot prompt](/purview/dlp-microsoft365-copilot-location-learn-about)__ policy to restrict Copilot from responding to prompts that contain sensitive information.

- Enable __[Purview Insider Risk Management (IRM)](/purview/insider-risk-management-solution-overview)__ policies to detect potentially inappropriate or non-compliant AI usage..

### Continuously enforce and optimize guardrails

Use Purview reporting, risk assessments, and alerts to continuously validate protection and investigate risky AI usage.

- Use __[DSPM Activity Explorer](/purview/data-security-posture-management-learn-about)__ to review Copilot interactions (prompts and responses), web search keywords, and sensitive data activity.

- Use __[DSPM data risk assessments](/purview/data-security-posture-management-oversharing?tabs=m365)__ to continuously validate that sensitive data remains protected from Copilot access.

- Review __Purview IRM and DLP alerts__ to detect and investigate risky AI usage or potential data loss.

## Step 3: Meet regulations

Finally, assess and close AI compliance gaps, define audit and retention requirements for Copilot interactions, and improve ongoing data hygiene to support responsible AI governance at scale.

### Identify and address gaps against AI regulations

- Use __[Purview Compliance Manager](/purview/compliance-manager)__ to assess your tenant against AI-related regulatory requirements and Microsoft recommended actions.

- Review __Compliance Manager improvement actions__ related to data protection, auditability, and AI usage controls.

- Assign and track remediation work to close __identified compliance gaps__.

- Validate improvements using __Purview DSPM__ reports.

### Define regulatory requirements

- Decide __[how long to keep audit logs](/purview/audit-log-retention-policies)__ in accordance with regulatory and internal requirements.

- Decide how to keep or when to delete __Copilot interactions__ based on legal risk or regulatory requirements with __[Purview Data Lifecycle Management](/purview/retention-policies-copilot)__.

- Use __[Purview eDiscovery](/purview/edisc-search-copilot-data)__ to search, preserve, and produce Copilot-related content for audits or legal requests.

### Improve data hygiene

Reduce ongoing risk and improve Copilot answer quality by continuously cleaning up inactive content and applying retention and deletion policies.

__For sites:__ 

- Maintain lifecycle hygiene by identifying and addressing inactive or obsolete sites using [SAM inactive site policies](/sharepoint/site-lifecycle-management).

- __For sites:__ Use [Microsoft 365 Archive](/microsoft-365/archive/archive-overview?view=o365-worldwide) to store inactive but high-value content at a lower cost while preventing Copilot from processing or reasoning over it.

__For files:__ 

- Apply [Purview retention and deletion policies](/purview/create-retention-policies?tabs=teams-retention) to reduce data exposure while meeting record-keeping obligations.

## Next steps

After completing the steps in this article:

- Review Copilot usage trends and reports regularly. See [Copilot Control System measurement reporting](/copilot/microsoft-365/copilot-control-system/measurement-reporting)
- Use the [SharePoint admin agent](/sharepoint/content-governance-agent) and the [Purview portal](/purview/purview-portal) to view information and run reports on a scheduled basis.
- Educate site owners and users on labeling, sharing, and responsible Copilot use. See [Microsoft 365 Copilot data and compliance readiness](/copilot/microsoft-365/microsoft-365-copilot-minimum-requirements-data-compliance).

Well-governed data not only reduces risk, it also significantly improves the quality and usefulness of Microsoft 365 Copilot responses.

