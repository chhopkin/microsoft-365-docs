---
title: "Configure release options for Microsoft 365"
f1.keywords:
- CSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 04/06/2026
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

Microsoft 365 delivers updates continuously, enabling organizations to adopt new capabilities without large, infrequent upgrades. To help IT admins manage this pace of change, Microsoft 365 introduces a new three-tier release model—**Frontier, Standard, and Deferred**—that balances broad adoption and organizational readiness.

> [!IMPORTANT]
> The Microsoft 365 updates described in this article apply to new Outlook, OneDrive, SharePoint in Microsoft 365, Microsoft 365 for the web, Microsoft 365 admin center, some components of Exchange Online and Microsoft Teams. These release options are targeted, best effort ways to release changes to Microsoft 365 but can't be guaranteed at all times or for all updates. They don't currently apply to services other than those listed previously. For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).

With **Standard release**, your organization receives new features as soon as they’re generally available (GA). Standard release is the default option and should be the primary release channel for most customers. Microsoft thoroughly tests and validates all features and services prior to release. Your organization is configured as standard release by default.

If you have additional validation requirements, your organization may want to consider **Deferred release** for all or some users. Major Microsoft 365 releases are considered “deferred-capable”, meaning admins will get up to 30 days to prepare for the release. After 30 days, generally available Microsoft 365 features appear to your users. You can see which features are deferred-capable in the Message center.

For pre-release, the [Microsoft Frontier program](https://www.microsoft.com/microsoft-365-copilot/frontier-program) provides early access to innovative and emerging AI capabilities in Microsoft 365 before those features reach general availability.

You can use these new release options so you can align feature delivery with your organization’s readiness, governance requirements, and overall change management strategy.

> [!NOTE]
> Deferred release channels aren’t available for GCC, GCC High, and DoD cloud environments. Check this article for updates regarding future support.

## How release validation works

Microsoft feature teams validates each new release first, followed by the Microsoft 365 feature team, and then that feature rolls out to all of Microsoft. At each release phase, Microsoft collects feedback and further validates quality by monitoring key usage metrics before it goes to the public. This series of progressive validations helps make sure the worldwide rollout to general availability (Standard release) is as robust as possible.  

:::image type="content" source="../../media/microsoft365-release-options.png" alt-text="Release audiences for Microsoft 365.":::

<sup>*</sup>Experimental features only
<sup>**</sup>Deferred-enabled features only

For a comparison of release options, see the following table:

| Release audience | Primary purpose | Feature readiness | Key considerations for IT admins |
| ----------------- | ----------------- | ------------------- | ---------------------------------- |
| Frontier program | Early experimentation and feedback | Pre-GA, not fully supported | Features may change or be removed, aren’t guaranteed to reach GA, and don’t include support, stability, or service-level agreement (SLA) commitments equivalent to GA |
| Standard release | Default GA rollout | Fully supported GA features | Features are supported, communicated through Message Center and release notes, and expected to remain available under standard lifecycle policies |
| Deferred release | Delayed GA for additional preparation | Fully supported GA features (delayed) | Same functionality as Standard release, with timing delayed (up to ~30 days) to support governance and compliance readiness |

For significant updates, Microsoft first notifies customers through the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap). As an update approaches rollout, Microsoft notifies you through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Microsoft 365 Message center</a>.

> [!NOTE]
> If your organization is using Targeted release, you can continue to do so. However, we recommend transitioning over to our modern release options, Frontier, Standard, and Deferred. For legacy configuration models for change management, see [Configure Standard and Targeted release](release-options-in-office-365.md).

## Prerequisites

You must have one of the following roles in Microsoft 365 admin center to configure Standard and Deferred release options:

- Office Apps Admin
- Security Admin
- AI Admin

> [!NOTE]
> Standard and deferred release channels aren’t currently available for GCC, GCC High, and DoD cloud environments. Check this article for updates regarding future support.

## Release option best practices

We recommend that you use the release options in the following ways to balance early access with organizational readiness:

- If you only want to configure release audiences to access broadly available and fully supported features, assign most users in deferred release and put IT Pros and power users in standard release to evaluate new features for privacy and compliance and to prepare teams to support users.
- Use deferred release for features that are deferred-capable when you need extra time to do security reviews and compliance checks before releasing to your organization.
- Plan release phases around user impact and readiness, not individual feature controls, to help manage risk and set clear expectations for users.
- Align your release configuration with your change management and support readiness, including documentation, training, and help desk preparation.
- Review and adjust audience assignments over time as your organization’s readiness and change tolerance evolve.
- If your organization is already using Targeted release, you can continue doing so. If your organization isn't using Targeted release, we recommend using this three-tier release model, which includes Frontier, Standard, and Deferred release options. For legacy configuration models for change management, see [Configure Standard and Targeted release](release-options-in-office-365.md).

## Configure release options for in Microsoft 365 admin center

Standard release is the default release option for Microsoft 365 service updates and should be used by the majority of customers. To better manage your organization’s readiness and testing needs, you can change the default release selection at any time in the Microsoft 365 admin center. It can take up to 24 hours for the following changes to take effect in Microsoft 365.

> [!NOTE]
> Currently, Deferred release option only supports Microsoft 365 Copilot-related features. For information on which features are Deferred-capable, check Message Center posts. This documentation will be updated as more features are supported.

To assign users to the Deferred release audience, follow these steps:

1. Sign in to the Microsoft 365 admin center.
1. In the left navigation, expand **Copilot** and select **Settings**.

    :::image type="content" source="../../media/copilot-settings-admin-center.png" alt-text="Screenshot of Copilot settings in Microsoft 365 admin center":::

1. Under the **All Settings** tab, select **Copilot release preferences: General Availability**.
1. Choose either **Standard Release** or **Deferred Release**.

    :::image type="content" source="../../media/microsoft365-release-options-standard.png" alt-text="Screenshot of standard release and deferred release options in Microsoft 365 admin center.":::

1. Add any user exceptions. You can add up to 100 user exceptions to Standard release or Deferred release.
    - If you want to only assign a specific user to deferred release, select **Standard Release**, search for the user, and select their name.
    - If you want to only assign a specific user to standard release, select **Deferred Release**, search for the user, and select their name.
1. Select **Save**.

> [!NOTE]
> If you move users from standard release to deferred release, they might lose access to features that aren't available yet in standard release.

## Related articles

[Modern change management for Microsoft 365 - Overview](plan-for-change-management.md)

[Configure Microsoft Release Communications MCP server](mrc-mcp.md)

[Set up the Standard or Targeted release options for Microsoft 365](release-options-in-office-365.md)

[Prepare for Microsoft 365 updates with Message center](message-center.md)
