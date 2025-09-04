---  
title: "Block Microsoft Publisher"  
description: Use the Microsoft 365 admin center, Office Group policies or registry keys to block Microsoft Publisher.
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/25/2025  
ms.topic: how-to
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
ms.reviewer: kwekua
audience: admin
ROBOTS: NOINDEX, NOFOLLOW
---

# Block Microsoft Publisher

Publisher has a large attack surface and will no longer be included in Microsoft 365 starting in October 2026. Blocking Publisher now reduces security risk and aligns with Microsoft’s support strategy.

When you enable this setting, Microsoft Publisher will not launch. When users try to launch Publisher, they will get an error message “Publisher could not start because of a security policy set by your organization”.

If you have enabled this setting but need to revert to the default behavior, you can turn this setting off directly in the Microsoft 365 admin center.

## Turn off setting in the Microsoft 365 admin center

1. Go to the admin center and select Org settings.
1. Select Baseline Security Mode, find the **Block Microsoft Publisher** setting, and switch the toggle to **Off**.

## Office Cloud Policy service

Alternatively, you can make changes to the policy setting directly using the [Office Cloud Policy service](https://config.office.com/). Set the **Disable Publisher** policy as not configured to revert to the default behavior.
