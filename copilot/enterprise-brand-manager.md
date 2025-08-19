---
title: Enterprise brand manager policy and organizational asset library (OAL) access
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 05/30/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- Tier2
- scotvorg
- M365-subscription-management 
- Adm_O365
- Adm_TOC
- m365copilot
- magic-ai-copilot
description: "Learn about enabling brand kits and asset libraries in the Microsoft 365 Copilot app to streamline on-brand content creation."
---

# Enterprise brand manager policy and organizational asset library (OAL) access

Your organization can enable their brand managers to set up and publish organization or official brand kits via [create.microsoft.com](https://create.microsoft.com). These brand kits can contain multiple logos, color palettes, fonts, images, and templates pertaining to a certain brand.

Once published, the brand kit is available to all users in the organization on create.microsoft.com. They can use these brand kits to generate branded artifacts or manually add brand content to existing designs and images.

To enable this functionality, admins must configure the Enterprise Brand Manager policy, which involves:

- Defining a security group that includes the brand managers.
- Assigning responsibility to these brand managers for creating, managing, and publishing the official or organizational brand kits.

Beyond brand kits, Copilot also supports access to an organization’s designated [organizational asset library (OAL)](/sharepoint/organization-assets-library). OALs provide broad, centralized access to brand content and support images, logos and illustrations. OALs need to be configured as searchable by an admin.

## Configure Enterprise Brand Manager policy

Use the following instructions to configure Enterprise Brand Mangager. 

**Prerequisite** Create a mail-enabled security group with identified brand managers who have access and permission to create, publish, and manage brand kits available to all users within the organization.

**Policy setup** Follow these steps to create and enable the Enterprise Brand Manager policy for your organization:

1. Navigate to [Config.office.com](https://config.office.com/) and sign in using an Administrator account.
1. Under Customization, select **Policy Management**.
1. Select your existing tenant level policy with scope set to **Apply to all users** or create a new tenant policy with scope set to **Apply to all users**.
1. Go to the **Policies** tab.
1. Use the search box to search for **Brand Manager**. Select the **Elevated role for Brand Managers** policy.

    :::image type="content" source="media/brand-manager/brand-manager-policy.png" alt-text="Screenshot showing the Policy Management page to configure settings." lightbox="media/brand-manager/brand-manager-policy.png":::

6. Set the policy to **Enabled**. By default, it's set as **Not configured**.
7. In the Security group email address field, provide the email address for the brand managers security group for your tenant.

    :::image type="content" source="media/brand-manager/brand-manager-role.png" alt-text="Screenshot showing the Security group email text box filled with an email." lightbox="media/brand-manager/brand-manager-role.png":::

8. Select **Apply**.

> [!NOTE]
> It could take up to 24 hours after a policy is created for brand managers to be able to create and edit and official brand kits.

## Related content

- [Create an organizational asset library (OAL) in the Microsoft 365 Copilot app](enterprise-brand-manager-policy.md)