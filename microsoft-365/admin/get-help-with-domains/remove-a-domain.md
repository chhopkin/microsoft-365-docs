---
title: Remove a Domain from Microsoft 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 02/19/2026
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: m365-domains
ms.localizationpriority: medium
ms.collection:
  - Tier2
  - scotvorg
  - M365-subscription-management
  - Adm_O365
  - Adm_TOC
  - Adm_O365_Setup
  - operations-pod
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Learn how to remove a domain from Microsoft 365. Follow these steps to move users and groups to another domain, update DNS records, and complete the process.
#customer intent: As an IT admin, I want to remove a domain from Microsoft 365 so that I can reuse it in another tenant, switch subscription plans, or safely decommission the domain.
---

# Remove a domain from Microsoft 365

You can remove a domain from Microsoft 365 when you want to [add it to a different subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md), transfer users to another domain, or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).

## Before you begin

Before you remove a domain, make sure that:

- The domain isn't set as the default domain.
- No users, shared mailboxes, resource mailboxes, or contacts use the domain.
- No Microsoft 365 groups, distribution lists, or Teams use the domain.
- The domain isn't used for sign-in by any admin accounts.
- You understand how email flow changes if the domain has MX records pointing to Microsoft 365.

## Step 1: Move users to another domain

### Move users

::: moniker range="o365-worldwide"

