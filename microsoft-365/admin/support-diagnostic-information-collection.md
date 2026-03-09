---
title: Understand Microsoft 365 Support Case Creation and Data Access
ms.author: deniseb
ms.reviewer: onatwil; ramical
author: denisebmsft
manager: dansimp
ms.date: 02/19/2026
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: Tier1
description: Learn what happens during the Microsoft 365 support case lifecycle, including data access for Microsoft Support engineers and audit log events. Review now.
customer-intent: As an IT leader, I want to understand the Microsoft Support case lifecycle and what to expect.
---

# Understand Microsoft 365 support case creation and data access

Microsoft is improving your visibility into Microsoft Support's read-only access to your data during the Microsoft 365 support case lifecycle. When you create a support request, you grant [cross-tenant access](/entra/external-id/cross-tenant-access-overview) to Microsoft Support to access the information needed to troubleshoot the issue. This access is time bound and uses least-privileged access, in accordance with [Zero Trust Principles](/security/zero-trust/zero-trust-overview).

This article describes what you see in your Microsoft Entra audit logs when:

- When a Microsoft 365 Support case is created.
- When a Microsoft Support engineer works on your case.
- When a Microsoft 365 Support case is closed.

It also lists who can create support cases and what permissions are granted to Microsoft Support engineers.

> [!NOTE]
>
> To learn how to create a support case, see [Get support for Microsoft 365 for business](get-help-support.md).
>
> If you're a home user and you need technical support, see [Contact us](https://support.microsoft.com/contactus).

## What happens when a Microsoft 365 support case is created?

