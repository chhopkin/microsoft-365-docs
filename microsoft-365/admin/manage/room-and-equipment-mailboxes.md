---
title: Room and equipment mailboxes
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
ms.date: 04/02/2026
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
 - Tier2
 - scotvorg
 - M365-subscription-management
 - Adm_O365
 - must-keep
 - operations-pod
ms.custom:
- Lean
- MSStore_Link
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
ms.assetid: 9f518a6d-1e2c-4d44-93f3-e19013a1552b
description: Create a room or equipment mailbox so that everyone in your organization can reserve it for meetings or events using Outlook.
#customer intent: As an admin, I want to create a room or equipment mailbox so that my organization can reserve shared resources for meetings or events.
---

# Create Microsoft 365 room and equipment mailboxes

If you have a conference room, company car, or equipment that everyone needs to use, you need a way to make those resources reservable to everyone. The best way to do that is to create a room or equipment mailbox in Microsoft 365 for each resource. You might create one for your first floor conference room, media equipment, or a moving truck.

Once you create a room or equipment mailbox, everyone in the company can reserve it for meetings or events using Outlook. Learn **how to use it** and **how to set it up** on the next two tabs. Here are some other common questions about room and equipment mailboxes.

## Use room and equipment mailboxes

To use room or equipment mailboxes, follow these steps to reserve the resource for a meeting or event:

1. Open **Outlook** or **Outlook on the web** on your computer.

1. On the **Home** tab, choose **New items**, and then select **Meeting** from the drop-down list.

   :::image type="content" source="../../media/ffd575a8-1036-4d67-b839-73941fc60276.png" alt-text="Screenshot of scheduling a meeting in Outlook by selecting New Items and then Meeting on the Home tab.":::

   Or, from your Calendar, just select **New Meeting**.

1. In the **Required** field, type the name of the conference room or equipment you want to reserve, in addition to any attendees you'd like to invite.

   Or, select **Required**, then double-click the conference room or equipment from the list. Then select **OK**.

   :::image type="content" source="../../media/4588c806-9fb9-46c9-b2d8-34caa943e28e.png" alt-text="Screenshot of reserving a room mailbox in Outlook.":::

1. In the **Title** line, type the purpose of the reservation or meeting.

1. Change the **Location** value or leave as is.

1. Change the **Start time** and **End time**. Or, select **All day**. To make the meeting or reservation repeat, select **Recurrence** at the top.

   :::image type="content" source="../../media/4b72a0a6-4da2-449e-909e-85ea79f78e2c.png" alt-text="Screenshot of reserving a meeting time in Outlook." lightbox="../../media/4b72a0a6-4da2-449e-909e-85ea79f78e2c.png":::

1. Type a message describing the purpose and attach any files if needed.

1. To allow others to join online or call in to the meeting, select **Microsoft Teams Meeting** at the top.

1. To make sure the room, equipment, and people you invited are available, select **Scheduling Assistant** from the menu bar. Then select an available time in the calendar.

   :::image type="content" source="../../media/eb0097c6-4263-4b63-bfca-f7c03ad99b4f.png" alt-text="Screenshot of checking if room or equipment is available in Outlook." lightbox="../../media/eb0097c6-4263-4b63-bfca-f7c03ad99b4f.png":::

   > [!TIP]
   > In the scheduling calendar, blue means the room or equipment is reserved, or busy. Select the white, or free, area on the calendar.

1. When finished, select **Send**.

## Set up room and equipment mailboxes

To set up a room or equipment mailbox, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) with an account that has appropriate permissions.

1. From the left navigation bar, select **… Show all**, and then select **Resources** to expand it.

1. Under **Resources**, select [**Rooms & equipment**](https://go.microsoft.com/fwlink/p/?linkid=2067334).

1. In the **Rooms & equipment** page, select **+ Add resource**.

1. In the **Add resource** pane, fill out the room or equipment fields:

   - **Room** or **Equipment**: The type of mailbox you'd like to create.

   - **Name**: A friendly name or short description.

   - **Email**: The email alias of the room or equipment. An email address is necessary to send a meeting request to the room or equipment.

   - **Capacity**: The number of people who can fit in the room or use the equipment at the same time.

   - **Location**: The room number or location of the room in a building or region.

   - **Phone number**: The phone number of the room itself. This phone number is different from the meeting phone number generated when using Microsoft Teams.

   :::image type="content" source="../../media/114d49e3-976e-40ef-b0af-2b0f5c85f15e.png" alt-text="Screenshot of adding a room mailbox in Microsoft 365 admin center." lightbox="../../media/114d49e3-976e-40ef-b0af-2b0f5c85f15e.png":::

1. Select **Save**.

> [!TIP]
>
> To keep your room and equipment mailboxes secure, block sign-in to these mailboxes. For more information, see [Block sign-in for the shared mailbox account](/office365/admin/email/create-a-shared-mailbox#block-sign-in-for-the-shared-mailbox-account).

## Common questions about room and equipment mailboxes

### How can you tell when the room or equipment is available?

Open Outlook and create a new meeting. Add the room or equipment to the meeting as if it were a person and select **Scheduling Assistant** to see a live calendar view of the room or equipment's availability. If the hour slot is clear, the slot is available. If the hour slot is blue, the slot is reserved.

### How do you cancel a room or equipment request?

Open the meeting you scheduled in Outlook and then remove the room or equipment from the meeting like you would an attendee. Removing the room or equipment frees up the room for others to reserve.

### Does someone have to accept or decline every room or equipment request?

No, you don't need someone to accept or decline requests. You can decide whether to let someone in your company automatically book or manage the room or equipment.

### Does a room mailbox or equipment mailbox need a product license?

No. Room and equipment mailboxes are considered resource mailboxes. While most users in your organization need a license to use Microsoft 365, you don't need to assign a license for a room mailbox or equipment mailbox. For more information, see [Exchange Online limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits?source=docs).

### Do I need an owner in charge of booking the rooms or equipment?

 No, you don't need someone in charge of the room mailbox or equipment mailbox.
