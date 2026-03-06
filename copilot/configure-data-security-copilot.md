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

# Configure data security for Microsoft 365 Copilot

> Applies to: Microsoft 365 Copilot, SharePoint Advanced Management, and Microsoft Purview

[Microsoft 365 Copilot](microsoft-365-copilot-overview.md) responds to user prompts using data that the user already has permission to access. When your organization's data is well governed, current, and appropriately shared, Copilot can deliver accurate, relevant, and secure responses. This article explains how to prepare and secure your data so Copilot can provide high‑quality results while respecting your organization's security and compliance requirements.

This guidance is intended for IT administrators and security administrators who are preparing their organization for Microsoft 365 Copilot or tightening controls after Copilot is enabled.

## What this article helps you achieve

By completing the steps in this article, you can:

- Reduce oversharing and stale content that can negatively affect Copilot responses.
- Ensure sensitive data is correctly classified and protected.
- Control how SharePoint and OneDrive content is discovered by Copilot.
- Monitor changes and Copilot activity to identify and remediate risk.

## Before you begin

Microsoft recommends that you also review and follow [Microsoft 365 Copilot – best practices with SharePoint](/sharepoint/sharepoint-copilot-best-practices), which covers optimizing SharePoint search, reviewing sharing settings, and validating site permissions.

### Licensing