When a [user who has an appropriate role assigned](#who-can-create-support-cases) creates a support case in the [Microsoft 365 admin center](https://admin.microsoft.com), a special type of cross-tenant access policy resource is created in your tenant. This cross-tenant access policy gives you visibility into Microsoft Support's permission to access diagnostic data in your tenant. This policy is restricted to the Microsoft Support tenant and the [Microsoft 365 Support Engineer role](/entra/identity/role-based-access-control/permissions-reference#microsoft-365-support-engineer). You can't create or modify any other type of cross-tenant access policy, except for administrators who have the Global Administrator, Security Administrator, or Teams Administrator role assigned.

To provide you with contextual understanding of this policy, the cross-tenant access policy resource appears in Microsoft Entra audit logs as created by the user who initiated the support case. The level of access granted for the Microsoft Support tenant is captured as *Delegated Admin Service Provider Constraints*.

Microsoft Entra audit events are logged throughout the Microsoft 365 Support case lifecycle.

## What audit events are logged during a Microsoft Support case lifecycle?

Audit events are logged when:

- A Microsoft 365 support case is opened.
- A Microsoft Support engineer works on the support case.
- A Microsoft 365 support case is closed.

To learn more about Microsoft Entra audit logs, see the following articles:

- [What are Microsoft Entra audit logs?](/entra/identity/monitoring-health/concept-audit-logs)
- [How to access activity logs in Microsoft Entra ID](/entra/identity/monitoring-health/howto-access-activity-logs)

### Audit events during support case creation

When you create a support case, the following Microsoft Entra audit events are recorded:

| Order | Event | Actor |
|--|--|--|
| 1 | If it doesn't already exist, **Add a partner to cross-tenant access setting**.<br/><br/>Adds the Microsoft Support tenant with Tenant ID `b4c546a4-7dac-46a6-a7dd-ed822a11efd3`. | Identity of the user who created the support case. |
| 2 | If it doesn't already exist, **Adding allowed assignable roles**.<br/><br/>Adds the Microsoft 365 Support Engineer role only. | Identity of the user who created the support case. |

### Audit events when Microsoft Support works on your case

When a Microsoft Support engineer works on your support case, the following Microsoft Entra audit events are recorded:

| Order | Event | Actor |
|--|--|--|
| 1 | If it doesn't exist already, **Add a Service Principal** for the Microsoft Support tenant. <br/><br/>Microsoft Entra GDAP application. | Service Principal for the Assist API application. <br/><br/>(See [What is the Assist API application, and how do I find it in my tenant?](#what-is-the-assist-api-application-and-how-do-i-find-it-in-my-tenant)) |
| 2 | **Add member to role**.<br/><br/> Group from Microsoft Support tenant is added to the Microsoft 365 Support Engineer role. | Assist API application. <br/><br/>App ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`. |

### Audit events during support case closure

When your support case is closed, the following Microsoft Entra audit events are recorded:

| Order | Event | Actor |
|--|--|--|
| 1 | **Add a service principal**.<br/><br/>The Microsoft Entra GDAP application handles revocation. | Assist API application. <br/><br/>App ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`. |
| 2 | **Deleting allowed assignable roles**. | Microsoft Entra GDAP application.<br/><br/>App ID `bc56af95-7a3b-459f-98a9-bd86532b0e89`. |
| 3 | **Delete partner specific cross-tenant access setting**. <br/><br/>Removes the Microsoft Support tenant if there are no other active support cases or 30 days have elapsed since the most recent case was created. | Microsoft Entra GDAP application.<br/><br/>App ID `bc56af95-7a3b-459f-98a9-bd86532b0e89`. |

### What is the Assist API application, and how do I find it in my tenant?

Assist API is a Microsoft-owned application with the Application ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`. In Microsoft Entra audit events, you can see the service principal ID of the Assist API application for your tenant. The service principal ID is unique to your tenant.

To find the service principal ID in your tenant, follow these steps:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com).

1. From the left navigation bar, select **Entra ID** to expand it, and then select **Enterprise Apps**.

1. In the **Enterprise applications | All applications** page, under **Manage**, select **All applications**.

1. Select the **Application Type ==** filter.

1. In the **Application type** window, select **All Applications** from the dropdown, and then select **Apply**.

1. In the **Search by application name or object ID** search box, search for the Application ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`.

   Your unique service principal ID is displayed.

## What level of access does Microsoft Support have in my tenant?

The level of access is captured as *Delegated Admin Service Provider Constraints*, using the *Microsoft 365 Support Engineer* role. To see the read permissions that are granted, see [Microsoft Entra built-in roles: Microsoft 365 Support Engineer](/entra/identity/role-based-access-control/permissions-reference#microsoft-365-support-engineer).

> [!NOTE]
>
> Use the Microsoft 365 Support Engineer role only for Microsoft Support cases. Don't assign this role to other users in your organization.

For more information, see the following articles:

- [What's new in Microsoft Entra RBAC documentation](/entra/identity/role-based-access-control/whats-new).
- [Roles not shown in the Microsoft Entra admin center](/entra/identity/role-based-access-control/permissions-reference#roles-not-shown-in-the-portal).
- [Microsoft 365 Support Engineer role](/entra/identity/role-based-access-control/permissions-reference#microsoft-365-support-engineer).

## What information can Microsoft Support access?

Microsoft Support accesses only the information needed to troubleshoot and resolve your support case. Depending on the nature of your support request, the data that Microsoft Support can access falls under the categories listed in the following table:

| Category | Examples |
|--|--|
| **Support data**: All data provided to Microsoft by the customer as part of a customer engagement to obtain support services. | Support requests from customers and phone conversations, online chat sessions, or remote assistance sessions between support professionals and customers.<br/><br/> Case notes and records related to support requests from customers.<br/><br/>Data provided to Microsoft by the customer as part of support activities. |
| **Account data**: Contact, billing, purchase, payment, and license information. | Customer's provisioning information.<br/><br/>Account configuration and billing data.<br/><br/>Tenant administrator contact information, such as tenant administrator's name, address, e-mail address, phone number.<br/><br/>Licensing and purchase information. |
| **System metadata**: Data generated in the course of running the service. | Event logs.<br/><br/>Access control logs.<br/><br/>Account information belonging to Microsoft operations personnel.<br/><br/>Microsoft server names and server IPs.<br/><br/>Server patching and vulnerability data.<br/><br/>Service configuration data.<br/><br/>Telemetry (on-premises or cloud). |
| **Organization information**: Data that can be used to identify a particular tenant, deployment, or organization (generally configuration or usage data). | Tenant ID (non-GUID).<br/><br/>Tenant ID (GUID) due to the existence of many out of boundary Tenant ID to name mapping tables.<br/><br/>Tenant usage data.<br/><br/>Tenant IP addresses (IPv4), such as tenant's firewall IP address.<br/><br/>Global prefix and subnet ID (first 64 bits of IPv6 address).<br/><br/>Tenant domain name in e-mail address, such as `joe@contoso.com`.<br/><br/>Mapping of organizational GUID to organization. |
| **Customer data**: Data that directly identifies or could be used to identify the authenticated user of a Microsoft service. | User-specific IP address (IPv4).<br/><br/>User principal name (`joe@company.com`).<br/><br/>Address book data.<br/><br/>User's machine name.<br/><br/>SIP URI. |
| **Pseudonymous identifiers**: An identifier created by Microsoft tied to the user of a Microsoft service. | User GUIDs or PUIDs.<br/><br/>Session IDs. |

## How long does Microsoft Support have access to tenant data?

Microsoft Support loses access to your tenant data when the support tenant is removed from your cross-tenant access settings. This process is automated and directly linked to the lifecycle of support cases within your tenant.

- If a case is open for more than 30 days, access is revoked automatically, provided there aren't any other, newer cases opened. You can restore access by opening a new support case or reopening a closed case.

- You can revoke access at any time by deleting the Microsoft Support tenant partner in your cross-tenant access settings. To remove the Microsoft Support tenant, which is listed as Office 365 with Tenant ID `b4c546a4-7dac-46a6-a7dd-ed822a11efd3`, see [Cross-tenant access settings: Remove an organization](/entra/external-id/cross-tenant-access-settings-b2b-collaboration#remove-an-organization).

   > [!CAUTION]
   >
   > If you revoke access manually, Microsoft Support loses the ability to help resolve your support cases.

## What happens when a support case is closed?

When a support case is closed, Microsoft checks if there are any other active support cases open. If there are no other active support cases, Microsoft initiates the access revocation process, which includes multiple steps.

## How long is diagnostic data retained in Microsoft systems?

Microsoft retains diagnostic data related to your support case for up to 28 days after collection. After this period, Microsoft deletes the data.

For information about how Microsoft protects your data, see [Privacy and data management overview](/compliance/assurance/assurance-privacy).

## Who can create support cases?

Only users assigned one of the following roles can create a support case and the special type of cross-tenant access policy described in this article. These users can't create or modify any other type of cross-tenant access policy, except for administrators who have Security Administrator or Microsoft Teams Administrator role assigned.

- Application Administrator.
- Authentication Administrator.
- Authentication Policy Administrator.
- Azure Information Protection Administrator.
- Billing Administrator.
- Cloud Application Administrator.
- Compliance Administrator.
- Compliance Data Administrator.
- Desktop Analytics Administrator.
- Dynamics 365 Administrator.
- Exchange Administrator.
- Fabric Administrator.
- Global Administrator.
- Global Secure Access Administrator.
- Groups Administrator.
- Helpdesk Administrator.
- Hybrid Identity Administrator.
- Insights Administrator.
- Intune Administrator.
- Office Apps Administrator.
- Power Platform Administrator.
- Privileged Authentication Administrator.
- Security Administrator.
- Security Operator.
- Service Support Administrator.
- SharePoint Administrator.
- Skype for Business Administrator.
- Teams Administrator.
- Teams Communications Administrator.
- Teams Telephony Administrator.
- User Administrator.
- Windows 365 Administrator.

For more information about roles in Microsoft Entra ID, see [Support least privileged roles](/entra/identity/role-based-access-control/delegate-by-task#support-least-privileged-roles).

## Related content

- [Overview: Cross-tenant access with Microsoft Entra External ID](/entra/external-id/cross-tenant-access-overview).
- [What are Microsoft Entra audit logs?](/entra/identity/monitoring-health/concept-audit-logs).
- [How to customize and filter identity activity logs](/entra/identity/monitoring-health/howto-customize-filter-logs).
- [Personnel management overview - Microsoft Service Assurance](/compliance/assurance/assurance-human-resources).
- [Audit logging and monitoring overview - Microsoft Service Assurance](/compliance/assurance/assurance-audit-logging).
