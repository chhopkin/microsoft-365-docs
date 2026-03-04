---
title: Configure data security for Microsoft 365 Copilot
description: Get your data ready for Microsoft 365 Copilot.
f1.keywords:
- NOCSH
manager: dansimp
ms.author: deniseb
author: denisebmsft
ms.date: 03/04/2026
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

> Applies to: Microsoft 365 Copilot, SharePoint Advanced Management (SAM), and Microsoft Purview

Microsoft 365 Copilot responds to user prompts using data that the user already has permission to access. If your tenant contains overshared, outdated, or poorly governed content, Copilot responses can be inaccurate or expose information more broadly than intended. This article explains how to prepare and secure your data so Copilot can deliver accurate, relevant, and secure results.

This guidance is intended for IT administrators and security administrators who are preparing their organization for Microsoft 365 Copilot or tightening controls after Copilot is enabled.

## What this article helps you achieve

By completing the steps in this article, you can:

- Reduce oversharing and stale content that can negatively affect Copilot responses.
- Ensure sensitive data is correctly classified and protected.
- Control how SharePoint and OneDrive content is discovered by Copilot.
- Monitor changes and Copilot activity to identify and remediate risk.

## Before you begin

Microsoft recommends that you also review and follow **Microsoft 365 Copilot – best practices with SharePoint**, which covers optimizing SharePoint search, reviewing sharing settings, and validating site permissions.

### Licensing

The capabilities described in this article require:

- **Microsoft 365 Copilot**
- **SharePoint Advanced Management (SAM)** (included with Copilot licenses)
- **Microsoft Purview**

Some advanced controls (such as Endpoint DLP, Adaptive Protection, and insider risk integration) require Microsoft 365 E5 or equivalent add-ons. Where relevant, these differences are called out.

### Admin roles

You'll need access to the following admin portals and roles:

- **SharePoint admin center** (SharePoint Administrator)
- **Microsoft Purview portal** (roles vary by feature, such as Information Protection Admin, Compliance Admin, or eDiscovery Admin)

## Step 1: Reduce oversharing and stale content with SharePoint Advanced Management

SharePoint Advanced Management (SAM) provides tenant-wide controls to identify oversharing, reduce clutter, and monitor changes that can affect Copilot results.

### Ensure all sites have valid owners

Sites without active owners often become overshared or outdated.

- Use a **Site ownership policy** to identify sites that don't have at least two owners.
- Run the policy in **simulation mode** first, then switch to **active mode** to notify potential owners.

Having accountable site owners ensures permissions, access reviews, and lifecycle actions are completed.

### Find and clean up inactive sites

Inactive SharePoint sites can still surface content in Copilot responses.

- Create a **site lifecycle management policy** to detect inactive sites.
- Notify site owners and require them to confirm whether the site is still needed.
- If a site is no longer required:
  - Put it in **read-only mode**, or
  - Move it to **Microsoft 365 Archive**.

Archived sites aren't accessible to users and aren't used by Copilot, which improves response accuracy.

### Identify overshared or sensitive sites

Use **Data access governance (DAG) reports** in the SharePoint admin center to find risk areas:

- Sharing links (Anyone, organization-wide, or external)
- Sites shared with **Everyone except external users (EEEU)**
- Sites containing files with sensitivity labels
- Oversharing baseline reports across sites, OneDrives, and files

Review these reports regularly, especially during early Copilot adoption.

### Control access to high-risk SharePoint sites

When oversharing is identified, you can limit exposure without immediately restructuring permissions:

- **Site access reviews** – Ask site owners to validate members and sharing links.
- **Restricted Access Control (RAC)** – Restrict site access to a specific security group.
- **Restricted Content Discoverability (RCD)** – Prevent site content from appearing in Copilot and organization-wide search results without changing permissions.

> [!TIP]
> Communicate clearly with site owners and users before applying RAC or RCD to avoid unexpected disruptions.

### Monitor changes that affect Copilot

Use the **Change history** reports to track:

- Site-level changes (sharing, access, and settings)
- Organization-level changes (external sharing, site creation settings)

Review these reports regularly to catch changes that could introduce oversharing or expose sensitive data.

### (Optional) Restrict SharePoint search during remediation

If your organization needs time to review permissions at scale:

- Enable **Restricted SharePoint Search (RSS)**.
- Add only reviewed and approved sites to the allowed list.

RSS is a temporary control. Your long-term goal should be to correct permissions and disable RSS so Copilot can access a complete, accurate data set.

## Step 2: Classify and protect data with Microsoft Purview

Microsoft Purview helps ensure Copilot only surfaces data that's appropriately classified and protected.

### Create and apply sensitivity labels

Sensitivity labels classify data and enforce protection such as encryption, access restrictions, and visual markings.

- Create sensitivity labels for files, emails, and other data assets.
- Enable sensitivity labels for **SharePoint and OneDrive**, which is required for Copilot to access encrypted files.
- (Optional) Enable labels for **groups and sites** to control access at the container level.

When Copilot uses labeled content:

- It respects encryption and usage rights.
- Returned responses display the highest-priority label.
- New content generated by Copilot inherits the source label.

### Apply default and automatic labeling

To reduce reliance on manual user action:

- Configure **default sensitivity labels** for SharePoint document libraries.
- Use **automatic labeling** to detect sensitive information and apply stricter labels at scale.

Automatic labeling improves consistency and reduces the risk of sensitive content appearing in Copilot responses.

### Prevent data leakage with Data Loss Prevention (DLP)

Use **Microsoft Purview DLP** to prevent unintentional or risky sharing:

- Protect data across Exchange, SharePoint, OneDrive, Teams, and endpoints.
