---
title: "Configure release options for Microsoft 365"
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
description: "Learn how to set up the standard and deferred release options for new features for Microsoft 365 Copilot."
appliesto: 
- Microsoft 365 Copilot
- Microsoft 365 admin center
---

# Configure release options for Microsoft 365 features

> [!IMPORTANT]
> The Microsoft 365 updates described in this article apply to new Outlook, OneDrive, SharePoint in Microsoft 365, Microsoft 365 for the web, Microsoft 365 admin center, some components of Exchange Online and Microsoft Teams. These release options are targeted, best effort ways to release changes to Microsoft 365 but can't be guaranteed at all times or for all updates. They don't currently apply to services other than those listed previously. For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).

Microsoft 365 provides multiple release options that let you control when new features are made available to your organization. These options help you balance early access, testing, and validation with production readiness and organizational risk management.

The available release options include Standard, Deferred, Targeted, and Frontier. Each option serves a different purpose, ranging from early evaluation and feedback to general availability to a delayed rollout for additional review.

This article explains how each release option works, how they differ, and when to use them, so you can choose the approach that best fits your organization’s testing, compliance, and adoption requirements.

## How release validation works

Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft. After internal testing and validation, the next step is a Targeted release (formerly known as First release) to customers who opt-in. At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics. This series of progressive validation is in place to make sure the worldwide release is as robust as possible. The releases are pictured in the following figure.

For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap). As an update gets closer to rolling out, it's communicated through your <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Microsoft 365 Message center</a>.

> [!NOTE]
> You need a Microsoft 365 or Microsoft Entra account to access your Message center through the [Microsoft admin center](../admin-overview/admin-center-overview.md). Microsoft 365 home plan users don't have an admin center.

## Prerequisites

You must have one of the following roles in Microsoft 365 admin center to configure standard, deferred, and targeted release options:

- Office Apps Admin
- Security Admin
- AI Admin
- Global Admin

In order to get early access to the latest AI innovations in Microsoft 365, you can join the Frontier program. You must have a Microsoft 365 Copilot license to use Microsoft Agent 365 and other AI features in Microsoft 365 that are part of the Frontier program. For more information about the Frontier program, see [Frontier: Try what's next in AI](https://adoption.microsoft.com/copilot/frontier-program/).

> [!IMPORTANT]
> Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.
>For more information about administrator roles, see [About administrator roles in the Microsoft 365 admin center](../add-users/about-admin-roles.md).

## Compare release options for Microsoft 365 services



## Configure release options for in Microsoft 365 admin center

Standard release is the default release option. To better manage your organization’s readiness and testing needs, you can change the default release selection at any time in the Microsoft 365 admin center using the following steps. It can take up to 24 hours for the following changes to take effect in Microsoft 365.

You can control two separate release settings in the Microsoft 365 admin center.

### Targeted release

> [!IMPORTANT]
> Large or complex updates might take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release. Targeted release is available for customers with either the Office 365 GCC plan or the Office 365 GCC High plan and DoD plan for the following services: new Outlook, OneDrive, SharePoint in Microsoft 365, Microsoft 365 for web, Microsoft 365 admin center, and some components of Exchange Online.

If you want to use targeted release, we recommend that you only assign a small group of users to Targeted release to test and validate instead of whole tenants.

1. In the Microsoft 365 admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.
    - To opt out of targeted release, select **Standard release**, then select **Save changes**.
    - To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.
1. To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save**.
1. Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.
1. When you're done adding users, select **Save**.

### Deferred release

>[!NOTE]
> Currently, the Deferred release option only supports Microsoft 365 Copilot-related features. For information on which features are Deferred-capable, check Message Center posts. This documentation will be updated as more features are supported.

1. Sign in to the Microsoft 365 admin center.
1. In the left navigation, expand Copilot and select Settings.
1. Under the All Settings tab, select Copilot release preferences: General Availability.
1. Choose either Standard release or Deferred release.
1. Add any user exceptions.
    - If you select **Standard release** and want a specific user to assign to deferred release, search for the user and select their name.
    - If you select **Deferred release** and want a specific user to assign to standard release, search for the user and select their name.
1. Select **Save**.

### Frontier program

For more information about the Frontier program, see [Frontier: Try what's next in AI](https://adoption.microsoft.com/copilot/frontier-program/).

For more information about deploying Microsoft 365 Insider program for Business, see [Microsoft 365 Insider program for Business](https://docs.microsoft.com/microsoft-365/insider/deploy/options).






As an IT admin, you can now choose to either adopt new, generally available Microsoft 365 Copilot features immediately, or you can choose to delay the rollout of Copilot features to your organization by 30 days after general availability.

This article is only about the general availability release options for Copilot features. For information about  release options that apply to new Outlook, OneDrive, SharePoint in Microsoft 365, Microsoft 365 for the web, Microsoft 365 admin center, and some components of Exchange Online and Microsoft Teams, see [Set up the Standard or Targeted release options for Microsoft 365](release-options-in-office-365.md). For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).

## Release option best practices




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

[Prepare for Microsoft 365 updates with Message center](message-center.md)
