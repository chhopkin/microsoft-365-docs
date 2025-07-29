---
title: "Account security"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: deniseb
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business-security
ms.date: 05/21/2025
ms.localizationpriority: medium
ms.collection:
- M365-Campaigns
- m365solution-smb
- highpri
- tier2
- trust-pod
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: "Learn how security defaults can help protect your organization from identity-related attacks by providing preconfigured security settings for Microsoft 365 Business Premium."
appliesto:
  - ✅ <a href="https://www.microsoft.com/microsoft-365/business/microsoft-365-business-basic" target="_blank">Microsoft 365 Business Basic</a>
  - ✅ <a href="https://www.microsoft.com/microsoft-365/business/microsoft-365-business-standard" target="_blank">Microsoft 365 Business Standard</a>
  - ✅ <a href="https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium" target="_blank">Microsoft 365 Business Premium</a>
  - ✅ <a href="https://m365forcampaigns.microsoft.com/" target="_blank">Microsoft 365 for Campaigns</a>
---

# Multifactor authentication in Microsoft 365 for business

User account security is critical in Microsoft 365 for business organizations, and multifactor authentication (MFA) makes it difficult for unauthorized users to sign in. When MFA is enabled, a user enters their account and password as usual, but then a supported app on their phone (for example, the Microsoft Authenticator app) verifies their identity before they can sign in and access resources.

Microsoft 365 for business organizations have the following options to enable MFA for users:

