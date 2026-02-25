---
title: Organizational messages in the Microsoft 365 admin center
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
ms.date: 02/25/2026
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- operations-pod
ms.custom: campaignIDs-batch2
search.appverid:
- MET150
- MOE150
description: Learn how to send messages to your organization in Microsoft 365 using organizational messages in the Microsoft 365 admin center.
---

# Organizational messages in the Microsoft 365 admin center

As an admin, you can use organizational messages to connect with your organization through customized, in-product messages. Organizational messages are available in the Microsoft 365 admin center under **Reports**. From **Reports**, you can create and manage messages and review delivery reports from a single, central location. Use organizational messages to streamline communication with users across Microsoft products. These messages enhance in-product experiences and support remote and hybrid work scenarios by sharing:

- Educational content.
- Information about Microsoft 365 service or license availability
- Updates on organizational initiatives.

To get started, go to [Organizational messages in the Microsoft 365 admin center](https://admin.cloud.microsoft/?#/organizationalmessages).

> [!NOTE]
>
> As of November 18, 2025 Organizational Messages now include two powerful new capabilities available in Public Preview.
>
> **Email Messages**: Admins can now deliver pre‑made, templatized messages by email, extending existing surfaces like Windows Spotlight, the taskbar, Notification Center, and Microsoft Teams. For the initial Public Preview, there are eight pre-made email templates available:
>
> - Two welcome messages for *Welcome to Copilot* and *Welcome to Copilot Chat*.
> - Six templates from the *Great M365 Copilot Journey* that highlight features and best practices to help drive Copilot onboarding and adoption.
>
> **Action Segments**: Admins can now target organizational messages based on usage behaviors. For the Public Preview there are two predefined Action Segments available for Copilot usage: *Inactive Copilot Users* and *Inactive Copilot Users in Teams*.
>
> For more information about, see [Release Notes for Public Preview of Email and Action Segments](#release-notes-for-public-preview-of-email-and-action-segments).
>
> As we roll out the Public Preview for these features throughout November 2025, we're excited to see how these features enhance communication and help drive Copilot adoption within your organization. We're committed to continuously improving these capabilities based on your feedback and usage.

## What can I do with organizational messages?

Organizational messages' centralized experience within Microsoft 365 admin center includes the following features and capabilities:

- Create messages from scratch (for example, free text entry)

- Use or edit pre-made template messages from Microsoft

- Send messages to Windows 11 and Microsoft 365 app locations, such as Windows Spotlight, Windows Notification Center, Windows Taskbar, and Teams teaching popover (or coachmark)

- Save draft messages

- Reject or Approve customized messages

- Add images or icons to messages

- Specify custom destination URLs

- Configure delivery schedules and parameters for messages, including via urgent messages configuration

- Assign targeting via Microsoft Entra user groups and advanced targeting options, such as [Group Level Aggregate-based targeting](/microsoft-365/admin/adoption/group-level-aggregates)

- Manage messages created in Microsoft 365 admin center and other portals, including [Usage reports](/microsoft-365/admin/activity-reports/microsoft-365-copilot-organizational-messages)

- Review message performance with time series data

## Setup requirements

Before working with organizational messages, make sure your team satisfies the following requirements:

- **Tenant**: See [Setting tenant policies](#setting-tenant-policies).

- **Authors**: Anyone in your organization who wants to create messages must have the [Organizational Messages Writer](/azure/active-directory/roles/permissions-reference#organizational-messages-writer) role assigned to them within Microsoft 365 admin center.

- **Approvers**: Anyone in your organization who is a designated responsible party for approving customized messages must have one of these following admin roles assigned to them within Microsoft 365 admin center:

- [Organizational Messages Approver](/entra/identity/role-based-access-control/permissions-reference#organizational-messages-approver)

- **Message recipients**: Anyone in your organization who receives messages from your authors must have access to the Microsoft products your authors configure for delivery. End users aren't required to have any Microsoft Entra roles to receive organizational messages. For example, any message configured to be delivered to a Windows channel, like Windows Spotlight, requires that recipients use Windows 11 Enterprise.

- **Devices**: Microsoft Entra ID joined devices are supported, but not Microsoft Entra (AD) hybrid joined devices.

To ensure users can communicate with organizational messages, the following endpoints must be opened:

- fd.api.orgmsg.microsoft.com
- ris.prod.api.personalization.ideas.microsoft.com

## Get started

:::image type="content" source="../../media/OM-LandingPage_annotated.png" alt-text="Screenshot showing the organizational messages landing page in the Microsoft 365 admin center with numbered annotations." lightbox="../../media/OM-LandingPage_annotated.png":::

There are three basic experiences to familiarize yourself with within the organizational messages centralized experience:

1. **Manage** - Where you and your team can see most of your organizational messages created in various portals, including Usage reports and Copilot advanced deployment guide within the Microsoft 365 admin center. Your team can also execute various functions on each message, view details, and conduct approval flows in the **Manage** area.

1. **Create a message** - The wizard where anyone with the described Organizational Messages Writer Microsoft Entra role can go to create either fully customized or templatized messages.

1. **Review activity** - Where your admins can go to see the performance activity of messages that are or have been delivering to your users.

## Manage

You can review and control the messages from anyone in their organization using the main landing experience. Operations that admins can affect within the **Manage** experience include:

- Filtering based on message status (such as Active), location (such as Windows Spotlight), or objective (such as Adoption); filtering using search on message name.

- Reviewing existing message details (such as language, targeting, among others).

- Understanding aggregate performance data per message.

- Cancelling, deleting, approving, copying messages.

### How to continue creating a draft message (Modify)

If you have the Organizational Messages Writer Microsoft Entra role as described previously, you can edit or otherwise complete a saved draft message in your tenant. To do so:

1. Filter Status to **Draft**.

1. Select the message name of the message you want to edit.

1. In the message details panel, select **Modify**.

1. In the Creation Wizard, continue the creation of the draft message.

### How to approve or reject a pending approval message

If you have the Organizational Messages Approver Microsoft Entra role as described previously, you can review and approve or reject messages from your colleagues that are in the **pending approval** state. To approve or reject a **pending approval** message:

1. Filter Status to **Pending approval**.

1. Select the message name of the message you want to review.

1. In the message details panel, read through all of the content provided by the author.

1. If you believe this message is appropriate for delivering to users in your tenant, you can optionally add a comment and select **Approve**.

1. However, if you believe the message isn't ready or appropriate for delivering to your tenant's users, you must add a comment in the text field and select **Reject**.

### How to overcome a rejected message (Withdraw)

If you have the Organizational Messages Writer Microsoft Entra role as described previously, you can overcome a rejection from the approvers in your tenant. To do so:

1. Filter status to **Rejected**.

1. On the message name of the rejected message you want to overcome, select **Withdraw**.

1. The state of the rejected message is now set to **Draft**.

1. From there, you can go to the message details panel, select **Modify**.

1. The creation wizard opens up where you can continue the creation of this draft message, once again sending for approval to return the message to approvers for review.

> [!NOTE]
>
> - Fully customized messages require an approver to **approve** any message before delivery to your users. However, selecting a pre-made message doesn't require any approval from your organization before it can be delivered to end users.
>
> - Approvers can't approve or reject a message that they personally created.
>
> - **Rejecting** a message marks the message state as **Rejected**, requiring an author to **Withdraw** the message and then **Modify** the new draft.
>
> - System automatically rejects messages that aren't reviewed (such as, approved, or rejected) by approvers before the set **End date** of the message. This policy ensures minimum duration of delivery of messages as expected by authors.

## Create a message

> [!IMPORTANT]
>
> Organizational messages deliver messages to end users within the time windows configured by admins via Microsoft 365 admin center experiences. However, occasionally, messages might not be delivered as expected due to system or user device conditions. For example, urgent messages not being delivered to devices that are disconnected from the internet. In such instances, our system continues trying to deliver messages as possible and appropriate. If a device is offline while an urgent message is attempting to be delivered, the message is cached for up to 24 hours. Then, Windows attempts to show the message to the user again once the device is back online.

Users with the Organizational Messages Writer Microsoft Entra role described previously have access to the **Create a message** button and capability in the centralized experience. Selecting this button invokes the wizard, which includes these primary creation steps:

- **Objective** for selecting the nature or purpose of your new message.

- **Location** for indicating to which in-product channel the message is sent for your users.

- **Template** for choosing the format of the message, create your own or a pre-made message from Microsoft.

- **Customize** for adding customization to the message, including full text and/or custom URLs.

- **Recipients** for setting the groups within your organization that should receive the message.

- **Schedule** for configuring the start date, end date, and frequency with which the system will send the message to the same user over time. If the user doesn't select the message when the message is displayed, or dismisses the message by selecting **X**, then the message reappears again to the user later based on the specified frequency. If they do select the message, the message doesn't reappear again for a year if the message isn't already expired based on the chosen end date.

- **Finish** for reviewing the message before scheduling or sending for approval by your organization's approvers.

> [!NOTE]
>
> To support tenant-based targeting, the organizational messages system might take up to 24-48 hours to initialize for tenants that haven't scheduled a message in the past 30 days.

### Choosing custom or pre-made messages

There are two primary forms of message creation that are enabled in this experience:

- **Fully customized creation** (or 'create your own') - An open-ended format of entering in arbitrary content for messages, allowing your team to make messages that include your company name or other specifics that are unique to your company, group, or team. For example, an author can select 'create your own' and type all of the words of the message themselves.

    > [!NOTE]
    >
    > The ability to create fully customized messages is enabled if your organization has at least one Microsoft license as described in the [Advanced features](#advanced-features) section.

-. **pre-made messages** (or templatized messages) - A method of selecting and customizing content that is partially created by Microsoft for general purpose use. For example, Microsoft might provide various generic messages that your team can pick and add your logo and URL to drive awareness of a software update.

### How to save and continue draft message

1. Notice that throughout the creation wizard, each step has a **Save and close** button.

1. You can select **Save and close** at any point to save the message as a new draft.

1. Once saved, you can see your message at the top of the **Manage** table.

1. To go back to making your message, select the draft message's name to invoke the message details panel.

1. Select **Modify** in the message details panel to continue creating that message in the creation wizard.

### How to enable targeting by Companies, Departments, Locations

The advanced targeting options of "Companies", "Departments", "Locations" in the **Recipients** step of the message creation flow are made possible by the group-level aggregates settings associated with Adoption Score. To learn more, see [Group Level Aggregates in Adoption Score](/microsoft-365/admin/adoption/group-level-aggregates).

This advanced targeting in organizational messages can be enabled using the following procedure:

1. Go to **Settings** > **Org settings** within the Microsoft 365 admin center.

1. Select **Adoption Score**.

1. Under **Group data filtering**, select "Turn on group-level insights" and then "Save".

1. Within **Adoption Score**, select the "Manage group-level filtering" button.

1. Select the "Organizational attributes" checkbox and then the "Turn on selected filters" button.

> [!NOTE]
>
> The ability to use advanced targeting options is enabled if your organization has at least one Microsoft license as described in the [Advanced features](#advanced-features) section.

### How to create a message by copying an existing message

1. Go to the Manage experience and find a message you want to use as a starting point.

1. Select the **Copy** function.

1. You're immediately placed within the creation wizard with relevant elements from the previous message copied over.

1. Edit as you like and complete the creation wizard or save as a draft.

> [!NOTE]
>
> - For the same channel (such as Windows Spotlight), images provided by your team for the last created message are automatically provided for your next message. However, you can override that image with a new image upload.
>
> - Once you select **Send for approval** at the end of a fully customized message creation flow, anyone in your tenant that has the Organizational Messages Approver Microsoft Entra role that is described previously is able to review and approve or reject your message.
>
> - If you save your draft before the **Schedule** step and thus don't provide a custom message name, the draft has a programmatically generated name based on the date-time when you saved the draft. You can edit this message name by modifying the draft message.
>
> - Not all selections in the **Objective** step might have pre-made messages available. However, all objectives have the create your own format available for full customization authoring.

### Urgent delivery

For some time-sensitive communications, admins and other communicators might need to get a message out fast. Admins might need to quickly broadcast an event to some users so they can be prepared. For example:

- An event is occurring on a corporate campus.
- A service outage begins.

To support communications in such events, admins in Microsoft 365 admin center are able to select the **Urgent messages** button in the "Top Actions" section.

The message creation experience for an urgent message is similar to the flow for creating other messages with these exceptions:

- The only locations available are Windows 11 Taskbar and Notifications area.
- Only Microsoft Entra group targeting can be used.
- No Start/End dates nor frequency configurations are available as urgent messages are sent once as soon as possible.

  :::image type="content" source="../../media/OM-urgentMessages_annotated.png" alt-text="Screenshot that highlights the button to send an urgent message." lightbox="../../media/OM-urgentMessages_annotated.png":::

## Review activity

As you can see upon visiting the centralized experience, the basic Manage table includes basic aggregate insights data for your messages (including Total messages seen, Total clicks, and Clickthrough rate). However, the centralized experience also includes advanced insights experiences, including:

- Filtering on time range, status, and other aspects,

- Graphing of selected date range,

- Data export to CSV

You also see three time-series data charts at the top, showing daily changes in the Total messages seen (or impressions), Total clicks, and Clickthrough rate for your messages.

### How to export data

If you or your team would like to work with your tenant's message performance data, you can export it to a CSV file. To do so:

1. Set the filters, including time range, for the data you're interested in retrieving.

1. Select the **Export to CSV** button and save the file locally.

## Advanced features

Advanced features are experiences in Organizational messages in the Microsoft 365 admin center that are restricted to tenants and users, which meet the following requirements:

### Tenant - accessing advanced features when creating messages

Advanced features are accessible to admins within Organizational messages in the Microsoft 365 admin center when their tenant has one of the following licenses:

- Microsoft 365 E3-E5 licenses
- Office 365 E3-E5 licenses
- Windows Enterprise E3-E5 licenses

### End user - receiving messages with advanced features

End users within a tenant are eligible to receive messages created using advanced features when these end users personally have one of the following licenses:

- Microsoft 365 E3-E5 license
- Office 365 E3-E5 license
- Windows Enterprise E3-E5 license

### Current advanced features

The advanced features in Organizational messages in Microsoft 365 admin center include:

1. Fully customized message creation
1. Advanced targeting - group level aggregates (Department, Location, Company)

## Setting tenant policies

> [!NOTE]
> Setting tenant policies is only required for delivering messages to Windows surfaces such as Windows Spotlight, Windows Notification Center, and Windows Taskbar. It isn't required for sending messages to Teams Teaching Popover or to Email.

There are certain policies that block the delivery of organizational messages to your end users if not configured properly, such as using [Microsoft Intune](https://intune.microsoft.com). This section describes some ways to adjust all policy settings for your tenant so that delivery is allowed and works as intended.

### General Instructions

>[!NOTE]
> If you recently onboarded your tenant to Microsoft Entra ID, it can take 36 to 64 hours before you're able to use the organizational messages features.

To make policy changes on your tenant using Intune, your admin should:

1. Sign in to the Microsoft Endpoint Manager admin center for your tenant.

1. Configure the policies described using a Microsoft Intune device restrictions profile template or the settings catalog.

1. Make sure to adjust these policies in all new and existing policies that are targeted at end users and devices that might receive organizational messages.

1. Enable Organizational Messages Policy.

   > [!NOTE]
   >
   > This policy is required for devices running [Windows](https://support.microsoft.com/topic/november-29-2022-kb5020044-os-build-22621-900-preview-43f0bdf9-0b75-4110-bab3-3bd2433d84b3), [version 22H2](https://support.microsoft.com/topic/november-29-2022-kb5020044-os-build-22621-900-preview-43f0bdf9-0b75-4110-bab3-3bd2433d84b3), [build 10.0.19045.4842](https://support.microsoft.com/topic/august-29-2024-kb5041582-os-build-19045-4842-preview-f4c4d191-5457-475c-80ac-e1d43cf9c941), [build 10.0.22621.900](https://support.microsoft.com/topic/november-29-2022-kb5020044-os-build-22621-900-preview-43f0bdf9-0b75-4110-bab3-3bd2433d84b3) and later. If you don't enable this policy, these devices can't receive organizational messages.

1. Go to **Settings catalog** > **Experience** > **Enable delivery of organizational messages (User)**.

1. To enable delivery of organizational messages, switch the toggle to **Enabled**.

### Enable Experiences Policies

>[!NOTE]
>
> If you use the Windows Mobile Device Management (MDM) security baseline, you need to change the required policies to **Not configured**. These policies control organizational messages configured by your team and other messages coming directly from Microsoft. To continue blocking messages coming directly from Microsoft as defined in the Windows MDM security baseline, configure the Microsoft messages policy found in the Organizational messages settings experience within the admin center.

If using Settings catalog, follow these steps:

(Refer the new or existing Windows configuration profile.)

1. Go to **Devices** > **Windows** > **Configuration profiles**.

1. Select **Settings catalog**.

1. Select **Add Settings**.

1. In Settings picker, select **Experience category**.

1. In configuration settings, ensure the following are selected or set to **Allow**:

   - Add Allow Windows Spotlight (User)
   - Add Allow Windows Spotlight on Action Center (User)
   - Add Allow Windows Tips
   - Add Configure Windows Spotlight on Lock Screen (User)

1. In configuration settings, ensure the following are deselected:

   - Disable Cloud Optimized Content

1. In configuration settings, ensure the following are selected or set to **Allow**:

    - Enable delivery of organizational messages (User)

If using Device Restrictions, follow these steps:

(Refer the new or existing Windows configuration profile.)

1. Go to **Devices** > **Windows** > **Configuration profiles**.

1. In a new or existing template profile, select **Device restrictions** > **Windows Spotlight**.

1. Ensure or Select **Not configured** is set for:

   - Windows Spotlight.
   - Windows Spotlight on lock screen.
   - Windows Tips.
   - Windows Spotlight in action center.
   - Windows Spotlight personalization.

## Release Notes for Public Preview of Email and Action Segments

- Email functionality during the Public Preview is limited to the 8 provided pre-made templates and in English only. The Email templates aren't customizable.

- Message analytics aren't yet available for Email. They are coming soon during the Public Preview.

- Action Segments can't be used together with Email messages during the Public Preview. Action Segments are available for the existing surfaces of Windows Spotlight, Task Bar, Notification Center, and Teams Popover.

- Action Segments during the Private Preview are limited to the 2 provided segments: *Inactive Copilot Users* and *Inactive Copilot Users in Teams*.
