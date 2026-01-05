---
title: "Step 3 - Wipe and block a former employee's mobile device"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 10/28/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
- admindeeplinkEXCHANGE
description: "Use the Exchange admin center to wipe and block a former employee's device so that all organization data is removed and it no longer connects to Microsoft 365."
---

# Step 3 - Wipe and block a former employee's mobile device

If an employee has left your organization and they had a business phone, you can use the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) to wipe and block that device. This action helps ensure that your business data is removed from the device and it can no longer connect to your organization's Microsoft 365 subscription. 

If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices [using Basic Mobility and Security](/microsoft-365/admin/security-and-compliance/m365b-devices-basic-mobility-security-wipe-devices).

> [!NOTE]
> You must have appropriate permissions through a an appropriate role, such as the [Directory Writers role](/entra/identity/role-based-access-control/permissions-reference#directory-writers) to perform the tasks in this article. 

## Wipe mobile device using the Exchange admin center

1. In the [Exchange admin center](https://admin.exchange.microsoft.com/), go to > **Recipients** > **Mailboxes**. (Or, go directly to the [Mailboxes page](https://go.microsoft.com/fwlink/p/?linkid=2183135).)

1. Select the user, and under **Email apps & mobile devices**, select **Manage mobile devices**.

1. On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe company data**![Wipe Device.](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block access**.

1. Select **Save**.

   > [!TIP]
   > Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.

## Related content

[Exchange admin center in Exchange Online](/exchange/exchange-admin-center)
