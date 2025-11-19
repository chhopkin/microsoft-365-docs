---
title: "Copilot in Microsoft 365 Admin Centers"
description: "Learn how to use Copilot in Microsoft 365 admin centers to automate tasks, navigate features, and gain actionable insights with natural language queries."
#customer intent: As an admin, I want to understand how to use Copilot in Microsoft 365 admin centers so that I can simplify and streamline admin tasks.
f1.keywords:
- NOCSH
author: kwekuako
ms.author: kwekua
manager: scotv
ms.date: 10/23/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
  - scotvorg
  - M365-subscription-management
  - Adm_O365
  - Adm_TOC
  - m365copilot
  - magic-ai-copilot
  - operations-pod
---

# Copilot in Microsoft 365 admin centers

Copilot in Microsoft 365 admin centers uses generative AI to make you more productive by simplifying administration of Microsoft 365 and Microsoft 365 Copilot. It helps you focus on more strategic priorities. Copilot in Microsoft 365 admin centers helps you perform tasks across different Microsoft 365 services. It provides natural language interactions, contextual guidance, and proactive suggestions.

## Before you begin

You must have a Microsoft 365 Copilot license enabled for your tenant. For more information about Copilot licensing, see [License options for Microsoft 365 Copilot](microsoft-365-copilot-licensing.md).

## Get started

To use Copilot in Microsoft 365 admin centers, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/), or one of the specialized admin centers like Teams, SharePoint, or Exchange.

2. Select the Copilot button in the upper right shell to launch Copilot in Microsoft 365 admin centers.

:::image type="content" source="media/copilot-for-microsoft-365-admin-centers-button.png" alt-text="Screenshot of the Microsoft 365 admin center highlighting the Copilot button in the ribbon.":::

## How can I use Copilot in Microsoft 365 admin centers?

You can use Copilot to help manage your organization and focus on what's important. Try using the prepopulated prompt options in the Copilot pane for the best results. The following sections describe what you can do with Copilot in Microsoft 365 admin centers.

> [!IMPORTANT]
> To maintain your security and privacy, Copilot doesn't make any configuration changes on your behalf. For more information, see [Data, privacy, and security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md).

### Search for users and groups

Search your users and groups based on natural language queries. Copilot returns a list where you can view the results in active users or group lists, and export them to a CSV file for further analysis.

Example prompts:

- *Show me users in Australia with Teams license assigned.*
- *Identify all groups in my organization without an owner.*
- *Identify all users who are unlicensed.*

### Mailbox search

Find insights about your users' mailboxes through natural language queries.

Example prompts:

- *Find all the mailboxes which are hidden from address lists.*
- *Show me all mailboxes put on litigation hold date before 13 August 2017.*

### Navigate admin center

Navigate to different pages, features, and experiences within the admin center. Copilot provides a breadcrumb trail and direct link to your desired page, and you can use a wayfinding query to be brought directly to that page with the Copilot chat pane still open.

Example prompts:

- *Where do I manage role assignments?*
- *Where can I see my meeting policies?*

### Get admin support

Get support for any challenges or questions related to administering Microsoft 365 for your tenant. Copilot can also give you an alert for a service incident ongoing for your organization if your question is relevant to that incident, along with a self-help insight. For certain issues, Copilot can give you diagnostic solutions that use the information and details you provide to help diagnose and solve your problems.

Example prompts:

- *How do I view my bill?*
- *How do I set up multifactor authentication?*
- *How do I restore a deleted user?*

### Discover Microsoft 365 products

Discover products to help take advantage of value from Microsoft 365. Copilot can help you find the right product to suit your needs. When applicable, you can initiate trials and purchases directly from the Copilot response.

Example prompts:

- *What is included in Business Premium?*
- *What is the price of Viva Goals?*
- *How do I get email?*

### Identity management

Use Copilot to guide you in managing various aspects of identity and security within your organization's ecosystem.

Example prompts:

- *How many hybrid users am I syncing?*
- *Which authentication methods do I have on?*
- *Perform a guest access review.*

### Device management

Copilot can help you locate resources to create mobile app protections policies. Get deployment guidance for setting up and managing various aspects of identity and security within the tenant.

Example prompts:

- *What is the status of my security defaults?*
- *What is the identity user status in my org?*

### Service health

Surface general status of Microsoft services, tenant health status, health advice, and recommendations.

Example prompts:

- *Are there any service issues right now?*
- *Show me health of teams.*

### Copilot guidance

Get Microsoft 365 Copilot guidance to help you with your Copilot onboarding and deployment journey with the help of guidance and insights.

Example prompts:

- *How do I give access to Copilot?*
- *See Copilot requirements for my organization.*
- *How many Copilot licenses have I assigned?*
- *Review Copilot user readiness.*

### Onboard users

Onboard users to your organization with one prompt. Copilot can help with adding a new user by using the information you provide in a prompt in combination with the data it has about the tenant (like domains and licenses). Copilot can seamlessly recommend a configuration for this new user, which saves time.

Example prompts:

- *Onboard John Smith as a new user to my organization.*

### Admin recap

Use admin recap to get a personalized and concise summary of key insights and trends across admin areas, such as Service Health, Message Center, Experience Insights, and more to save valuable time. Admin recap is personalized based on your role and usage patterns. You can copy the text for easier sharing and also personalize what shows in the recap.

Example prompts:

- *Recap the latest admin info for me.*

## Frequently asked questions

### How do I enable Copilot in Microsoft 365 admin centers?

Copilot is automatically enabled for select customers who purchased Microsoft 365 Copilot.

### How do I disable Copilot in Microsoft 365 admin centers?

If you would like to exclude certain admins from this feature, add them to a custom security group. Create a security group with the following name: `CopilotForM365AdminExclude`. You don't need to specify a description or configure other settings. Microsoft 365 admin centers disable the Copilot experience for any admin users in this group.

### Which admin roles can use Copilot in Microsoft 365 admin centers?

The feature is available to all admin users. It respects role-based access controls in the admin center and only shows information and controls that the user has access to. Copilot doesn't make any configuration changes on your behalf.

### Does Copilot in Microsoft 365 admin centers support audit logging?

Yes. Copilot in Microsoft 365 admin centers aligns with Microsoft's commitment to providing enterprise-grade compliance capabilities for all Copilot products. These capabilities include features such as auditing, eDiscovery, legal hold, and data retention controls.

### How much does Copilot in Microsoft 365 admin centers cost?

This feature is included in the Microsoft 365 Copilot license. When you purchase and assign Microsoft 365 Copilot licenses for your tenant, admin users with an assigned license can use Copilot in Microsoft 365 admin centers.
