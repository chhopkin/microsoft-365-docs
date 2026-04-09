---
title: "Frequently asked questions about release options for Microsoft 365"
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
description: "Find answers to frequently asked questions about release options for Microsoft 365."
appliesto: 
- Microsoft 365 Copilot
- Microsoft 365 admin center
---

# Frequently asked questions about release options for Microsoft 365

This article provides answers to frequently asked questions that IT admins might have about release options in Microsoft 365. For more information about release options in Microsoft 365, see [Manage continuous change in Microsoft 365](plan-for-change-management.md) and [Configure release options](configure-release-options.md).

## What are standard and deferred Release options?

These audience-based release options allow your organization to decide when certain major Microsoft 365 features will become available to your users.

- **Standard release**: Users receive new features as they begin rolling out in General Availability (GA).
- **Deferred release**: Users receive eligible major features 30 days after rollout begins in standard release.

This helps your organization:

- Start testing early with a small group of users
- Prepare communications and training
- Complete readiness or compliance reviews before broader rollout

## Can I choose which users get Microsoft 365 features earlier vs later?

Yes, within the same tenant, you can choose the following:

- Assign most users to standard release and assign a subset of users to deferred release, or
- Assign most users to deferred release and assign a small group of early adopters to standard release

This allows you to:

- Test changes with IT or pilot groups first
- Give business-critical users more time before receiving changes

## Can I defer individual features?

No, you can’t defer individual features. Deferred release applies to eligible major features that Microsoft identifies as "deferred‑capable."

If your tenant is configured for deferred release, all eligible major features follow the deferred timeline automatically.

You can still use existing admin controls (when available) to manage specific features in your tenant.

## When does the 30‑day Deferred period begin?

The 30‑day timer starts when the feature *begins* rolling out in GA to standard release users globally. The deferred period doesn't begin when the standard global rollout completes. Standard users can begin evaluating the feature immediately, but users that are in deferred release receive the feature 30 days later.

## What if feature rollout takes weeks or months to reach all users?

Microsoft rolls out Microsoft 365 features in stages to help ensure quality.

When we rollout a feature for general availability, standard release users receive the feature before deferred release users. Users assigned to standard release can start evaluating the feature as soon as it reaches your standard release users.

Deferred release users receive the deferred-capable feature 30 days after the rollout to standard release begins. This delay gives IT admins and power users more time to test, validate, and prepare before the feature reaches your deferred release users.

## Will tenant-wide features respect standard and deferred user settings?

Most Microsoft 365 features are delivered at the user level and respect your standard and deferred release assignments. However, some features are deployed at the tenant level. Tenant-wide changes might apply to all users at once, regardless of release audience assignment.

## What happens if a feature needs to be rolled back?

If Microsoft finds a quality issue during rollout:

- Microsoft pauses the rollout.
- Users who haven’t received the feature won’t get it.
- If needed, Microsoft may remove the feature from users who already received it.

Deferred release users won't receive a feature that Microsoft rolls back before it reaches them.

## Does deferred release replace admin controls?

No, deferred release provides time to evaluate production-ready (GA) features. It works alongside existing admin controls, feature-level enable/disable settings (when available).
You may still request additional controls through your Microsoft account team if needed.

## How does Message center support Deferred release?

For Deferred release, we've updated the Message center to do the following actions:

- Clearly identify Deferred-eligible features
- Include rollout timing to help you plan for updates
- Send out announcements closer to the start of GA to ensure accuracy

These updates can help reduce shifting timelines, improve readiness planning, and align communications with generally available and fully supported features.

## Can I assign specific users to deferred release and others to standard release for testing?

Yes, if your organization needs more time for testing and evaluation of major features, you can leverage the new release model for deferred-capable features.

## How does Deferred release affect Frontier features?

Deferred release doesn’t affect Frontier program features. Deferred release allows customers to delay delivery of eligible features at general availability. The Frontier release is pre-GA, providing early adopters to try new experiences and give feedback. Features, agents, and capabilities in the Frontier program are managed separately. For more information about the Frontier program, see [Microsoft Frontier Program](https://www.microsoft.com/microsoft-365-copilot/frontier-program).

## Where can I find guidance on these new features and updates?

Check for updates to this document as well as Message Center posts and the Microsoft 365 Roadmap for more information about the modern change communications coming to Microsoft 365.

## Do standard release and deferred release options affect Microsoft 365 App release options?

No. For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).

## Related articles

[Configure modern release options for Microsoft 365](configure-release-options.md)

[Modern change management for Microsoft 365 - Overview](plan-for-change-management.md)

[Message center in the Microsoft 365 admin center](message-center.md)

[Get started with the Microsoft Release Communications MCP Server](mrc-mcp.md)