1. Sign in to the [Microsoft 365 admin center](https://admin.cloud.microsoft/).

::: moniker-end

::: moniker range="o365-21vianet"

1. Sign in to the [Microsoft 365 admin center](https://portal.partner.microsoftonline.cn/adminportal/).

::: moniker-end

1. Select **Users** > **Active users**.

1. Select the check boxes next to the names of all the users you want to move.

1. At the top of the page, select **Change domains**.

1. In the **Change domains** pane, select a different domain.

You need to do this step for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, sign out and sign back in by using the new domain you chose to continue.

### Move yourself

> [!IMPORTANT]
>
> If you're the only Global Administrator using this domain, make sure at least one other Global Administrator exists on a different domain before you change your username.

::: moniker range="o365-worldwide"

1. Sign in to the [Microsoft 365 admin center](https://admin.cloud.microsoft/).

::: moniker-end

::: moniker range="o365-21vianet"

1. Sign in to the [Microsoft 365 admin center](https://portal.partner.microsoftonline.cn/adminportal/).

::: moniker-end

1. In the left navigation bar, select **Users** > **Active Users**.

1. In the **Active users** page, select your account from the list.

1. On the **Account** tab of the account details pane, select **Manage username**.

1. In the **Manage username** pane, choose a different domain, and then select **Save Changes**.

1. At the upper right, select your account name, and then select **Sign Out**.

1. Sign in by using the new domain and your same password.

You can also use PowerShell to move users to another domain. For more information, see [Update-MgUser](/powershell/module/microsoft.graph.users/update-mguser). To set the default domain, use [Update-MgDomain](/powershell/module/microsoft.graph.identity.directorymanagement/update-mgdomain).

## Step 2: Move groups to another domain

> [!NOTE]
>
> Moving groups to another domain includes Microsoft 365 groups, Teams-connected groups, and distribution lists that have email addresses using the domain.

::: moniker range="o365-worldwide"

1. Sign in to the [Microsoft 365 admin center](https://admin.cloud.microsoft/).

::: moniker-end

::: moniker range="o365-21vianet"

1. Sign in to the [Microsoft 365 admin center](https://portal.partner.microsoftonline.cn/adminportal/).

::: moniker-end

1. In the left hand navigation pane, select **Teams & groups** to expand it, and then select **Active teams & groups**.

1. In the **Active teams and groups** page, make sure **Teams & Microsoft 365 groups** is selected, and then select a group.

1. In the group properties pane, make sure the **General** tab is selected.

1. Under **Aliases** in the **Email addresses** column, select **Edit**.

1. Under **Primary email address** in the **Edit email addresses** pane, select the pencil icon.

1. Use the drop-down list to select a different domain and then select **Done**.

1. In the **Edit email addresses** pane, select **Save**, and then close the **Edit email addresses** pane using the **X** in the upper right corner.

1. Repeat these steps for any groups or distribution lists associated with the domain that you want to remove.

## Step 3: Remove the old domain

::: moniker range="o365-worldwide"

> [!IMPORTANT]
>
> If you're removing a custom domain, complete the steps in [Remove a custom domain](#remove-a-custom-domain) before continuing.

1. Sign in to the [Microsoft 365 admin center](https://admin.cloud.microsoft/).

::: moniker-end

::: moniker range="o365-21vianet"

1. Sign in to the [Microsoft 365 admin center](https://portal.partner.microsoftonline.cn/adminportal/).

::: moniker-end

1. From the left navigation bar, select **… Show all**, and then select **Settings** > **Domains**.

1. In the **Domains** page, select the domain that you want to remove.

1. In the domain properties pane, select **Remove domain**.

1. In the **Remove domain?** pane, select **Remove domain**.

## Remove a custom domain

If you're canceling your subscription and are using a custom domain, a few extra steps need to be taken before canceling your subscription.

To remove a custom domain to Microsoft 365, select the tab based on if:

- **Microsoft 365 managed** - Microsoft 365 is currently managing your DNS records. Select this option even if you plan to move your DNS records to a new NS provider before canceling your subscription.
- **Non-Microsoft managed** - Your DNS records are managed at a non-Microsoft NS provider.

### [:::image type="icon" source="../../media/icons/microsoftsymbol-18.svg"::: **Microsoft 365 managed**](#tab/microsoft-365-managed)

If your domain currently points to Microsoft 365 nameservers (NS), the following steps are required to properly move the domain to new NS and service providers:

- Update your DNS records at both Microsoft 365 and your new NS provider to point to your new provider's services. For example, point your MX record to your new email provider at both Microsoft 365 and your new NS provider. For more information on changing your DNS records at Microsoft 365, see [Change DNS records to set up Microsoft 365 with any domain registrar](../setup/add-domain.md). For more information on changing your DNS records at your new NS provider, see your new NS provider's documentation.

- Once the DNS records are updated at both Microsoft 365 and your new NS provider, change your NS records at your registrar to point to your new NS provider instead of Microsoft 365. For more information, see [Add a custom domain to Microsoft 365](../../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).

    > [!TIP]
    >
    > You can also update your DNS records at your new NS provider first before moving your NS records. On the day you want to move your NS records, update your DNS records at Microsoft 365 to point to your new provider and then change your NS records to point to your new NS provider.

- Notify your users of the date you plan to switch them to their new service provider along with the new service provider's name. For example, notify your users that their email is being moved to a new email provider. Although the switch usually happens seamlessly, it's a good idea to let your users know about the change.

- On the day you change the NS and DNS records:

  - Make sure to save user data that is in Microsoft 365. For more information, see [Save your data](../../commerce/subscriptions/cancel-your-subscription.md#save-your-data).
  - If needed, uninstall Microsoft 365 from user's devices. For more information, see [Uninstall Microsoft 365](../../commerce/subscriptions/cancel-your-subscription.md#uninstall-microsoft-365-optional).

### [:::image type="icon" source="../../media/icons/software-18.svg"::: **Non-Microsoft managed**](#tab/non-microsoft-managed)

If your domain currently points to non-Microsoft nameservers (NS), the following steps are required to properly move the domain to a new service provider:

- Update your DNS records at your NS provider to point to your new provider's services. For example, point your MX record to your new email provider at your new NS provider. For information on changing your DNS records at your NS provider, see your new NS provider's documentation.

- Notify your users of the date you plan to switch them to their new service provider along with the new service provider's name. For example, notify your users that their email is being moved to a new email provider. Although the switch usually happens seamlessly, it's a good idea to let your users know about the change.

- On the day you change the DNS records:

  - Make sure to save user data that is in Microsoft 365. For more information, see [Save your data](../../commerce/subscriptions/cancel-your-subscription.md#save-your-data).
  - If needed, uninstall Microsoft 365 from user's devices. For more information, see [Uninstall Microsoft 365](../../commerce/subscriptions/cancel-your-subscription.md#uninstall-microsoft-365-optional).

---

## How long does it take for a domain to be removed?

It can take as little as five minutes for Microsoft 365 to remove a domain if the domain isn't referenced in many places such as:

- Security groups.
- Distribution lists.
- Users.
- Aliases.
- Shared mailboxes.
- Resource mailboxes.
- Microsoft 365 groups.

If many references use the domain, it can take several hours up to a day for the domain to be removed.

> [!TIP]
>
If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for some users to be missed via the UI. If not all users are properly moved, when you go to remove the domain, you can't remove the domain. For more information:
>
> - Query users and move to another domain: [Update-MgUser](/powershell/module/microsoft.graph.users/update-mguser).
> - Set the default domain: [Update-MgDomain](/powershell/module/microsoft.graph.identity.directorymanagement/update-mgdomain).

## Still need help?

[!INCLUDE [How to get tech support for SMB](../../includes/smb-how-to-get-tech-support.md)]

[**Check the Domains FAQ**](../setup/domains-faq.yml) if you don't find what you're looking for.

::: moniker range="o365-worldwide"

> [!NOTE]
>
> You can't remove [**.onmicrosoft.com**](../setup/domains-faq.yml) domains from your account. When you remove a domain, user accounts revert to the default **.onmicrosoft.com** address as the primary SMTP/UserprincipalName.

If the process isn't working, you might need to manually remove your domain. For assistance with manually removing your domain, [contact support](../../business-video/get-help-support.md).

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
>
> You can't remove [**.partner.onmschina.cn**](../setup/domains-faq.yml) domains from your account. When you remove a domain, user accounts revert to the default **.partner.onmschina.cn** address as the primary SMTP/UserprincipalName.

If the process isn't working, you might need to manually remove your domain. For assistance with manually removing your domain, [contact support](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true).

::: moniker-end

## Related content

- [Domains FAQ](../setup/domains-faq.yml).
- [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).
- [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).
