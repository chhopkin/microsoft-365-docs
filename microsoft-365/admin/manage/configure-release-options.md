---
title: "Configure Standard or Deferred release options for Microsoft 365 Copilot"
f1.keywords:
- CSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 02/12/2026
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
description: "Learn how to set up the standard and deferred release options for new features for Microsoft 365 Copilot."
appliesto: 
- Microsoft 365 Copilot
- Microsoft 365 admin center
---

# Configure Standard or Deferred release options for Microsoft 365 Copilot features

As an IT admin, you can now choose to either adopt new, generally available Microsoft 365 Copilot features immediately, or you can choose to delay the rollout of Copilot features to your organization by 30 days after general availability.

This article is only about the general availability release options for Copilot features. For information about  release options that apply to new Outlook, OneDrive, SharePoint in Microsoft 365, Microsoft 365 for the web, Microsoft 365 admin center, and some components of Exchange Online and Microsoft Teams, see [Set up the Standard or Targeted release options for Microsoft 365](release-options-in-office-365.md). For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).

## Prerequisites

You must be a global admin in Microsoft 365 to opt in.

[!INCLUDE [global-administrator-note](../../includes/global-administrator-note.md)]

## Standard vs Deferred release options

> [!NOTE]
> Standard and deferred release channels aren’t available for GCC, GCC High, and DoD cloud environments.

**Standard release** is the default option where you and your users receive the latest Copilot feature updates when they're released broadly to all customers.

With **Deferred release**, you can delay the rollout of Copilot features to validate and prepare for a new feature's use in your organization. You can choose to have individuals or your entire organization receive Copilot updates 30 days after they are generally available. For heavily regulated organizations, such as financial institutions, a good practice is to assign most users to Deferred release and then assign IT Pros and power users in Standard release so that they can evaluate new features and prepare teams to support your users.

## Configure Standard or Deferred release options

Standard release is the default release option. To better manage your organization’s readiness and testing needs, you can change the default release selection at any time in the Microsoft admin center using the following steps. It can take up to 24 hours for the following changes to take effect in Microsoft 365.

1. Sign in to the Microsoft 365 admin center.
1. In the left navigation, expand **Copilot** and select **Settings**.
1. Under the **All Settings**  tab, select **Copilot release preferences: General Availability**.
1. Choose either **Standard release** or **Deferred release**.
1. Add any user exceptions.
    - If you select **Standard release** and want a specific user to assign to **Deferred release**, search for the user and select their name.
    - If you select **Deferred release** and want a specific user to assign to **Standard release**, search for the user and select their name.
1. Select **Save**.

If you switch from deferred release back to standard release, your users may lose access to features that haven't reached standard release yet.

## Related articles

[Plan for modern change management in Microsoft 365](plan-for-modern-change-management.md)

[Set up the Standard or Targeted release options for Microsoft 365](release-options-in-office-365.md)