- **Security defaults**: Security defaults is a set of unmodifiable policies in all Microsoft 365 organizations via Microsoft Entra ID Free.

  Security defaults include the following security features:

  - Requiring all users and admins to register for Microsoft Entra multifactor authentication (MFA) using the [Microsoft Authenticator app](/entra/identity/authentication/concept-authentication-authenticator-app) or any third-party authentication app that supports [OATH TOTP](/entra/identity/authentication/concept-authentication-oath-tokens#oath-software-tokens).
  - Requiring MFA for admin accounts at every sign in.
  - Requiring MFA for users when necessary (for example, on new devices).
  - Blocking legacy authentication protocols (for example, POP3 and IMAP4 in old email clients).
  - Requiring MFA for users and admins accessing Azure Resource Manager services (for example, the Microsoft Azure portal).

  Security defaults is either on or off in an organization. Microsoft 365 for business organizations created after October 2019 have security defaults (hence, MFA) turned on by default, **so you don't need to do anything to enable security defaults or MFA in a new organization**. For most organizations, security defaults offer a good level of sign-in security.

  For more information about security defaults and the policies enforced, see [Enforced security policies in security defaults](/entra/fundamentals/security-defaults#enforced-security-policies).

- **Conditional Access policies in Microsoft 365 Business Premium**: In addition to security defaults, Business Premium includes Conditional Access policies via Microsoft Entra ID Plan 1.

  You create Conditional Access policies that react to sign-in events before a user is granted access to an application or service. If your organization has complex security requirements or you need granular control over security policies, you can use Conditional Access policies instead of security defaults.

  > [!TIP]
  > Organizations can use security defaults or Conditional Access policies, but not both at the same time. Conditional Access policies require security defaults to be turned off, so it's important to recreate the policies from security defaults in Conditional Access policies as a baseline for all users.

  For more information about Conditional Access policies, see [What is Conditional Access?](/entra/identity/conditional-access/overview).

The rest of this article explains how to manage security defaults and Conditional Access policies in Microsoft 365 for business.

> [!TIP]
> For user instructions to set up MFA on devices, see [Set up your Microsoft 365 sign-in for multifactor authentication](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14) and the following video:
>
> > [!VIDEO https://learn-video.azurefd.net/vod/player?id=b82831d1-4740-4466-ae55-94c335f87158]

## What do you need to know before you begin?

- You need to be assigned permissions before you can do the procedures in this article. You have the following options:
  - [Microsoft Entra permissions](/entra/identity/role-based-access-control/manage-roles-portal):
    - _Turn on or turn off security defaults_: Membership in the **Global Administrator**<sup>\*</sup> or **Security Administrator** roles.
    - _Create and manage Conditional Access policies_: Membership in the **Global Administrator**<sup>\*</sup> or **Conditional Access Administrator** roles.

    > [!IMPORTANT]
    > <sup>\*</sup> Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Manage security defaults

Microsoft 365 for business organizations created after October 2019 have security defaults turned on by default. To see or change the current status of security defaults in your organization, do the following steps:

1. In the Microsoft Entra admin center at <https://entra.microsoft.com>, go to **Identity** \> **Overview**. Or, to go directly to the overview page, use <https://entra.microsoft.com/#view/Microsoft_AAD_IAM/TenantOverview.ReactView>.
2. On the overview page, select the **Properties** tab, and the go to the **Security defaults** section at the bottom of the tab.

   Depending on the current status of security defaults, one of the following experiences is available:

   - **Security defaults is on**: The following text is shown and **Manage security defaults** is available:

     > Your organization is protected by security defaults.

   - **One or more Conditional Access policies are or were turned on in Business Premium**: The following text is shown and **Manage security defaults** isn't available:

     > Your organization is currently using Conditional Access policies which prevents you from enabling security defaults. You can use Conditional Access to configure custom policies that enable the same behavior provided by security defaults.

     **Manage Conditional Access** takes you to the **Policies** page at <https://entra.microsoft.com/#view/Microsoft_AAD_ConditionalAccess/PoliciesList.ReactView> to manage Conditional Access policies. To switch between security defaults and Conditional Access policies, see the [Revert to security defaults from Conditional Access policies](#revert-to-security-defaults-from-conditional-access-policies) section later in this article.

   - **Security defaults is off**: The following text is shown and **Manage security defaults** is available:

     > Your organization is not protected by security defaults.

3. If **Manage security defaults** is available, select it turn on or turn off security defaults:

   In the **Security defaults** flyout that opens, do one of the following steps:

   - **Turn on security defaults**: In the **Security defaults** dropdown list, select **Enabled**, and then select **Save**.
   - **Turn off security defaults**: In the **Security defaults** dropdown list, select **Disabled**. In the **Reason for disabling** section, select one **My organization is planning to use Conditional Access**.

     When you're finished in the **Security defaults** flyout, select **Save**

   > [!IMPORTANT]
   > We don't recommend turning off security defaults unless you're switching to Conditional Access policies in Business Premium.

## Manage Conditional Access policies in Microsoft 365 Business Premium

If your Business Premium organization has complex security requirements or you need more granular control over your security policies, you can use Conditional Access instead of security defaults for a higher security posture.

For more information, see [Plan a Conditional Access deployment](/entra/identity/conditional-access/plan-conditional-access).

Switching from security defaults to Conditional Access policies in Business Premium requires the following basic steps:

1. Turn off security defaults.
2. Create baseline Conditional Access policies to recreate the security policies in security defaults.
3. Adjust MFA exclusions.
4. Create other Conditional Access policies to meet your business needs.

> [!TIP]
> If security defaults is turned on, you can create new Conditional Access policies, but you can't turn them on. After you turn off security defaults, you can turn on the Conditional Access policies.

### Step 1: Turn off security defaults

Security defaults and Conditional Access policies can't be turned on at the same time, so the first thing you need to do is turn off security defaults.

For instructions, see the previous [Manage security defaults](#manage-security-defaults) section in this article.

### Step 2: Create baseline Conditional Access policies to recreate the policies in security defaults

The policies in security defaults are the Microsoft-recommended baseline for all organizations, so it's important to recreate these policies in Conditional Access before you create other Conditional Access policies.

The following templates in Conditional Access recreate the policies in security defaults:

- [Require MFA for all users](/entra/identity/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Require MFA for administrators](/entra/identity/conditional-access/policy-old-require-mfa-admin)<sup>\*</sup>
- [Block legacy authentication](/entra/identity/conditional-access/howto-conditional-access-policy-block-legacy)
- [Require MFA for Azure management](/entra/identity/conditional-access/howto-conditional-access-policy-azure-management)

<sup>\*</sup>You can improve your security posture by using [Require phishing-resistant MFA for administrators](/entra/identity/conditional-access/policy-admin-phish-resistant-mfa) instead.

To create Conditional Access policies using these templates, do the following steps:

1. In the Microsoft Entra admin center, go to the **Conditional Access | Policies** page at <https://entra.microsoft.com/#view/Microsoft_AAD_ConditionalAccess/ConditionalAccessBlade/~/Policies>.
2. On the **Conditional Access | Policies** page, select :::image type="icon"source="../../media/m365-cc-sc-create-icon.png" border="false"::: **New policy from template**.
3. On the **New policy from template** page, verify the **Select a template** tab is selected. On the **Select a template** tab, verify the **Secure foundation** tab is selected.
4. On the **Secure foundation** tab, select one of the required templates (for example, **Require multifactor authentication for all users**), and then select **Review + Create**.

   > [!TIP]
   > To find and select the **Require phishing-resistant multifactor authentication for admins** template, use the :::image type="icon"source="../../media/m365-cc-sc-search-icon.png" border="false"::: **Search** box.

5. On the **Review + Create** tab, view or configure the following settings:
   - **Basics** section:
     - **Policy name**: Accept the default name or customize it.
     - **Policy state**: Select **On**
   - **Assignments** section: In the **Users and groups** section, notice the **Excluded users** value is **Current user** and you can't change it. Only [emergency access accounts](/entra/identity/role-based-access-control/security-emergency-access) should be excluded from MFA requirements. For more information, see the next step.

   When you're finished on the **Review + Create** tab, select **Create**.

   The policy you created is shown on the **Conditional Access | Policies** page.

6. Repeat the previous steps for the remaining templates.

#### Step 3: Adjust MFA exclusions

By default, the Conditional Access policies you created in the previous step contains exclusions for the account you were signed in as, and you can't modify the exclusions during policy creation.

We recommend at least two admin [emergency access accounts](/entra/identity/role-based-access-control/security-emergency-access) in every organization that aren't assigned to specific individuals and are only used in emergencies. These accounts need to be excluded from MFA requirements.

You might need to remove the current account exclusions and/or add emergency access account exclusions to the following policies:

- [Require MFA for all users](/entra/identity/conditional-access/policy-all-users-mfa-strength#create-a-conditional-access-policy)
- [Require MFA for administrators](/entra/identity/conditional-access/policy-old-require-mfa-admin) or [Require phishing-resistant MFA for administrators](/entra/identity/conditional-access/policy-admin-phish-resistant-mfa#create-a-conditional-access-policy)
- [Require MFA for Azure management](/entra/identity/conditional-access/policy-old-require-mfa-azure-mgmt#create-a-conditional-access-policy)

Before you create custom Conditional Access policies, create your emergency access accounts and then use the following steps to adjust the exclusions for MFA-related policies:

1. On the **Conditional Access | Policies** page at <https://entra.microsoft.com/#view/Microsoft_AAD_ConditionalAccess/ConditionalAccessBlade/~/Policies>, select one of the MFA-related policies that you created in the previous step (for example, **Require multifactor authentication for Azure management**).
2. On the policy details page that opens, select **All users included and specific users excluded** in the **Assignments** \> **Users** section.
3. In the information that appears, select the **Exclude** tab.
4. On the **Exclude** tab, the following settings are configured:
   - **Select the users and groups to exempt from the policy**: The value **Users and groups** is selected.
   - **Select excluded users and groups**: The value **1 user** is shown, and the user account that was used to create the policy is shown.
     - To remove the current account from the excluded users list, select :::image type="icon"source="../../media/m365-cc-sc-more-actions-icon.png" border="false"::: \> :::image type="icon"source="../../media/m365-cc-sc-delete-icon.png" border="false"::: **Remove**.

       The value changes to **0 users and groups selected** and the warning text **Select at least one user or group** appears.

     - To add emergency access accounts to the excluded users list, select **0 users and groups selected**. In the **Select excluded users and groups** flyout that opens, find and select the emergency access accounts to exclude. The selected users are shown in the **Selected** pane. When you're finished, select **Select**.

       Back on the policy details page, select **Save**.

5. Repeat the previous steps for the remaining MFA-related policies.

> [!TIP]
> The [Block legacy authentication](/entra/identity/conditional-access/howto-conditional-access-policy-block-legacy) policy probably needs no exclusions, so you can use the previous steps to remove the existing exclusion. Just uncheck **Users and groups** in Step 4.
>
> For more information about user exclusions in Conditional Access policies, see [User exclusions](/entra/identity/conditional-access/plan-conditional-access#user-exclusions).

### Step 4: Create other Conditional Access policies to meet your business needs

Now you can create Conditional Access policies to meet your business needs. For more information, see [Plan a Conditional Access deployment](/entra/identity/conditional-access/plan-conditional-access).

### Revert to security defaults from Conditional Access policies

Security defaults is turned off when you're using Conditional Access policies. If one or more Conditional Access policies exist in any state (**Off**, **On**, or **Report only**), you can't turn on security defaults. You need to delete all existing Conditional Access policies before you can turn on security defaults.

> [!CAUTION]
> Before you delete any Conditional Access policies, be sure to record their settings.

To delete Conditional Access policies, use the following steps:

1. On the **Conditional Access | Policies** page at <https://entra.microsoft.com/#view/Microsoft_AAD_ConditionalAccess/ConditionalAccessBlade/~/Policies>, select the policy that you want to delete.
2. In the details page that opens, select :::image type="icon"source="../../media/m365-cc-sc-delete-icon.png" border="false"::: **Delete** at the top of the page.
3. In the **Are you sure?** dialog that opens, select **Yes**.

After you delete all Conditional Access policies, you can turn on security defaults as described in [Manage security defaults](#manage-security-defaults).
