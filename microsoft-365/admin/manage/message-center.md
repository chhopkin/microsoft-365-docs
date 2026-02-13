---
title: "Prepare for Microsoft 365 updates with Message center"
f1.keywords:
- CSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 02/12/2026
ms.reviewer: brimcg
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Tier2
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
description: "Get an overview of Microsoft 365 Message center and its role in tracking new and changed features and other important announcements."
---

# Track new and changed features in the Microsoft 365 Message center

The Microsoft 365 Message center helps IT admins track upcoming changes, feature updates, and required actions across services. Use Message center to plan for change, prevent disruptions, and stay informed about Microsoft 365 updates that affect your organization.

::: moniker range="o365-worldwide"

To open Message center from the Microsoft admin center, go to **Health** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Message center</a>.

::: moniker-end

::: moniker range="o365-21vianet"

To open Message center from the Microsoft admin center, go to <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to **Health** > **Message center**.

::: moniker-end

You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Message center, which is a great way to stay current with push notifications.

## Updates to Microsoft 365 Message center

The Microsoft 365 Message center is now more timely, relevant, and concise to support actionable communications. To help IT admins quickly understand changes, posts now include bullet-point summaries, direct links to documentation, and launch-day announcements instead of early notifications.

Message center includes an improved post structure with the following new sections:

### What and Why

This section briefly describes the change with the reason behind it and includes the following details:

- What is changing (for example, new feature, update, retirement)
- Why Microsoft is making the change (for example, customer feedback, security, productivity)
- Alignment with one of three areas:
  - Personal and Team Productivity
  - Business Process Automation
  - Enterprise-ready AI

### Rollout Schedule

This section specifies when the change begins and ends and includes the following details:

- Start and end dates
- Phased rollout information, if applicable
- Preview or General Availability (GA) status

### Impact on Your Organization

This section helps you understand who and what is affected and includes the following details:

- Who's affected: Scope of impact (for example, all users, specific roles, tenants)
- Platforms/Services: Where the change applies (for example, Teams, Outlook, mobile, desktop)
- What will happen with clear bullet points describing:
  - UI changes
  - Feature behavior
  - Default settings
  - Policy interactions
  - End-user experience

### Action Required/Recommendations

This section guides IT admins on what to do and includes the following details:

- Checklist of required actions (for example, update settings, notify helpdesk)
- Optional recommendations
- Links to admin guides or documentation
- Whether the feature is opt-in or enabled by default

### Compliance Considerations

This section identifies any implications for data handling and governance and includes the following details:

- Data storage or processing changes
- AI/ML interactions with customer data
- Communication or access changes
- Impact on Purview capabilities (for example, DLP, eDiscovery)
- GDPR-related changes
- Admin control availability and Microsoft Entra ID integration
- Whether users can self-manage the feature

## Frequently asked questions

### Who can view posts in Message center?

