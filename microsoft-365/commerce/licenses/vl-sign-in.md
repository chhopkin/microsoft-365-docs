---
title: "Sign in to the Microsoft 365 admin center (volume licensing)"
f1.keywords: NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: aasthatiwari, atuldubey
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: m365-commerce-volume-licensing
ms.collection:
- Tier1
- scotvorg
ms.custom:
- commerce_vl
- AdminTemplateSet
service.tree.id: e6e1ea2a-04a0-4f78-bc75-7d45c90eee39
search.appverid: MET150
ms.localizationpriority: medium
description: "Learn how to sign in to the Microsoft 365 admin center for volume licensing products."
ms.date: 11/13/2025
---

# Sign in to the Microsoft 365 admin center (volume licensing)  

Customers can view and manage their Microsoft volume licensing (VL) agreements within a dedicated section of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> available only to authorized VL users.

## Before you begin

You must have a VL role to access the VL pages in the Microsoft 365 admin center.  

VL roles are assigned by one of the following people:

- A partner or seller who assigns you a role during the contract creation process.
- An administrator of the VL agreement who adds you as a user and invites you to sign in to register. If you have an Enterprise Agreement (EA) or Enterprise subscription (EU), you don't receive an invitation to sign in to register. Instead, the administrator of the VL agreement grants you access.

