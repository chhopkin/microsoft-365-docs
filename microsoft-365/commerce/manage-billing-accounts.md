---
title: Understand your Microsoft business billing account
f1.keywords:
- MACBillingBillingAccountsOverview
author: cmcatee-MSFT
ms.author: cmcatee
manager: dansimp
ms.reviewer: jkinma, ramagane
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: m365-commerce-management
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
- operations-pod
ms.custom:
- commerce_billing
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
- GAUpdates
- campaignIDs-batch2
search.appverid: MET150
description: "Learn about Microsoft business billing accounts and how they're used to manage account settings, invoices, payment methods, and purchases."
ms.date: 09/15/2025
---

# Understand your Microsoft business billing account

When you sign up to try or buy Microsoft business products, a billing account is automatically created for you. You use your billing account to manage your account settings, invoices, payment methods, and purchases from us.

You might have access to multiple billing accounts. For example, you can have one billing account when you buy directly from Microsoft, and another when you have access to your organization's billing account.

## Before you begin

- [Determine what type of billing account you have](#view-my-billing-accounts).
- If you have a Microsoft Customer Agreement (MCA) or Microsoft Partner Agreement (MPA) billing account type, you must be a Billing account reader to do the tasks in this article. For more information, see [What are billing account roles?](#what-are-billing-account-roles)
- If you have a Microsoft Online Subscription Agreement (MOSA) billing account type, you must be at least a Billing Administrator to do the tasks in this article. For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).

## What are the types of billing accounts?

The <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Billing accounts</a> page in the Microsoft 365 admin center provides a view of your business accounts with Microsoft. The following types of billing accounts are supported:

- **Microsoft Customer Agreement (MCA)**: This billing account is created when your organization works with a Microsoft representative, an authorized partner, or buys products and services independently. For MCA billing accounts, you have a corresponding billing profile that contains your subscriptions.
- **Microsoft Partner Agreement (MPA):** This billing account is created for Cloud Solution Provider (CSP) partners to manage their customers.
- **Microsoft Online Subscription Agreement (MOSA)**: This billing account was created when you signed up for a Microsoft 365 subscription directly. You might have a MOSA billing account if your account hasn't yet moved to the Microsoft Customer Agreement. For MOSA billing accounts, you receive an invoice for each order, on the account anniversary.

## View my billing accounts

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.
1. Select the **Navigation menu**, then select **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Billing accounts</a>.
1. The **Billing accounts** page lists the billing accounts associated with your organization.
1. The **Billing account type** column indicates what type of agreement you signed with Microsoft for each billing account. Select a billing account name to view its details page.

## Select a default billing account

If you have more than one billing account, you can use the billing account selector to set a default billing account. When you set a default billing account, we use that account as the first choice for all your billing and purchasing activities. You can change your default billing account at any time.

1. Go to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339%22%22).
1. Select the **Navigation menu**, then select **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a>.
1. On the **Invoices** tab, select **Change billing account**.
1. Select a billing account from the list, then select **Set as default**.

You can also change your default billing account from the **Your products** page. 

1. In the admin center, select the **Navigation menu**, then select **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a>.
1. Select **Change billing account**.
1. Select a billing account from the list, then select **Set as default**.

## Understand the billing account details page

The top of the billing account details page contains your account profile and shows the legal and tax information about your organization. You can update your profile to change your legal address and phone number. This account is the legal entity that pays for the products that you buy from Microsoft.

The following table lists the terms shown on the billing account details page.

