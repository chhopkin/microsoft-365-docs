---
title: "Frequently asked questions about release options for Microsoft 365"
f1.keywords:
- CSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 03/13/2026
ms.reviewer: pamelaar, gsaini
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
search.appverid: MET150
description: "Find answers to frequently asked questions about release options for Microsoft 365."
appliesto: 
- Microsoft 365 Copilot
- Microsoft 365 admin center
---

# Frequently asked questions about release options for Microsoft 365

This article provides answers to frequently asked questions that IT admins might have about release options in Microsoft 365. For more information about release options in Microsoft 365, see [Manage continuous change in Microsoft 365](plan-for-change-management.md) and [Configure release options](configure-release-options.md).

## What is a release audience and how does it affect my organization?

You can segment audiences in your tenant into Standard release and Deferred release channels based on regulatory status and readiness. The Standard release audience receives Microsoft 365 features as soon as they become generally available. For features that are deferred-capable, Deferred release channels get a 30-day buffer for compliance validation.

## What's the default release option?

By default, all tenants are automatically assigned to Standard release. As an IT admin, you can opt-in to Deferred release.

## Can I change my release channel assignment?

Yes, your organization can opt in and out of your release channel at any time via the Microsoft 365 admin center. If you switch from deferred release back to standard release, your users might lose access to features that haven't reached standard release yet.

## Can I assign specific users to Deferred release and others to Standard release for testing?

Yes. If you are in a regulated industry, a good practice is to leave most users in Deferred release and IT Pros and power users in Standard release to evaluate new features for privacy and compliance and to prepare teams to support your users.

## Why would my organization want to use Deferred release?

By using the Deferred release option, you can help your organization ensure legal and regulatory readiness, reduce risk by allowing time for internal review and testing, and support structured change management for sensitive environments.

## Why would my organization want to use Targeted release?

Targeted release offers early access to new features before general availability, whereas Standard release offers access to new Microsoft 365 Copilot features as soon as they become generally available. For more information on how to configure Targeted Release for your organization, see [Configure release options](configure-release-options.md).

## How does Deferred release affect Frontier features?

Deferred release doesn’t affect Frontier features, as Frontier agents and Frontier apps are managed in a separate manner. To learn about how to manage Frontier agents, see Manage Microsoft 365 Copilot Agents.

## Where can I find guidance on these new features and updates?

Check for updates to this document as well as Tech Community blog posts and Message Center posts for more information about the modern change communications coming to Microsoft 365.

## Do Standard release and Deferred release options affect Microsoft 365 App release options?

No. For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).

## Related articles

[Configure release options for Microsoft 365](configure-release-options.md)

[Manage continuous change in Microsoft 365](plan-for-change-management.md)

[Message center in the Microsoft 365 admin center](message-center.md)