The capabilities described in this article require:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/enterprise/e3) or [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/e5) (or [Office 365 E3](https://www.microsoft.com/microsoft-365/enterprise/office-365-e3) or [Office 365 E5](https://www.microsoft.com/microsoft-365/enterprise/office-365-e5)) for core Microsoft 365 services and features, such as SharePoint, OneDrive, and basic Microsoft Purview features.

- [Microsoft 365 Copilot](microsoft-365-copilot-licensing.md)
   - Depending on your subscription plan, you might be able to purchase Microsoft 365 Copilot licenses through the [Microsoft 365 admin center Marketplace page](https://go.microsoft.com/fwlink/p/?linkid=868433), Microsoft partners, or your Microsoft account team.
   - Microsoft 365 Copilot licenses are available as an add-on to other licensing plans. To learn more, see [Understand licensing for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-licensing).

- [SharePoint Advanced Management](/sharepoint/advanced-management) (included with Copilot licenses)

- [Microsoft Purview](/purview/) (varies by feature, but many capabilities are included with Microsoft 365 E3 or E5)

### Admin roles

You need access to the following admin portals and permissions:

| Admin portal | Required role |
|---|---|
| [Microsoft 365 admin center](https://admin.microsoft.com/) | Global Administrator or Privileged Role Administrator |
| [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) | SharePoint Administrator |
| [Microsoft Purview portal](https://purview.microsoft.com/) | Varies by task. See the following articles: <br/>- [Permissions required to create and manage sensitivity labels](/purview/get-started-with-sensitivity-labels#permissions-required-to-create-and-manage-sensitivity-labels)<br/>- [Roles and role groups in Microsoft Defender for Office 365 and Microsoft Purview](/defender-office-365/scc-permissions) |
   
## Step 1: Reduce oversharing and stale content with SharePoint Advanced Management

[SharePoint Advanced Management](/sharepoint/get-ready-copilot-sharepoint-advanced-management) provides tenant-wide controls to identify oversharing, reduce clutter, and monitor changes that can affect Copilot results.

### Ensure all sites have valid owners

Sites without active owners often become overshared or outdated.

- Use a [Site ownership policy](/sharepoint/create-sharepoint-site-ownership-policy) to identify sites that don't have at least two owners.
- Run the policy in simulation mode first, and then switch to active mode to notify potential owners.

Having accountable site owners ensures permissions, access reviews, and lifecycle actions are completed.

### Find and clean up inactive sites

Inactive SharePoint sites can still surface content in Copilot responses.

1. Create a [site lifecycle management policy](/sharepoint/site-lifecycle-management#how-to-create-an-inactive-site-policy) to detect inactive sites and generate reports.

2. Notify site owners and ask them to confirm whether the site is still needed.

3. If a site is no longer required, take one of the following steps:

   - Put it in **read-only mode** (see [Lock and unlock sites](/sharepoint/manage-lock-status))
   - Move it to [Microsoft 365 Archive](/microsoft-365/archive/archive-overview)

Archived sites aren't accessible to users and aren't used by Copilot, which improves response accuracy.

### Identify overshared or sensitive sites

Use [Data access governance (DAG) reports](/sharepoint/data-access-governance-reports) in the SharePoint admin center to find risk areas. Here are some examples:

- [How sharing links are configured](/sharepoint/data-access-governance-sharing-links-report) (Anyone, organization-wide, or external)
- [Sites shared with everyone except external users (EEEU)](/sharepoint/data-access-governance-everyone-except-external-user-report)
- [Sites containing files with sensitivity labels](/sharepoint/data-access-governance-sensitivity-label-report)
- Oversharing across sites, OneDrive libraries, and files (see [Snapshot and activity reports](/sharepoint/data-access-governance-reports#how-to-use-snapshot-and-activity-reports))

Review these reports regularly, especially during early Copilot adoption.

### Control access to high-risk SharePoint sites

When oversharing is identified, you can limit exposure with SharePoint Advanced Management controls:

1. [Initiate site access reviews](/sharepoint/site-access-review). Ask site owners to validate members and sharing links.

2. [Use Restricted Access Control (RAC)](/sharepoint/restricted-access-control). Grant appropriate access to sites through groups.

3. [Set up Restricted Content Discoverability (RCD)](/sharepoint/restricted-content-discovery). Prevent high-risk site content from appearing in Copilot and organization-wide search results without changing permissions.

> [!TIP]
> Communicate clearly with site owners and users before applying RAC or RCD to avoid unexpected disruptions.

### Monitor changes that affect Copilot

Use the [Change history reports](/sharepoint/change-history-report) to track:

- Site-level changes (sharing, access, and settings)
- Organization-level changes (external sharing, site creation settings)

Review these reports regularly to catch changes that could introduce oversharing or expose sensitive data.

### (Optional) Restrict SharePoint search during remediation

If your organization needs time to review permissions at scale:

- Enable [Restricted SharePoint Search (RSS)](/sharepoint/restricted-sharepoint-search).
- Add only reviewed and approved sites to the allowed list.

**RSS is a temporary control**. Your long-term goal should be to correct permissions and disable RSS so Copilot can access a complete, accurate data set.

## Step 2: Classify and protect data with Microsoft Purview

[Microsoft Purview](/purview/purview) helps ensure Copilot only surfaces data that's appropriately classified and protected.

### Create and apply sensitivity labels

[Sensitivity labels](/purview/sensitivity-labels) classify data and enforce protection such as encryption, access restrictions, and visual markings.

1. [Create and publish sensitivity labels](/purview/create-sensitivity-labels?tabs=classic-label-scheme) for files, emails, and other data assets.

2. [Enable sensitivity labels for files in SharePoint and OneDrive](/purview/sensitivity-labels-sharepoint-onedrive-files), which is required for Copilot to access encrypted files.

3. (Optional) [Enable labels for content in Teams, Microsoft 365 Groups, and SharePoint sites](/purview/sensitivity-labels-teams-groups-sites)  to control access at the container level.

When Copilot uses labeled content:

- It respects encryption and usage rights.
- Returned responses display the highest-priority label.
- New content generated by Copilot inherits the source label.

### Apply default and automatic labeling

To reduce reliance on manual user action:

- Configure [default sensitivity labels](/purview/default-sensitivity-labels-policies) for SharePoint document libraries.
- Use [automatic labeling](/purview/apply-sensitivity-label-automatically?tabs=apply-label) to detect sensitive information and apply stricter labels at scale.

Automatic labeling improves consistency and reduces the risk of sensitive content appearing in Copilot responses.

### Prevent data leakage with Data Loss Prevention (DLP)

Use [Microsoft Purview DLP](/purview/dlp-learn-about-dlp) to prevent unintentional or risky sharing:

1. Protect data across Exchange, SharePoint, OneDrive, Teams, and endpoints. See [Create a DLP policy to protect documents with FCI or other properties](/purview/dlp-protect-documents-that-have-fci-or-other-properties).

2. Block or audit actions such as copying, downloading, or sharing sensitive data. See [Protective actions of DLP policies](/purview/dlp-learn-about-dlp#protective-actions-of-dlp-policies).

3. Prevent Copilot from summarizing or referencing content that violates DLP policies. See [Learn about using Microsoft Purview Data Loss Prevention to protect interactions with Microsoft 365 Copilot and Copilot Chat](/purview/dlp-microsoft365-copilot-location-learn-about).

Advanced capabilities. such as [Endpoint DLP](/purview/endpoint-dlp-learn-about) and [Adaptive Protection](/purview/dlp-adaptive-protection-learn), require Microsoft 365 E5 or equivalent licensing.

### Remove data you no longer need

Stale data increases noise and risk. Use [retention policies and retention labels](/purview/retention?tabs=table-overriden) to comply with industry regulations and internal policies, remove old content you're not required to keep, and helps ensure users are working with content that's current and relevant.

- Use [retention policies](/purview/retention?tabs=table-overriden#retention-policies) to automatically retain or delete content.
- Use [retention labels](/purview/retention?tabs=table-overriden#retention-labels) when exceptions are required for specific documents or emails.

Cleaning up outdated data helps improves the relevance and accuracy of Copilot responses.

## Step 3: Monitor and investigate Copilot activity

Even with strong controls, monitoring Copilot usage is essential. Reports and tools are available to help you monitor Copilot usage and activity. See [Copilot Analytics introduction](/viva/insights/copilot-analytics-introduction).

### Review Copilot prompts and responses

Use Microsoft Purview tools to analyze Copilot interactions:

- [Use Data Security Posture Management (DSPM) for AI](/purview/dspm-for-ai?tabs=m365) to proactively monitor AI usage.
- [Use eDiscovery](/purview/edisc) to search, export, and (if necessary) delete Copilot prompts and responses.

These tools help you:

- Detect sensitive or inappropriate content.
- Investigate potential data spillage.
- Support compliance and legal requirements.

### Monitor communication risks

Use [Communication Compliance](/purview/communication-compliance) policies to detect risky or inappropriate Copilot interactions, such as:

- Sharing confidential information
- Harassment or abusive language
- Policy violations

Predefined templates make it easier to get started quickly. See [Get started with recommended actions](/purview/communication-compliance-configure#recommended-actions).

## Next steps

After completing the steps in this article:

- Review Copilot usage trends and reports regularly.
- Rerun SharePoint and Purview reports on a scheduled basis.
- Educate site owners and users on labeling, sharing, and responsible Copilot use.

Well-governed data not only reduces risk—it significantly improves the quality and usefulness of Microsoft 365 Copilot responses.