> [!NOTE]
> Global Administrators in the admin center don't have access to VL features. It's up to the VL agreement administrator to add any users, including Global Administrators, who might want access to specific license IDs. For more information, see [Commonly used Microsoft 365 admin center roles](../../admin/add-users/about-admin-roles.md#commonly-used-microsoft-365-admin-center-roles), and [Volume licensing roles](../../admin/add-users/about-admin-roles.md#volume-licensing-roles).

## Where to sign in to view and manage your volume licenses

To view your volume licenses and access software downloads and VL keys, you must sign in to one of the following locations:

- Commercial users and Government Community Cloud (GCC) users can sign in to the public cloud instance of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.
- Government Community Cloud High VL users can go to the <a href="https://portal.office365.us/adminportal/home" target="_blank">GCC High Microsoft 365 admin center</a>.
- US Department of Defence cloud VL users can go to the <a href="https://portal.apps.mil/adminportal/home" target="_blank">DoD Microsoft 365 admin center</a>.

> [!NOTE]
> Users who access both public clouds and GCC High clouds must have a separate ID for the GCC High Microsoft 365 admin center. If you're an EA or EU customer, any user with an Entra ID on a different cloud than the contract loses access to the contract. Users with an Entra ID on the same cloud as the contract continue to have uninterrupted access.

You can only access the VL contracts that are on the same cloud as your Entra ID. If you access VL contracts with Government Community Cloud High (GCC High) or US Department of Defence cloud (DoD) licenses, you must use the Entra ID in those clouds to access VL pages in the Microsoft 365 admin center.

Public and GCC users can’t access VL contracts with GCC High or DoD cloud licenses. Similarly, GCC High or DoD users can’t access VL contracts with public or GCC cloud licenses.

For example, Sarah from Contoso wants to manage VL licenses from both the public cloud and the GCC High cloud across multiple VL contracts. Sarah must have a separate Entra ID for both the public and GCC High clouds to manage VL licenses from each cloud. If she doesn't have an Entra ID for either cloud, then she must contact the respective Entra tenant admins or [Sign up for a new Microsoft Entra ID](#sign-up-for-a-new-microsoft-entra-id).

An Online Administrator of VL contracts from the public cloud can assign roles only to Sarah's public cloud Entra ID, while a GCC High cloud VL admin can assign roles exclusively to GCC High cloud Entra IDs.

To manage public cloud VL Contracts, Sarah must go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">public cloud instance of the Microsoft 365 admin center</a>. To manage GCC High cloud VL Contracts, she must go to the <a href="https://portal.office365.us/adminportal/home" target="_blank">GCC High cloud instance of the Microsoft 365 admin center</a>.

### If you're registering a volume license agreement for the first time (non-EA and non-EU customers only)

The first time that you register a VL agreement, use the following steps:

1. Locate the welcome email from "microsoft-noreply\@microsoft.com" with the subject line "Action required: Sign in to manage your volume licensing assets."
2. In the welcome email, select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">use your work or school account</a> link to sign in with your Microsoft Entra ID (previously called a work or school account). If you already use a Microsoft online service, you already have a Microsoft Entra ID. Try signing in with the same account that you use to access that service.

    > [!TIP]
    > Users with existing VL permissions, or who manage online services, should use the sign in with the same ID so that all their licensing contracts and online services are accessed with one ID.

3. Go to the business email mentioned in the welcome email and find an email with the subject line "Registration successful: Welcome to Microsoft admin center."
4. Select **Get Started** to go to Microsoft 365 admin center.
5. Go to the **Billing** > **Your products** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2244144" target="_blank">Volume licensing</a> tab.

> [!NOTE]
> We highly recommend that you select **Role Assignments** and immediately add another VL Administrator for each contract ID.

### If you're registering a VL agreement for the first time (EA and EU customers only)

1. Locate the notification email from microsoft-noreply\@microsoft.com with the subject Line "Permission changes for Microsoft Volume Licensing contracts."
2. In the email, select the Microsoft 365 admin center link to sign in with your Microsoft Entra ID or sign-in email address (previously called a work or school account). If you already use a Microsoft online service, you already have a Microsoft Entra ID. Try signing in with the same account that you use to access that service.

   > [!TIP]
   > Users with existing VL permissions, or who manage online services, should use the sign in with the same ID so that all their licensing contracts and online services are accessed with one ID.

3. Go to the **Billing** > **Your products** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2244144" target="_blank">Volume licensing</a> tab.

### If you previously registered a volume licensing agreement

After you register a VL agreement in the admin center, no new welcome emails are sent for subsequent agreements or license IDs that list you as a VL contact with the same business email address. More licenses are automatically available in the admin center on the **Billing** > **Your Products** > **Volume Licensing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2297440" target="_blank">Contracts</a> page.

## Who receives the volume licensing welcome email?

After you submit your VL agreement, welcome emails are sent to both the Primary Contact (Pri) and Notices and Online Administrator contact (NTC) that you provided to Microsoft in the VL document.

The welcome email is sent from the email address "microsoft-noreply\@microsoft.com" with the subject line "Action required: Sign in to manage your volume licensing assets." If you're an EA or EU customer, you receive a notification email with the subject line "Permission changes for Microsoft Volume Licensing contracts."

> [!NOTE]
> If you can't find the email in your inbox, check your junk or spam folders.

**Non-EA and non-EU customers:** If you don't have access to the business email address the welcome email is sent to, ask the owner of that email to forward you any invitation and registration confirmations emails.

## Sign up for a new Microsoft Entra ID

Organizations with no online presence with Microsoft must [sign up](https://signup.microsoft.com/get-started/signup?products=8339cc50-d965-4ad5-bb94-749021a5ebf9&origin=tenantonly&ali=1&ru=https%3a%2f%2fadmin.microsoft.com) for a new Microsoft Entra ID account (also known as a tenant) to allow VL users access to the Microsoft 365 admin center. This doesn't require the user, or the organization, to buy or use any Microsoft products or services, like Microsoft 365.

To create a Microsoft Entra ID using your organization's email domain (like aminata\@fourthcoffee.com), you must provide proof that the organization owns that domain. This proof might be something that your organization's IT administrator prefers to complete, rather than the VL user.

Alternatively, if you need a Microsoft Entra ID format that isn't linked to the organization's email domain (like aminata\@fourthcoffee.onmicrosoft.com), you can create one independently from an IT administrator. Before you deploy any online services like Microsoft 365, we highly recommend that your organization takes over such a Microsoft Entra tenant and link it to the organization's own domain.

> [!TIP]
> Make sure to write down your user ID because you need it later.

## Troubleshooting

This section explains how to resolve issues that you might encounter when you try to sign in to the Microsoft 365 admin center to perform VL tasks.

### You're redirected to the Azure portal when you sign in

When you try to sign in to the admin center, you might be redirected to the Azure portal (azure.microsoft.com) instead, and are unable to access your VL information. This redirect happens because of your organization's Outlook settings and isn't something that Microsoft's VL support team can resolve. Ask your IT administrators to check the safe links list in their Microsoft Defender policy settings. For more information, see [Set up Safe Links policies in Microsoft Defender for Office 365](/defender-office-365/safe-links-policies-configure). If you need help with configuring Outlook safe settings, you can open a [technical support request](https://support.serviceshub.microsoft.com/supportforbusiness/create).

### An error occurred while setting up your profile

If you can't sign in to the admin center, and repeatedly see the message "An error occurred while setting up your profile. Please refresh the page to try again," you might be trying to sign in with an invalid account type. Invalid account types include the following accounts:

- A Microsoft account (MSA). This account type is personal to you and isn't manged by your work organization. For example, you might sign in to a Microsoft service like email or Xbox with a log In ID like \<user>\@gmail.com or \<user>\@outlook.com. You must sign in with a Microsoft Entra ID instead.
- A self-service Microsoft Entra ID created when signing up for a cloud service. This account might look like it belongs to your work organization, but your organization has yet to take over or become the admin of the email domain to convert it into a Microsoft Entra ID.
- A Microsoft Entra ID that's different from the one that you used previously to sign in for volume licensing.  For example, you might be trying to sign in with your work email marcel\@contoso.com whereas you previously signed in to volume licensing with licenseAdmin\@contoso.com.

### Ready to become the admin of \<domain name\>

If you see the message "Ready to become an admin of \<domain name\>," this means that you're using a self-service (unmanaged) Microsoft Entra ID and are being prompted to take over the unmanaged directory to convert it to a managed one.

> [!TIP]
> If you see an Admin Tile in the App Picker when you sign in to portal.office.com or other online services, it means that the account is unmanaged. To find out whether you're a user of a managed or unmanaged tenant, see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).

The takeover process involves you, or your organization's IT administrator, verifying ownership of the email domain by confirming the domain's DNS TXT records. The DNS TXT records are available from your domain name registrar, like GoDaddy.

For step-by-step instructions, see [How to takeover over an unmanaged directory](/azure/active-directory/enterprise-users/domains-admin-takeover#decide-how-you-want-to-take-over-an-unmanaged-directory).

After your organization converts your account to a managed Microsoft Entra ID, or you identify a suitable alternative Microsoft Entra ID, contact <a href="https://go.microsoft.com/fwlink/p/?linkid=2166757" target="_blank">Microsoft Volume Licensing Support</a> to request a new volume licensing profile. When you contact support, you must provide the following items:

- Your old sign-in ID
- The new Microsoft Entra ID you just signed up for
- VL agreement numbers
- The email address listed on the licensing agreement (the one where the invitation was sent)

### I don't see the volume licensing page in the Microsoft 365 admin center

If you don't see the <a href="https://go.microsoft.com/fwlink/p/?linkid=2244144" target="_blank">Volume licensing</a> page after you sign in to the admin center, you can try the following actions to resolve it:

- **Use the correct URL:** Verify that you're going to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, then go to the **Billing** > **Your products** page and select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2244144" target="_blank">Volume licensing</a> tab.

  - If you don't see **Billing**, go to the bottom of the navigation menu, select **View all**, and then pin the **Billing** option to the navigation menu.

- **Use the correct role:**

  - If you're a VL user (Non-EA and non-EU customers only), verify that you completed the license registration by selecting the link in the welcome email that you received.
  - You might have access to the admin center because of a different role, or you might not have a VL role assigned to you. Contact a VL Administrator for your organization and ask them to grant you VL permissions.

- **Use the correct user ID:**

  - **Non-EA and non-EU customers only:** Verify that the user ID you used to register VL licenses in the admin center is the same as the user ID that you're using to sign in.
  - **EA and EU customers only:** Verify that the user ID you used to sign in is the one to which access was given by the VL administrator.

### My volume licensing welcome email is invalid

The old Volume Licensing Service Center (VLSC) was retired in April 2024, and all existing customers were migrated to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>. If you received an invitation to the VLSC before April 2024 but haven't yet registered your account in the site, the invitation is now invalid. If you still need permissions to view and manage a VL agreement, ask a VL Administrator in your organization to add you as a VL user. For more information, see [Manage volume licensing user roles](manage-user-roles-vl.md).

If there's no administrator for that agreement, ask the VL support team to create a new VL profile for you. You must be able to confirm the following information:

- VL agreement (License ID) number
- Business email address listed in the VL agreement
- The sign-in ID that you use to sign in to the Microsoft 365 admin center

## Contact volume licensing support

Submit a case in the admin center > <a href="https://go.microsoft.com/fwlink/p/?linkid=2166757" target="_blank">Help & Support</a>. If you can't access the admin center, see [Contact volume licensing support](contact-vl-support.md).
