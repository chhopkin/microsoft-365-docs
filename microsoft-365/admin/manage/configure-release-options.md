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

This article explains how release options work and how to configure them, so you can choose the approach that best fits your organization’s testing, compliance, and adoption requirements.

For a comparison of the release options available for Microsoft 365 features, see [Plan for change management in Microsoft 365](plan-for-change-management.md).

> [!NOTE]
> Deferred release channels aren’t available for GCC, GCC High, and DoD cloud environments. Check this article for updates regarding future support.

## How release validation works

Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft. After internal testing and validation, the next step is a Targeted release (formerly known as First release) to customers who opt-in. At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics. This series of progressive validation is in place to make sure the worldwide release is as robust as possible.

The releases are pictured in the following figure.

:::image type="content" source="../../media/release-validation-timeline.png" alt-text="Release validation rings for Microsoft 365":::

For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap). As an update gets closer to rolling out, it's communicated through your <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Microsoft 365 Message center</a>.

> [!NOTE]
> You need a Microsoft 365 or Microsoft Entra account to access your Message center through the [Microsoft admin center](../admin-overview/admin-center-overview.md). Microsoft 365 home plan users don't have an admin center.

## Prerequisites

You must have one of the following roles in Microsoft 365 admin center to configure standard, deferred, and targeted release options:

- Office Apps Admin
- Security Admin
- AI Admin
- Global Admin **(need confirmation that this is still required for TARGETED release and that a lesser role is not possible)**

In order to get early access to the latest AI innovations in Microsoft 365, you can join the Frontier program. You must have a Microsoft 365 Copilot license to use Microsoft Agent 365 and other AI features in Microsoft 365 that are part of the Frontier program. For more information about the Frontier program, see [Frontier: Try what's next in AI](https://adoption.microsoft.com/copilot/frontier-program/).

> [!IMPORTANT]
> Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.
>For more information about administrator roles, see [About administrator roles in the Microsoft 365 admin center](../add-users/about-admin-roles.md).

## Configure release options for in Microsoft 365 admin center

Standard release is the default release option. To better manage your organization’s readiness and testing needs, you can change the default release selection at any time in the Microsoft 365 admin center. It can take up to 24 hours for the following changes to take effect in Microsoft 365.

You can control three separate release settings in the Microsoft 365 admin center.

### Targeted release

> [!IMPORTANT]
> Large or complex updates might take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release. Targeted release is available for GCC, GCC High, and DoD cloud environments for the following services: new Outlook, OneDrive, SharePoint in Microsoft 365, Microsoft 365 for web, Microsoft 365 admin center, and some components of Exchange Online.

If you want to use targeted release, we recommend that you only assign a small group of users to Targeted release to test and validate instead of whole tenants.

1. In the Microsoft 365 admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.
    - To opt out of targeted release, select **Standard release**, then select **Save changes**.
    - To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.
1. To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save**.
1. Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.
1. When you're done adding users, select **Save**.

### Deferred release

>[!NOTE]
> Currently, Deferred release option only supports Microsoft 365 Copilot-related features. For information on which features are Deferred-capable, check Message Center posts. This documentation will be updated as more features are supported.

1. Sign in to the Microsoft 365 admin center.
1. In the left navigation, expand **Copilot** and select **Settings**.

    :::image type="content" source="../../media/copilot-settings-admin-center.png" alt-text="Screenshot of Copilot settings in Microsoft 365 admin center":::

1. Under the **All Settings** tab, select **Copilot release preferences: General Availability**.
1. Choose either **Standard release for everyone** or **Deferred release for everyone**.

    :::image type="content" source="../../media/release-preferences-general-availability.png" alt-text="Screenshot of standard release and deferred release options in Microsoft 365 admin center":::

1. Add any user exceptions.
    - If you want to only assign a specific user to deferred release, select **Standard release for everyone**, search for the user, and select their name.
    - If you want to only assign a specific user to standard release, select **Deferred release for everyone**, search for the user, and select their name.
1. Select **Save**.

If you switch users from deferred release back to standard release, these users may lose access to features that haven't reached standard release yet.

### Frontier program

**ADD MORE HERE**

For more information about the Frontier program, see [Frontier: Try what's next in AI](https://adoption.microsoft.com/copilot/frontier-program/).

For more information about deploying Microsoft 365 Insider program for Business, see [Microsoft 365 Insider program for Business](microsoft-365/insider/deploy/options).

## Release option best practices

We recommend that you use the release options in the following ways to balance early access with risk management:

- Only assign specific users in targeted release.
- If you need to test a feature in targeted release with a larger group of users (or a tenant), consider using a test tenant instead of putting your entire organization in targeted release.
- Use deferred release for features that are deferred-capable when you need extra time to do security reviews and compliance checks before releasing to your organization.
- Plan release phases around user impact and readiness, not individual feature controls, to help manage risk and set clear expectations for users.
- Align your release configuration with your change management and support readiness, including documentation, training, and help desk preparation.
- Review and adjust audience assignments over time as your organization’s readiness and change tolerance evolve.

## Related articles

[Plan for change management in Microsoft 365](plan-for-change-management.md)

[Set up the Standard or Targeted release options for Microsoft 365](release-options-in-office-365.md)

[Prepare for Microsoft 365 updates with Message center](message-center.md)
