---  
title: "Block Teams resource account sign in to Microsoft 365 clients"  
description: Learn how to restrict Teams Rooms resource account authentication using conditional access policies to ensure accounts authenticate only on managed Teams Rooms on Windows devices.
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/27/2025  
ms.topic: how-to
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
ms.reviewer: kwekua
audience: Admin
ai-usage: ai-assisted  
---  

# Block Teams resource account sign in to Microsoft 365

As administrator you can restrict Teams Rooms resource account authentication with conditional access policies to ensure the account can only authenticate on a managed Teams Rooms on Windows device. This ensures that the resource account can't authenticate from any other device.

To configure these settings, your organization must have one of the following subscriptions or add-ons:

- Azure AD Premium P1/P2 (for dynamic groups & Conditional Access)
- Microsoft Entra ID Governance (for Access Packages)
- Microsoft Intune (for device compliance and enrollment)
- Access to Exchange Admin Center (for resource account creation, if applicable)

You must be a member of the following roles to perform these tasks:

- [Conditional Access administrator](/entra/identity/role-based-access-control/permissions-reference)
- [Exchange Online administrator](../add-users/about-exchange-online-admin-role.md)

For more information, see [Microsoft Entra built-in roles](/entra/identity/role-based-access-control/permissions-reference).

## Step 1: Tag Resource Accounts Using Extension Attributes

Tag resource accounts (e.g., conference room, Teams Rooms) from regular user accounts using an Entra ID extension attribute.

1. Choose an extension attribute (e.g., extensionAttribute2) and a reserved value (e.g., -3) to mark all resource accounts.

2. Set the attribute when creating new accounts:

3. - In Exchange Admin Center or via PowerShell, edit the mailbox/account properties.
    - Under **Mail** \> **Mailbox Features** \> **Custom attributes**, set extensionAttribute2 = -3.

4. Bulk-update existing accounts (if needed):

5. Use Azure AD PowerShell to locate existing resource accounts and set the attribute in bulk.

## Step 2: Build a Dynamic Group for Resource Accounts

Automatically group all tagged resource accounts for policy assignment. Create a dynamic group called "MTR_Resource_Accounts".

1. Navigate to **Azure AD** \> **Groups** \> **New group**.
2. Select **Security** as the group type, and add a name.
3. Under **Membership type**, choose **Dynamic User** and add a rule: (user.extensionAttribute2 -eq "-3").
4. Review and create the group.

## Step 3: Configure Access Packages for Device Enrollment

Allow resource accounts to complete Entra join of Teams devices in a controlled, limited-time window.

1. In **Microsoft Entra ID** \> **Identity Governance** \> **Access packages**, create two packages:

2. - MTR Device Setup (one-time, limited duration)
    - MTR Device Full (persistent membership for deployed devices)

3. For MTR Device Setup:

4. - Resource roles: Assign the MTR_DeviceSetup group
    - Requests: Require two-step approval (local IT manager + global admin)
    - Duration: Configure a short access window (e.g., 1 day) for Entra join. Under **Lifecycle** -\> **Expiration** set the Access package assignments expire = "Number of days" and set number of days = 1.
    - Users who can request access: "For users in your directory" and select "Specific users and groups".
    - Select users and groups: set to "MTR_Resource_Accounts" dynamic group

5. For MTR Device Full:

6. - Resource roles: Assign the MTR_DeviceFull group
    - Requests: Require two-step approval (local IT manager + global admin)
    - Duration: Access package assignments expire = "Never"
    - Users who can request access: "For users in your directory" and select "Specific users and groups".
    - Select users and groups: set to "MTR_Resource_Accounts" dynamic group

## Step 4: Tag Approved Devices via Extension Attributes

Mark each successfully Entra joined Teams device to verify it's approved.

1. As part of the Access Package workflow (upon successful Entra join), use an Entra ID provisioning action or Azure Automation runbook to set a device extension attribute (e.g., extensionAttribute2 = "MTR_Approved").
2. Confirm in **Azure AD** \> **Devices** that the attribute appears on the device object.
3. When the device is removed from MTR Device Full, remove the device object extension attribute.
4. Confirm in **Azure AD** \> **Devices** that the attribute is removed on the device object when removed from MTR Device Full access package.

## Step 5: Conditional Access Policies

Deploy two key Conditional Access (CA) policies to enforce compliance:

<table data-border="1">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Policy Name</th>
<th>Conditions</th>
<th>Grant Controls</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Resource Accounts on Managed Devices</td>
<td>* Users: Dynamic group MTR_Resource_Accounts<br />
* Cloud apps: All Microsoft 365 apps<br />
* Device: device.extensionAttribute2 -eq "MTR_Approved"</td>
<td>Grant access only if device is compliant and Entra joined</td>
</tr>
<tr class="even">
<td>Compliant Devices Only</td>
<td>* Users: All users<br />
* Cloud apps: All Microsoft 365 apps<br />
* Device state: Intune compliant</td>
<td>Require device to be marked compliant via Intune</td>
</tr>
<tr class="odd">
<td>Require multifactor authentication (MFA)</td>
<td>* Users: All users<br />
* Exclusion group: MTR_DeviceSetup</td>
<td>Require MFA except for devices in exclusion group to allow MTR to Entra join</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Enforce MFA on all sign-ins as a tenant-wide prerequisite.

## Step 6: Verify and Test

1. Create a test conference room account, verify the extension attribute is set.
2. Confirm membership in MTR_Resource_Accounts.
3. Request the MTR Device Setup access package for the test account.
4. Within the approval window, perform Azure AD join on a Teams device.
5. Verify device object is tagged MTR_Approved.
6. On the joined device, sign in to Teams/M365 with the resource account - Allowed.
7. On a non-joined device, attempt sign-in with the same resource account - Blocked.
8. On any device with a personal user account - Allowed (assuming compliance/MFA).
9. Remove device from MTR Device Full access package when a Teams device is retired/decommissioned.
10. Ensure device object extension attribute tag is removed.
11. Attempt sign-in from the device and ensure it is blocked.
