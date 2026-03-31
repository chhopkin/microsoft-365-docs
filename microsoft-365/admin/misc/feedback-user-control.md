---
title: Microsoft Feedback User Experience and Control
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
manager: dansimp
ms.date: 03/31/2026
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- must-keep
- trust-pod
- feedback-content
ms.custom: campaignIDs-batch1
hideEdit: true
description: Learn how to manage Microsoft feedback in your organization, understand what data Microsoft collects, and configure policies in Microsoft 365. Get started now.
---

# Microsoft Feedback user experience and control

To manage Microsoft feedback for your organization, you need to understand how Microsoft 365 apps collect and use feedback. This article explains feedback types, what Microsoft feedback collects, and how it handles feedback data so you can configure policies with confidence.

As an admin, you can manage the feedback experience for your organization. Microsoft provides policy settings to help you manage user feedback collection in Microsoft 365 apps. These policy settings help you target Microsoft Entra groups and configure the feedback collection experience. User feedback goes directly to engineers and helps shape the future of Microsoft products and services for all users. To learn more about these policy settings, which apps they apply to, and best practices, see [Manage Microsoft feedback for your organization](../manage/manage-feedback-ms-org.md).

## Feedback types

### In-product feedback

If your users are using one of Microsoft's apps and want to provide feedback, they can do so in various ways from within the apps. Users can use these different ways to share product and feature feedback with Microsoft. One of the most common ways to share feedback in Microsoft apps is under the **Help** menu. Selecting **Help** > **Feedback** from most Microsoft apps launches a feedback page, which allows users to submit feedback to Microsoft.

#### In-product feedback examples

The following images show examples of how users can provide in-product feedback to Microsoft from various Microsoft 365 apps. The feedback experience might look different across different apps, but the core experience of providing feedback and the data collected with that feedback is consistent across apps.

- **Windows**: The following image shows the feedback form from the **Feedback Hub** app in Windows. To reach the form, users can open the **Feedback Hub** app from the **Start** menu.

    :::image type="content" source="../../media/In-appfeedbackbackstage.png" alt-text="Screenshot of the Windows Feedback Hub app." lightbox="../../media/In-appfeedbackbackstage.png":::

- **Microsoft Excel**: The following image shows how users can provide feedback from **Microsoft Excel**. The image shows the feedback pane that opens when a user selects **Help** > **Feedback** from the ribbon.

    :::image type="content" source="../../media/In-appfeedbackwindows.png" alt-text="Screenshot of Excel in-product feedback initiated from the Feedback button." lightbox="../../media/In-appfeedbackwindows.png":::

- **Microsoft Teams**: The following image shows the feedback form from **Microsoft Teams**. To reach the form, users can select the horizontal ellipsis (**...**) from the title bar and then select **Feedback**.

    :::image type="content" source="../../media/TeamsIn-appFeedback.png" alt-text="Screenshot of Teams in-product feedback initiated from the Help menu." lightbox="../../media/TeamsIn-appFeedback.png":::

### In-product surveys

Users can rate their experience and provide additional information about their experience through system-initiated survey prompts. These prompts occur within the Microsoft 365 products from time to time. When prompted, users can choose if they want to provide feedback. The survey prompts typically appear at the bottom right of the app. If the user decides to provide feedback, dismisses the prompt, or lets the prompt disappear on its own, the user doesn't see the survey again for some time. Microsoft also uses a governance process to limit the number of these system-initiated surveys. Governance ensures the number of survey prompts doesn't overwhelm users.

:::image type="content" source="../../media/feedback-love.png" alt-text="Screenshot of in-product survey feedback request." lightbox="../../media/feedback-love.png":::

:::image type="content" source="../../media/feedback-excel.png" alt-text="Screenshot of Excel in-product survey feedback request." lightbox="../../media/feedback-excel.png":::

### Community feedback