Most users assigned any admin role in Microsoft 365 can view Message center posts. [Here's a list](#admin-roles-that-dont-have-access-to-the-message-center) of admin roles that don't have access to the Message center. You can also assign the Message center reader role to users who should be able to read and share Message center posts without having any other admin privileges.

### Is Message center the only way Microsoft communicates changes about Microsoft 365?

No, but Message center is the primary way we communicate the timing of individual changes in Microsoft 365. For more information, see [Stay on top of Microsoft 365 changes](stay-on-top-of-updates.md).

### How can I see Message center posts in my language?

Message center posts are written in English. You can control whether, by default, posts are shown in English or are automatically machine-translated to your preferred language. You can also select to machine-translate posts to any language we support. For more information, see [Language translation for Message center posts](language-translation-for-message-center-posts.md).

### Can I preview changes or features before they're rolled-out to my organization?

Some changes and new features can be previewed by opting in to the Targeted release program. To opt in, from the Microsoft admin center, go to **Settings** > **Org settings** > **Organization profile** > **Release preferences**. You might need to select **Show all** at the bottom of the left navigation pane in Microsoft admin center to see **Settings**. You can choose Targeted release for your entire organization, or just for selected users. For more information about Targeted release, see [Standard or Targeted release options in Microsoft 365](release-options-in-office-365.md).

### VERIFY IF STILL ACCURATE - Can I find out the exact date a change is available in my organization?

Unfortunately, we can't tell you the exact date a change is made to your organization. In our Message center post, we give as much information as we can on the timing of the release, based on our confidence level. We're working on improvements to get better with that level of detail.

### Are these messages specific to my organization?

We do our best to make sure that you only see Message center posts that affect your organization. The Microsoft 365 Roadmap includes all of the features we're currently working on and rolling out, but not all of these features apply to every organization.

### Can I get message center posts emailed instead?

Yes, you can select to have a weekly digest emailed to you and up to two other email addresses. The emailed weekly digest is turned on by default. If you aren't getting your weekly digests, check your spam folder. For more information on how to set up the weekly digest, see the [Preferences](#preferences) section of this article.

### How do I stop getting the Message center digest?

1. Go to Message center in the Microsoft admin center and select **Preferences**.
1. In the **Email** tab, turn off the option to **Send me email notifications from message center**.

### How can I ensure data privacy notifications are received by the right contacts in my organization?

As a global admin, you receive data privacy messages for your organization. Additionally, you can assign the Message Center Privacy reader role to people who should see data privacy messages. Other admin roles with access to Message Center can't view data privacy messages. For more information, see [Preferences](#preferences) in this article.

### Why can’t I see a message that was previously in Message center?

To manage the number of messages within Message center, each message expires and is removed after a period of time. Generally, messages expire 30 days after the time period outlined in the message body.

## Feature release status for your organization in Message Center

For each new and updated feature announcement in Message center, the **Status for your org** field provides a release status to help you track when a feature is available in your tenant.

These three release statuses are updated on each applicable message over the lifecycle of the feature release:

- **Scheduled**: The feature is planned to release to your tenant, and isn't available to any users in your organization

- **Rolling out**: The feature is beginning to roll out to some applicable users in your organization.

- **Launched**: The feature is generally available to all the applicable users in your organization.

Updates to feature release status are provided on the original Message center post. Filtering capability on **“Status for your org”** allows easier visibility on the updated release status.

The release status is **ONLY** available for new and updated features that are also announced on Microsoft 365 Public Roadmap and that have general availability status (production ready). If you don't see release status on a message, it means the release status isn't available for that feature.

> [!NOTE]
> The release status will initially be available for a limited number of Microsoft Teams, Outlook on the web and Microsoft 365 admin center feature announcements.

## Relevance recommendation

For each new Message center post, we provide a recommendation for how relevant the change is for your organization. This recommendation is based on multiple factors such as:

- Apps and service usage.
- Changes meant to prevent or fix issues for subscription.
- Changes meant to help you plan ahead or stay informed.
- Impact changes, such as data privacy and app and service retirements.

There are three levels of relevance:

- **High** - These posts are about changes in your organization, which need immediate action to avoid service disruption. These posts can also include feature releases with high potential impact to your organization, for example, an app or service being heavily used by people in your organization.

- **Medium** - These posts are about changes in your organization, which don't need immediate action. Examples are nonbreaking changes or new features for a service, which is being used by your organization, an early announcement for an upcoming breaking feature change, retirement

- **Low** - These posts are about changes that you need to monitor. They're related to low impact apps and services in your organization. Examples would be a feature update for an app or service, which isn't actively used in your organization.

The relevance recommendations are **ONLY** available for the newer MC posts. This means the MC posts you already received are "blank" for relevance recommendation.

If you see **Processing** for a Message center post, it means that the score is being computed for this post and should be available soon. You should try to refresh after a few minutes.

Once you start receiving this, tell us if a Message center post is **not relevant** to you through the [**extended feedback**](#give-feedback-on-a-post). This feedback is important for us to improve the accuracy of the relevance recommendations.

## Filter messages

Message center presents a view of all active messages in a table format. By default, it shows the most recent message at the top of the list.

Use the **Service**, **Tag**, and **Message state**  drop-down menus to select a filtered view of messages:

- Under **Service**, you can select various services, such as Microsoft 365 Apps, SharePoint Online, etc., to filter messages.
- Under **Tag**, you can select **Admin impact**, **Data privacy**, **Feature update**, **Major update**, **New feature**, **Retirement**, or **User impact** messages.
- Under **Message state**, you can select **Favorites**, **Unread**, or **Updated** messages.

The **Archive** tab shows the messages you have archived. To archive a message from the message pane, select **Archive**.

You can select any column heading, except **Service** and **Tag**,  to sort messages in ascending or descending order.

### Major updates

#### INCORPORATE INTO UPDATED MC SECTION?

Major updates can be reviewed by selecting the **Major update** from the **Tags** drop-down.

Major updates are communicated at least 30 days in advance when an action is required and might include:

- User impacting changes to daily productivity such as changing a user’s inbox, meetings, delegations, sharing and access that might result in help desk calls, or organizational conformance concerns.
- Changes to the themes, web parts, deployed Copilot agents, and other components that might impact customer customizations.
- Increases or decreases to visible capacity such as storage, number of rules, Copilot agents and prompts, items, or durations.
- Rebranding that might cause end-user confusion or result in help desk changes, collateral changes, or URL changes if the new URL isn't *.cloud.microsoft
- A new service or application deployed with default settings turned on.
- Changes to where data is stored or accessed.

### Preferences

If administration is distributed across your organization, you might not want or need to see posts about all Microsoft 365 services. Each admin can:

- Set preferences that control which messages are displayed in Message center.
- Filter messages.
- Set email preferences to receive a weekly digest of all messages, emails for major updates only, and emails for data privacy messages.

To access Message center preferences, do the following steps:

::: moniker range="o365-worldwide"

1. Select **Preferences** at the top of Message center.

2. In the **Custom View** tab, make sure that the check box is selected for each service that you want to monitor. Clear the check boxes for the services you want to filter out of your Message center view.

3. Digest emails are turned on by default and are sent to your primary email address. To stop receiving the weekly digest, clear the **Send me email notifications from message center** check box in the **Email tab**.

   You can also enter up to two email addresses, separated by a semicolon.

   You can also choose the emails you want to get, and a weekly digest of services you select.

4. Select **Save** to keep your changes.

::: moniker-end

::: moniker range="o365-21vianet"

1. Select **Preferences** at the top of Message center.

2. In the **Custom View** tab, make sure that the check box is selected for each service that you want to monitor. Clear the check boxes for the services you want to filter out of your Message center view.

3. Digest emails are turned on by default and are sent to your primary email address. To stop receiving the weekly digest, clear the **Send me email notifications from message center** check box in the **Email tab**.

   You can also enter up to two email addresses, separated by a semicolon.

   You can also choose the emails you want to get and a weekly digest of services you select.

4. Select **Save** to keep your changes.

::: moniker-end

### Display messages in your preferred language

We use machine translation to automatically display messages in your preferred language. Read [Language translation for Message center posts](language-translation-for-message-center-posts.md) for more information on how to set your language.

> [!NOTE]
> The weekly digest and any posts that are emailed are sent in English-only. Recipients can use [Translator for Outlook](https://support.microsoft.com/office/3d7e12ed-99d6-406e-a453-b9db0d9653fa) to read the message in their preferred language.

## VERIFY NOTE - Service & monthly active users

When you open a message center post, we'll tell you the number of users who have been using that Microsoft 365 app or service in the **Service & monthly active users** section. The numbers are for the last 28 days. This info can help you prioritize which changes you should work on.

:::image type="content" source="../../media/msgctr-mau-teams.png" alt-text="Screenshot: Showing the Microsoft Teams Chat density page in the message center post with monthly active user data":::

The number of monthly users applies to all users who have been using that Microsoft 365 app or service on any device.

> [!NOTE]
> This feature isn't available for all Microsoft 365 productivity apps and services yet. We'll let you know when the feature isn't available.

## Display specific columns

To choose columns, on the **Message center** page, on the far right, select **Choose columns**, and in the **Choose columns** pane, select the ones you want displayed.

Here's a quick overview of the information in each column.

### Column information

|Column|Description|
|---|---|
|Check mark|Selecting the check mark in the column heading row selects all messages currently displayed. Selecting the check mark next to one or more messages lets you take action on those messages.|
|Message title|Message titles are brief descriptions of upcoming changes. If the full title doesn't display, hover your cursor over it and the entire title will appear in a pop-up box.|
|Service|Icons indicate the application to which the message applies.|
|More options|More options let you dismiss a message, mark it as read or unread, or share it with another admin. To restore an archived message, select the **Archive** tab, select the check mark next to the message, and select **Restore**.|
|Tags| You can choose tags from the Tag drop-down to filter messages. <br> <p> **Data Privacy**: Data privacy notification (limited to global administrator and Message center Privacy reader roles). <p> **Major update**: Changes communicated at least 30 days in advance ([Major updates](#major-updates)). <p> **Retirement**: Retirement of a service or feature. <p> **New feature**: New feature or service. <p> **Feature update**: Update to an existing feature. <p> **Admin impact**: When the change clearly impacts the admin in the following ways - UI change, workflow change, control available, and Specific/Potential Action. <p> **User impact**: When the change to the service clearly impacts the user - UI Change and workflow change. <p> **Updated message**: When a message is updated.|
|Category| This isn't shown by default, but can be specified in the **Choose columns** panel. Messages are identified by one of the following three categories: <p> **Prevent or fix issues**: Informs you of known issues affecting your organization and might require that you take action to avoid disruptions in service. Prevent or fix issues are different than Service health messages because they prompt you to be proactive to avoid issues. <p> **Plan for change**: Informs you of changes to Microsoft 365 that might require you to act to avoid disruptions in service. For example, we let you know about changes to system requirements or about features that are being removed. We try to provide at least 30 days' notice of any change that requires an admin to act to keep the service running normally. <p> **Stay informed**: Tells you about new or updated features we're turning on in your organization. announced first in the [Microsoft 365 Roadmap](https://go.microsoft.com/fwlink/?linkid=2070821). <p> Also lets you know about planned maintenance in accordance with our Service Level Agreement. Planned maintenance might  result in down time, where you or your users can't access Microsoft 365, a specific feature, or a service such as email or OneDrive.|
|Act by|We'll only have dates here if we're making a change that requires you to take an action by a certain deadline. Since we rarely use the **Act by** column, if you see something here, you should pay extra attention to it.|
|Last updated|Date that the message was published or last updated.|
|Message ID|Microsoft tracks our Message center posts by message ID. You can refer to this ID if you want to give feedback or if you call Support about a particular message.|

[!INCLUDE [global-administrator-note](../../includes/global-administrator-note.md)]

### Admin roles that don't have access to the Message center

- Compliance administrator
- Conditional access administrator
- Customer Lockbox access approver
- Device administrators
- Directory readers
- Directory synchronization accounts
- Directory writers
- Intune service administrator
- Privileged role administrator
- Reports reader

## Give feedback on a post

In the Message center, you can select a message to view details.

If a Message Center post isn't relevant to your organization, provide us with feedback. Select thumbs up or thumbs down on the MC post and select **This change isn't relevant to my org**.

> [!NOTE]
> If you're using Microsoft 365 for Government - GCC High and Office 365 Government - DoD, you can't provide feedback on a post.

## Share a message

See a message that someone else needs to act on? You can share the contents of the message with any user by email:

1. Select the message to open it, and then select **Share**.

2. To share the message, enter email addresses separated by a colon. You can send to individual and group email addresses. Optionally, you can choose to receive a copy of the message in email (the message goes to your primary email address) or add a personal message to provide recipients with more context.

3. Select **Share** to send the email.

## Get a link

Need to follow up with another admin to make sure they're aware of a change and taking action? You can generate a link to share in email or instant messaging. The person you share the link with has to have access to Message center. For more information, see [admin roles that don't have access to the Message center](message-center.md#admin-roles-that-dont-have-access-to-the-message-center).

1. Select the message center post.

2. Select **Copy link**.

3. Use Ctrl+V or right-click and select **Paste** to insert the link to whatever document you wish.

## Read and unread states

Any unread message in Message center appears in bold. Opening a message marks it as read.

To mark a message as unread, from the main page of the message center, select the **More options** ellipses next to a message, and then select **Mark as unread**. You can also open a message and mark it as unread in the details panel.

## Archive and restore a message

If you see a message that doesn't pertain to you, or maybe you've already acted on it, you can archive the message. Archiving a message removes it from the Inbox. The view that you see in the Message center is specific to your user account, so archiving it from your view doesn't affect other admins.

There are two ways to archive a message:

- On the main page of the Message center, select a message, and then select **Archive** above the list of messages.
- Open the message, and then select **Archive** on the top of the message pane.

Need to get an archived message back? No problem.

1. Select the **Archive** tab at the top of the Message center. A list of archived messages appears.

1. Select the message, select **Restore**, and the message is restored to Inbox.

## Favorite messages

To mark a message as a favorite, hover over the message title and you'll see a **Favorite** :::image type="icon" source="../../media/favorite-star.png" border="false"::: star you can select right after the **More options** ellipses. Once you have marked messages as favorite, you can also sort and filter them.

## Scroll messages in the message pane

When you open a message in a reading pane, you can use the **Up** and **Down** :::image type="icon" source="../../media/updownarrows.png" border="false"::: arrows on the top of the pane to move to the next, or the previous message in the list.

## Track your message center tasks in Planner

A lot of actionable information about changes to Microsoft 365 services arrives in the Microsoft 365 message center. It can be difficult to keep track of which changes require tasks to be done, when, and by whom, and to track each task to completion. You also might want to make a note of something and tag it to check on later. You can do all this and more when you sync your messages from the Microsoft 365 admin center to Microsoft Planner. For more information, see [Track your message center tasks in Planner](/office365/planner/track-message-center-tasks-planner).

## Set language translation for Message center posts

To learn how to set your language preferences to enable machine translation for Message center posts, see [Language translation for Message center posts](language-translation-for-message-center-posts.md).

## Work with service communications API in Microsoft Graph

If you'd like to program an alternative way to get real-time service health information and Message center communications, see [Working with service communications API in Microsoft Graph](/graph/api/resources/service-communications-api-overview).

## Unsubscribe from Message center emails

1. Digest emails are turned on by default and are sent to your primary email address. To stop receiving the weekly digest, select **Preferences** and then **Email**.
    - Deselect the **Send a weekly digest of my messages** checkbox.
    - Email notification for major updates is a separate control. If you don't want to receive email notices about major updates, verify that **Send me emails for major updates** checkbox isn't selected.
    - To stop receiving email notices about data privacy messages, verify that **Send me emails for data privacy messages** checkbox isn't selected. (Data privacy messages aren't included in the weekly digest.)

2. Select **Save** to keep your changes.

## Related articles

[Plan for modern change management in Microsoft 365](plan-for-modern-change-management.md)

[Set up the Standard or Targeted release options](../manage/release-options-in-office-365.md)

[Configure Standard or Deferred release options for Microsoft 365 Copilot](configure-release-options.md)
