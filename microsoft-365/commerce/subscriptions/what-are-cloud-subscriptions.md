---
title: "What are cloud subscriptions?"
f1.keywords: CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, jobailey
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-business
ms.subservice: m365-commerce-acquisition
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminTemplateSet
- admindeeplinkMAC
- campaignIDs-batch1
service.tree.id: 84a24b9c-ce0c-4b4b-b837-45bc5ee4bef0
search.appverid: MET150
robots: NOINDEX, NOFOLLOW
description: "Learn about cloud subscriptions and how to view them in the Microsoft 365 admin center."
ms.date: 02/05/2026
---

# What are cloud subscriptions?

A cloud subscription (also called an *Azure subscription*) is a way to manage the products and services that you buy from Microsoft. A cloud subscription is automatically created when you acquire Azure resources like Virtual Machines, or Enterprise Support and when you get some non-Azure services like Microsoft 365, Microsoft Dynamics 365, and the Microsoft Power Platform. You can view your cloud subscriptions through either the <a href="https://portal.azure.com/#view/Microsoft_Azure_Billing/SubscriptionsBladeV2" target="_blank">Azure portal</a> or the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, but you can only manage the subscriptions in the Azure portal.

Cloud subscriptions are different from standard subscriptions in the following ways:

- **No cost for cloud subscriptions**: A cloud subscription doesn’t cost any money. They're used to help you organize and manage the things that you buy. While individual products like calling features and perpetual software managed within a cloud subscription might incur charges, the subscription itself doesn't.
- **Multiple subscriptions**: You can create multiple cloud subscriptions to delegate management to different users in your organization or to apply policies for security, budgeting, and compliance.
- **Familiar management tools in the Azure portal**: If you use other Azure subscriptions, you can manage cloud subscriptions similarly, with more manageability for a broader set of products and services.

## Before you begin

- You must be a Global or Billing Administrator to view your cloud subscriptions in the Microsoft 365 admin center. For more information, see [About admin roles in the Microsoft 365 admin center](../../admin/add-users/about-admin-roles.md). 
- To manage your cloud subscriptions, you must have the Global Administrator role in the Azure portal.

[!INCLUDE [ga-roles-limitation](../../includes/ga-roles-limitation.md)]

## Find your cloud subscription

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page and select the **Cloud Subscriptions** tab.
2. Select a subscription name to view the details for that cloud subscription. The details page contains information about costs, billing settings, roles and access, and products included in the cloud subscription.
3. To manage the subscription, at the top of the page, select **Manage this usage-based subscription and its resources in the Azure portal**.

## Manage your cloud subscriptions

You can use cloud subscriptions to manage the products and services that you buy from us. You can view your list of cloud subscriptions and other details in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>. From there, you can link to the <a href="https://portal.azure.com/#view/Microsoft_Azure_Billing/SubscriptionsBladeV2" target="_blank">Azure portal</a> where you can manage the cloud subscriptions for your organization. For information about common cloud subscription tasks, see the following articles:

## Frequently asked questions (FAQs)

Here are some common questions and answers about cloud subscriptions.

### Why is Microsoft creating cloud subscriptions?

Cloud subscriptions are synonymous with Azure subscriptions. Microsoft is expanding the role of cloud subscriptions to provide a consistent platform management story across all products and services that can be acquired commercially from Microsoft.

### Where can I find my cloud subscription?

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page and select the **Cloud Subscriptions** tab.
1. Select a subscription name to view the details for that cloud subscription. The details page contains information about costs, billing settings, roles and access, and products included in the cloud subscription.
1. To manage the subscription, at the top of the page, select **Manage this usage-based subscription and its resources in the Azure portal**.

### Do I get charged for creating and using cloud subscriptions?

No. Cloud subscriptions don't incur charges, only the resources within. Cloud subscriptions are created and used to manage the products and services that you buy.

### How do I manage cloud subscriptions?

To see your cloud subscriptions, navigate to your list of subscriptions in the <a href="https://portal.azure.com/#view/Microsoft_Azure_Billing/SubscriptionsBladeV2" target="_blank">Azure portal</a>, or select the link **Manage this usage-based subscription and its resources in the Azure portal**. on the details page of any cloud subscription. From there, you can manage your subscriptions using the Azure tools and services you’re already familiar with.

### Who has access to the cloud subscription?

Cloud subscriptions are created either in an acquisition process like proposal acceptance or are created as Azure subscriptions today. Like Azure subscriptions, cloud subscriptions owners are the individuals who create the subscription or anyone they [delegate management](/azure/lighthouse/how-to/view-manage-customers#view-and-manage-delegations) to. If the subscription was created during proposal acceptance, the purchaser is the subscription owner. You can use the **Identity and Access Management** (IAM) page for an individual cloud subscription to view and manage access.

### What is the impact of cloud subscriptions?

A cloud subscription is a management container that allows customers to manage the products and services they acquire from Microsoft commercially. You can use cloud subscriptions to do the following:

- [Delegate management](/azure/lighthouse/how-to/view-manage-customers#view-and-manage-delegations) of the resources they contain to different teams or individuals

- [Manage policies and controls for security and compliance](/azure/governance/policy/tutorials/create-and-manage.md)

- [Track budget and spend](/azure/cost-management-billing/costs/tutorial-acm-create-budgets.md)

- Perform [other management activities](/azure/cost-management-billing/manage/manage-azure-subscription-policy.md) available to existing Azure subscriptions.

If a specific resource doesn't support a particular manage action (for example, self-service cancellation or transfer between different scopes like billing accounts or tenants) that operation is blocked at the subscription level until that resource is moved or removed.

### Can cloud subscriptions be canceled?

Yes. Cloud subscriptions can be canceled as long as all resources contained in the cloud subscription and its resource groups allow self-service cancellation. If a particular resource like the Microsoft Azure Consumption Commitment (MACC) doesn't support self-service cancellation, it blocks the cancellation and deletion of the subscription until it's moved or removed. Resources that don't allow self-service cancellation frequently have unique requirements to enable cancellation. Check product documentation for resources requiring special cancellation handling for more specific instructions.

### Can I choose not to use cloud subscriptions?

No. Cloud subscriptions are a requirement for the product and service resources that use them and provide important management capabilities those resources and resource providers rely on. Any product and service that requires cloud subscriptions isn't available without their dependent cloud subscription container.

### Why do I see so many cloud subscriptions?

Cloud subscriptions are created when someone creates a cloud subscription directly or when someone makes a purchase that requires a cloud subscription. In some cases, cloud subscriptions are created and named by the person creating them, while in other cases they're named automatically and created as part of the purchase process. You can view all the cloud subscriptions in the **Cloud Subscriptions** tab of the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.

## Related content

[What is a cloud subscription? (Azure)](/azure/cost-management-billing/manage/cloud-subscription) (article)
