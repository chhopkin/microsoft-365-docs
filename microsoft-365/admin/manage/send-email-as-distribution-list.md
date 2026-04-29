---
title: Send Email as a Distribution List in Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
ms.date: 04/29/2026
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
 - Tier3
 - scotvorg
 - Adm_O365
 - operations-pod
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
description: Send email as a distribution list in Microsoft 365 so replies appear to come from the group, not individual members. Learn the steps in Outlook and Outlook on the web.
#customer intent: As a distribution list member, I want to send email as the distribution list so that replies appear to come from the group instead of my personal address.
---

# Send Microsoft 365 email as a distribution list

In Microsoft 365, you can send email as a distribution list. When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.

## Before you begin

Before you perform the steps in this article, make sure the following prerequisites are met:

- You're added to a Microsoft 365 distribution list and you're granted **Send as** permission on it.

- An administrator follows the steps in the following articles:

  - [Add a user or contact to a Microsoft 365 distribution group](../email/add-user-or-contact-to-distribution-list.md).
  - [Allow members to send email as a group](/previous-versions/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group#allow-members-to-send-email-as-a-group).

- The correct people are added to the distribution list.

## Outlook on the web

1. Open Outlook on the web and go to your inbox.

1. Open a message that was sent to the distribution list.

1. Select **Reply**.

1. At the bottom of the message, select **More** > **Show from**.

   :::image type="content" source="../../media/outlook-web-show-from-distribution-list.png" alt-text="Screenshot of selecting More and then choosing Show From." lightbox="../../media/outlook-web-show-from-distribution-list.png":::

1. Right-click on the **From** address, such as `john@contoso.com`, and select **Remove**.

   :::image type="content" source="../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png" alt-text="Screenshot of removing the personal address from the From field." lightbox="../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png":::

1. In the **From** field, enter the distribution list address, such as `support@contoso.com`, and then send the message. The next time you reply from the distribution list, its address appears as an option in the **From** list.

   :::image type="content" source="../../media/outlook-web-from-list-distribution-list-address.png" alt-text="Screenshot of the alias of the shared mailbox appearing." lightbox="../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png":::

## Outlook

1. Open Outlook desktop client.

1. Select **New Email**.

1. Select the **From** field and then select **Other email address**.

    If you don't see the **From** field, go to **Options** and then select **From** in the **Show fields** section.

1. Select the **Distribution List** address.

1. Send the email.