Users can use the [Microsoft Feedback Portal](https://feedbackportal.microsoft.com/feedback/) to participate in public community forums for all the Microsoft 365 products. The Microsoft Feedback Portal allows users to browse and upvote publicly submitted feedback and submit new community feedback for any of the supported products. Top known feedback items remain available in the portal. This portal also allows users to track official Microsoft responses and engage with Microsoft on feedback they submit.

:::image type="content" source="../../media/community-feedback1.png" alt-text="Screenshot of Microsoft Teams feedback portal page." lightbox="../../media/community-feedback1.png":::

## What feedback is most useful?

Detailed and actionable feedback is vital for making changes and improvements in Microsoft products. If your users have issues or suggestions for how Microsoft can improve, Microsoft would like to hear from them. The following are a few tips and examples on actionable feedback sent to Microsoft.

- **Concise and descriptive title**: Descriptive and specific titles help Microsoft understand the issue being reported. For example:

    Excel's **Recent files** list doesn't include recently added OneDrive files.

- **Focus on one issue at a time**: Provide feedback for one issue or recommendation at a time. Providing feedback for only one item at a time ensures the correct logs and data are received with each submission and can be assigned for follow-up. If you have more than one issue, submit a new feedback request for each issue. Submitting separate requests for each item helps Microsoft identify the volume of feedback it's receiving for a particular issue.

- **Write details in the Description box**: Information about your device, operating system, and apps are automatically included in each submission. Add any additional info about an issue you think is important. For example, include detailed steps to reproduce the issue.

## How Microsoft uses feedback

Microsoft uses feedback to improve Microsoft products. Microsoft gathers user feedback in the form of questions, problems, compliments, and suggestions. Microsoft makes sure this feedback makes it back to the appropriate teams, who use feedback to identify, prioritize, and make improvements to Microsoft products. Feedback is essential for Microsoft product teams to understand users' experiences and directly influences the priority of fixes and improvements.

### What does Microsoft collect?

When a user submits feedback, Microsoft collects app information along with app ratings and feedback descriptions. Here are the most common items Microsoft collects or calculates.

| **Item**                         | **Description**                                                                                     |
| -------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Comments**                     | User-submitted comments in the original language.                                                   |
| **App**                          | The Microsoft product obtained from the feedback form.                                              |
| **Date submitted**               | Date and time when the feedback was submitted.                                                      |
| **User ID**                      | Microsoft Entra ID or email address of the authenticated user submitting the feedback. Anonymous feedback is allowed but not shown in this view. |
| **User Email**                   | If the user is okay with providing their email address for follow-up.                               |
| **Language or Comment Language** | Original language the comment was submitted in.                                                     |
| **Feedback Type**                | Survey feedback or in-product feedback.                                                             |
| **Survey Questions**             | Questions that Microsoft asks the user during the survey.                                           |
| **Survey Responses**             | User responses to survey questions.                                                                 |
| **Channel**                      | Channel of the Microsoft product related to the feedback.                                           |
| **App Build**                    | Build number of the Microsoft product that was captured on submission.                              |
| **App Language**                 | Language of the Microsoft product that was captured on submission.                                  |
| **Attachments**                  | Shows if any attachments were collected as part of the feedback.                                    |
| **Tenant ID**                    | If feedback is submitted from a Microsoft Entra account, this value shows the associated tenant ID. |
| **App module**                   | Information about app modules that might have caused a recent crash, where applicable.              |
| **Optional diagnostic data**     | If you opt in, this data is included with the feedback. For more information, see [Optional diagnostic data for Office](/microsoft-365-apps/privacy/optional-diagnostic-data). |

If the corresponding policies are enabled, Microsoft might allow users to submit screenshots, attachments, content samples, and logs to help debug and resolve problems the user might be running into. Microsoft uses this data to debug and resolve problems that might be challenging or impossible to resolve without this additional information. Users choose whether or not to submit this content and data to Microsoft.

- **Screenshots**: Captures the user's screen at the time they submitted feedback. For example, the screen including the dialog box from which the user is submitting feedback.

- **Attachments**: Files the user can submit as attachments as part of their feedback. For example, the file they were working on when they encountered a problem.

- **Content samples**: Content from a document or interaction with Microsoft services. For example, the prompt and response to an AI service.

- **Log files**: Additional log files that aren't included in [diagnostic log files](https://support.microsoft.com/office/fba86aac-70dc-4858-ae1f-ec2034346cdf). The log files might include the user's name or contents of the user's files. For example, logs that include the element of the customer's file that's preventing the file from saving.

For more information, see the following articles:

- [Providing feedback about Microsoft Copilot with Microsoft 365 apps](https://support.microsoft.com/topic/c481c26a-e01a-4be3-bdd0-aee0b0b2a423) for what feedback data is collected about Microsoft Copilot with Microsoft 365 apps.

- [Configure log files for monitoring and troubleshooting in Teams](/microsoftteams/log-files) for Microsoft Teams log files.

## View your users' feedback

Administrators can view, delete, and export the feedback data for their organizations in the Microsoft 365 admin center. This functionality helps administrators provide direct transparency into their users' experiences with Microsoft 365 products and enables user feedback data to be part of any [Data Subject Request](/compliance/regulatory/gdpr-dsr-office365). The [Compliance Administrator](/entra/identity/role-based-access-control/permissions-reference#compliance-administrator) role can view, export, and delete user feedback. All other administrators and readers can view and export feedback data. However, they can't perform compliance-related tasks or see information about who posted the feedback. For example, all other administrators and readers can't see the following information:

- Username.
- Email.
- Device name.

To access your organization's feedback data:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Health** to expand it.

1. Under **Health**, select [**Product Feedback**](https://admin.cloud.microsoft/?#/tenantfeedback).

:::image type="content" source="../../media/manage-feedback-3.jpg" alt-text="Screenshot of product feedback in the Microsoft 365 admin center.":::

## Data handling and privacy

When you use Microsoft cloud services, you're entrusting Microsoft with one of your most valuable assets: your data. Microsoft ensures the feedback it receives is stored and handled under Microsoft governance rules, and that it can only be accessed for approved uses. Microsoft doesn't use your email, chat, files, or other personal content to target ads to you. When Microsoft collects data, it uses the data to make your experiences better.

To learn more about how Microsoft protects the privacy and confidentiality of your data, review the privacy principles at the [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy). These principles describe how Microsoft ensures your data is used only in ways that are consistent with your expectations.