|Field name                       |Description                                     |
|---------------------------------|------------------------------------------------|
|Billing account ID                               |The unique identifier for your billing account. |
|Name                             |The name of your billing account. To change the name, select **Update name**. |
|Status                   |A read-only field that specifies the status of your commercial account with Microsoft. |
|My current role|The role you have on this billing account. See the [What are billing account roles?](#what-are-billing-account-roles) section later in this article.|
|Sold-to address                          |The details of the legal entity responsible for payment and identified on the invoice. This section contains the name and address of the individual or organization responsible for the account, together with a contact email address and phone number. The address provided here is used to determine your tax rate unless you opt to provide an alternative shipping address during your purchase. For more information, see [Tax information](billing-and-payments/tax-information.md). |
|Tax ID                           |This field only applies if you're in a country/region that requires you to provide a VAT or local equivalent. For more information, see [Tax information](billing-and-payments/tax-information.md). |
|Registration number (Optional)   |A legal registration number that you provide to us so we can review the details of your account. For more information, see [About registration numbers and under-review notifications](about-registration-numbers.md). To add a registration number, select **Edit**. |
|Type|The type of billing account.|
|Agreements|Links to the agreements signed by your organization with Microsoft. Not all agreements are available to view online.|

> [!NOTE]
> If you need to change the **Sold-to** name, you must [contact support](../admin/get-help-support.md) to change it. Requests to change the **Sold-to** name require a credit check. Complete [this form](https://www.microsoft.com/download/details.aspx?id=102732), and be ready to share one of the following documents with Microsoft when you contact support:
>
> - Government-issued document or registration letter
> - Print out of the local company's registry
>
> Support can help with name and address changes where only the customer name changes, but the entity remains the same. Any documentation you provide should clearly show that only the entity's name changed. If the change is the result of a transaction, including the sale of a business, a change of controls, or a divestiture or “spin-off” of a Customer Affiliate, contact your Microsoft Seller or Microsoft support.

## What are billing account roles?

If you have an MCA billing account type, the top of the billing account details page includes a **Billing account roles** tab. This section lists the names of the users and admin center roles assigned to specific billing account roles. Billing account roles are specific to billing accounts and provide different levels of access to the billing account for your organization.

> [!IMPORTANT]
> Billing account roles only apply to billing accounts, and don't apply to other Microsoft 365 admin center scenarios.

If you're a Global Administrator, you can assign yourself a Billing account role in the Microsoft 365 admin center through the billing account roles and permissions. Elevating your access to manage billing accounts gives you the ability to view and manage cost and billing for your accounts. You can view invoices, charges, products that are purchased, and the users who have access to the billing accounts.

You can provide others with access to the billing account in the Microsoft 365 admin center through the billing account roles and permissions. For instructions about how to grant billing account access to other users, see [Assign billing account roles](#assign-billing-account-roles).

Only a billing account owner can grant access to a billing account. You can assign the following roles to users:

|Role                           |Description                                                          |
|-------------------------------|---------------------------------------------------------------------|
|Billing account owner          |Can assign roles, edit accounts, sign agreements, and view accounts. |
|Billing account contributor    |Can edit accounts, sign agreements, and view accounts. |
|Billing account reader         |Can view accounts. |

## Assign billing account roles

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.
2. Select the **Navigation menu**, then select **Billing** > **Billing accounts**.
3. On the <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Billing accounts</a> page, select the billing account.
4. Under **Billing account roles**, select **Assign roles**.
5. In the **Assign roles** pane, type the name or email address, select the role you want to assign to them, then select **Assign**.

## View related role assignments

You can view the roles assigned to users for a billing account and related billing profiles across associated tenants.

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.
2. Select the **Navigation menu**, then select **Billing** > **Billing accounts**.
3. On the <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Billing accounts</a> page, select a billing account.
1. Under **Billing account roles**, select **View related role assignments**.

To export the information shown in the **Related billing role assignments** pane, select **Export to CSV**.

## What are associated billing tenants?

If you have an MCA billing account type, you can give users from other tenants access to collaborate on a single set of resources across all products. For more information about associated billing tenants and how to add and assign roles to them, see [Manage billing across multiple tenants in the Microsoft 365 admin center](billing-and-payments/manage-multi-tenant-billing.md).

## Keep your billing account active

If a billing account is unused for a certain amount of time, it's classified as *inactive*. An inactive billing account can increase potential security risks to that account and the resources it contains. To reduce this risk, Microsoft takes measures to secure, protect, and ultimately delete inactive billing accounts, tenants, and subscriptions within them.

This section applies to the following agreements:

- Microsoft Customer Agreement (MCA)
- Microsoft Online Subscription Agreement (MOSA)
- Cloud Solution Provider (CSP)
- Enrollment for Education Solutions (EES)

### What is an inactive billing account?

A billing account is considered inactive when the following criteria are met in a minimum of a 12-month period:

- No usage within the billing account, tenant, or subscription
- No sign-in activity within the billing account, tenant, or subscription
- No open or pending support requests

When a billing account meets all these criteria, you receive a notification from Microsoft that says that your inactive billing account will be blocked in 30 days.

> [!IMPORTANT]
> If your billing account remains inactive for 30 days after the notification, we block it. 

### How do I keep my billing account active?

If you use your billing account within 30 days of receiving the notification, your account returns to its active state and is no longer subject to getting blocked. The following list includes examples of activities and account usage that keep your billing account active:

- Using a product or a service
- Generating metered usage
- Creating a support ticket

### What happens if my billing account is blocked?

When your billing account is blocked, you can no longer perform certain actions, like adding new subscriptions and transferring existing subscriptions. To unblock your billing account and return it to its active state, use the following criteria to contact support for help:

- If you bought your subscription directly from Microsoft, [contact Microsoft Support](../admin/get-help-support.md).
- If you're a Partner or Enterprise customer, contact your partner or account manager.

**If you have a billing account with a prepaid subscription set to auto-renew:** After your billing account is blocked, if no action is taken, you receive a notification of tenant deauthorization. This step can be avoided or reversed within the allowed timeframe specified in the notification. Subscription usage isn't affected until a lifecycle management event occurs, like when a payment method expires. At that time, subscriptions might expire and be deleted, followed by billing account expiration and deletion.

**All other customers:** After your billing account is blocked, if no action is taken, subscription suspension, tenant deauthorization, and account termination might occur. Before each step is implemented, you receive a notification that contains the details and timeframe for that specific step. Each step can be avoided or reversed within the allowed time by contacting the support channels listed in this section.

> [!WARNING]
> You can avoid account termination, but after it occurs, it's not reversible. If no action is taken within the notification period, your billing account is terminated, and any data and resources associated with the billing account are permanently deleted and can't be recovered.

## Related content

[Tax information](billing-and-payments/tax-information.md) (article) \
[Manage your Microsoft business billing profiles](billing-and-payments/manage-billing-profiles.md) (article) \
[Get support for Microsoft 365 for business](../admin/get-help-support.md) (article)
