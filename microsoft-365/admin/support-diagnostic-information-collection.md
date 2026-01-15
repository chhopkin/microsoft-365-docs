---
title: "Understanding Microsoft 365 support case creation and data access"
ms.author: deniseb
ms.reviewer: onatwil; ramical
author: denisebmsft
manager: dansimp
ms.date: 01/15/2026
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: Tier1
description: "Understand what happens during the support case lifecycle, including consent that's granted to Microsoft Support engineers and what to expect in audit logs."
customer-intent: As an IT leader, I want to understand the Microsoft Support case lifecycle and what to expect.
---

# Understanding Microsoft 365 support case creation and data access

Microsoft is improving your visibility into Microsoft Support's read-only access to customer data during the support lifecycle. When a customer creates a support request, [cross-tenant access](/entra/external-id/cross-tenant-access-overview) is granted to Microsoft Support to access the information that's needed to troubleshoot the issue. This access is time bound and uses least-privileged access, in accordance with [Zero Trust Principles](/security/zero-trust/zero-trust-overview).

This article describes the events that are logged in a customer tenant during the Microsoft Support case lifecycle, the access Microsoft Support engineers have, and the types of information that might be accessed for a support case.

> [!NOTE]
> To learn how to create a support case, see [Get support for Microsoft 365 for business](get-help-support.md).
> 
> If you're a home user and you need technical support, see [Contact us](https://support.microsoft.com/en-us/contactus#!).

## What happens when a support case is created in the Microsoft 365 admin center?

When a [user with permissions](#who-can-create-support-tickets) in an organization submits a support request in the [Microsoft 365 admin center](https://admin.microsoft.com), they grant Microsoft Support permission to access the information that's needed for assistance. This activity is recorded in the customer's cross-tenant access settings by adding the Microsoft Support tenant (Tenant ID `b4c546a4-7dac-46a6-a7dd-ed822a11efd3`) as a service provider partner. In this configuration, the Microsoft Support tenant is treated as a partner (see [Partner cross-tenant access settings](/graph/api/resources/crosstenantaccesspolicy-overview)).

> [!IMPORTANT]
> Only a user who has an appropriate role assigned can open a support case. The Microsoft Support tenant is added to the customer's tenant as a service provider partner to enable the Microsoft Support team to troubleshoot and resolve a case. The user who opens a support cases can't grant cross-tenant access to other partners. Only a user who has the Security Administrator, Teams Administrator, or Global Administrator role can modify any other aspects of cross-tenant access settings.

The level of access granted for the Microsoft Support tenant is captured as *Delegated Admin Service Provider Constraints*, which represents the user role a Microsoft Support engineer can have in the customer tenant. The [Microsoft 365 Support Engineer](/entra/identity/role-based-access-control/permissions-reference#microsoft-365-support-engineer) role is used for Microsoft Support engineers. 

## What audit events are logged during a Microsoft Support case lifecycle?

Audit events are logged when a support case is opened, when Microsoft Support engineers work on a case, and when a case is closed. This article describes what to expect in audit log entries.

To learn more about Microsoft Entra audit logs, see the following articles:

- [What are Microsoft Entra audit logs?](/entra/identity/monitoring-health/concept-audit-logs)
- [How to access activity logs in Microsoft Entra ID](/entra/identity/monitoring-health/howto-access-activity-logs)

### Audit events during support case creation

When a support case is created, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Order | Event | Actor |
|--|--|--|
| 1 | If it doesn't exist already, **Add a partner to cross-tenant access setting**<br/>(Adds the Microsoft Support tenant only) | Identity of the user who created the support ticket |
| 2 | If it doesn't exist already, **Adding allowed assignable roles**<br/>(Adds the Microsoft 365 Support Engineer role only) | Identity of the user who created the support ticket |

### Audit events when Microsoft Support works on a case

When a Microsoft Support engineer works on a support case, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Order | Event | Actor |
|--|--|--|
| 1 | If it doesn't exist already, **Add a Service Principal** for the Microsoft Support tenant <br/>(Microsoft Entra GDAP application) | Service Principal for the Assist API application <br/>(See [What is the Assist API application, and how do I find it in my tenant?](#what-is-the-assist-api-application-and-how-do-i-find-it-in-my-tenant)) |
| 2 | **Add member to role** (Group from Microsoft Support tenant is added to the Microsoft 365 Support Engineer role) | Assist API application <br/>(App ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`) |

### Audit events during support case closure

When a support case is closed, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Order | Event | Actor |
|--|--|--|
| 1 | **Add a service principal**<br/>(The Microsoft Entra GDAP application handles revocation) | Assist API application <br/>(App ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`) |
| 2 | **Deleting allowed assignable roles** | Microsoft Entra GDAP application <br/>(App ID `bc56af95-7a3b-459f-98a9-bd86532b0e89`) |
| 3 | **Delete partner specific cross-tenant access setting** <br/>(Removes only the Microsoft Support tenant) | Microsoft Entra GDAP application <br/>(App ID `bc56af95-7a3b-459f-98a9-bd86532b0e89`) |

### What is the Assist API application, and how do I find it in my tenant?

Assist API is a Microsoft-owned application that has Application ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`. In audit events, you can see the service principal ID of the Assist API application for your tenant. The service principal ID is unique to your tenant.

To find the service principal ID in your tenant, follow these steps:

1. Go to the [Microsoft Entra admin center](https://entra.microsoft.com) and sign in.

2. Navigate to **Enterprise Apps**.

3. In the **Application Type** filter, select **All Applications**, and then search for the Application ID `2b8844d8-6c87-4fce-97a0-fbec9006e140`.

   Your unique service principal ID is displayed.

## What level of access does Microsoft Support have on the customer tenant?

The level of access is captured as *Delegated Admin Service Provider Constraints*. Currently, the support case creation process allows Microsoft Support engineers to assume the *Microsoft 365 Support Engineer* role, which includes the read permissions that are described in [Microsoft Entra built-in roles: Microsoft 365 Support Engineer](/entra/identity/role-based-access-control/permissions-reference#microsoft-365-support-engineer).

> [!NOTE]
> The Microsoft 365 Support Engineer role is used for Microsoft Support cases only. This role shouldn't be assigned to other users in your organization.

For more information, see the following articles:

- [What's new in Microsoft Entra RBAC documentation](/entra/identity/role-based-access-control/whats-new)
- [Roles not shown in the Microsoft Entra admin center](/entra/identity/role-based-access-control/permissions-reference#roles-not-shown-in-the-portal)
- [Microsoft 365 Support Engineer role](/entra/identity/role-based-access-control/permissions-reference#microsoft-365-support-engineer)

## What information can Microsoft Support access?

Microsoft Support accesses only the information that's needed to troubleshoot and resolve support cases. Depending on the nature of your support request, the data that Microsoft Support can access would belong under the categories listed in the following table:

| Category | Examples |
|--|--|
| **Support data**: All data provided to Microsoft by the customer as part of a customer engagement to obtain support services | Support requests from customers and phone conversations, online chat sessions, or remote assistance sessions between support professionals and customers<br/><br/> Case notes and/or records related to support requests from customers<br/><br/>Data provided to Microsoft by the customer as part of support activities |
| **Account data**: Contact, billing, purchase, payment, and/or license information | Customer's provisioning information<br/><br/>Account configuration and billing data<br/><br/>Tenant administrator contact information (such as tenant administrator's name, address, e-mail address, phone number)<br/><br/>Licensing and purchase information |
| **System metadata**: Data generated in the course of running the service | Event logs<br/><br/>Access control logs<br/><br/>Account information belonging to Microsoft operations personnel<br/><br/>Microsoft server names/server IPs<br/><br/>Server patching and vulnerability data<br/><br/>Service configuration data<br/><br/>Telemetry (on-premises or cloud) |
| **Organization information**: Data that can be used to identify a particular tenant, deployment, or organization (generally configuration or usage data) | Tenant ID (non-GUID)<br/><br/>TenantID (GUID) due to the existence of many out of boundary `TenantID` to name mapping tables<br/><br/>Tenant usage data<br/><br/>Tenant IP addresses (IPv4), such as tenant's firewall IP address<br/><br/>Global prefix and subnet ID (first 64 bits of IPv6 address)<br/><br/>Tenant domain name in e-mail address (such as `joe@contoso.com`)<br/><br/>Mapping of organizational GUID to organization |
| **Customer data**: Data that directly identifies or could be used to identify the authenticated user of a Microsoft service | User-specific IP address (IPv4)<br/><br/>User principal name (`joe@company.com`)<br/><br/>Address book data<br/><br/>User's machine name<br/><br/>SIP URI |
| **Pseudonymous identifiers**: An identifier created by Microsoft tied to the user of a Microsoft service | User GUIDs or PUIDs<br/><br/>Session IDs |

## How long does Microsoft Support have access to tenant data?

Access to tenant data is revoked when the Microsoft Support tenant is removed from the customer's cross-tenant access settings. This process is automated and is directly linked to the lifecycle of support cases within the tenant. 

If a case is opened for more than 30 days, access is revoked automatically, provided there aren't any other, newer cases opened. A customer can open a new support case or reopen a closed case to restore access.

A customer can also revoke access at any time by deleting the Microsoft Support tenant partner in their cross-tenant access settings. To remove Office 365 (`b4c546a4-7dac-46a6-a7dd-ed822a11efd3`), follow the steps in [Cross-tenant access settings: Remove an organization](/entra/external-id/cross-tenant-access-settings-b2b-collaboration#remove-an-organization).

> [!CAUTION]
> If you revoke access manually, Microsoft Support loses the ability to help resolve your support cases.

## What happens when a support case is closed?

When a support case is closed, Microsoft checks to see if there are any other active support cases open. If there are no other active support cases, Microsoft initiates the access revocation process, which includes multiple steps.

## How long is diagnostic data retained in Microsoft systems?

Microsoft retains diagnostic data related to a support case for up to 28 days after it's collected. After this period, the data is deleted.

For information about how Microsoft protects customer data, see [Privacy and data management overview](/compliance/assurance/assurance-privacy).

## Who can create support tickets?

Authorization to create support tickets is restricted to users who are assigned one of the following roles. These user roles are also permitted to add the Microsoft Support partner as a service provider in cross-tenant access settings. 

- Application Administrator
- Authentication Administrator
- Authentication Policy Administrator
- Azure Information Protection Administrator
- Billing Administrator
- Cloud Application Administrator
- Compliance Administrator
- Compliance Data Administrator
- Desktop Analytics Administrator
- Dynamics 365 Administrator
- Exchange Administrator
- Fabric Administrator
- Global Administrator
- Global Secure Access Administrator
- Groups Administrator
- Helpdesk Administrator
- Hybrid Identity Administrator
- Insights Administrator
- Intune Administrator
- Office Apps Administrator
- Power Platform Administrator
- Privileged Authentication Administrator
- Security Administrator
- Security Operator
- Service Support Administrator
- SharePoint Administrator
- Skype for Business Administrator
- Teams Administrator
- Teams Communications Administrator
- Teams Telephony Administrator
- User Administrator
- Windows 365 Administrator

Only users who have the Security Administrator, Teams Administrator, or Global Administrator role can modify any other aspects of cross-tenant access settings.

For more information about roles in Microsoft Entra ID, see [Support least privileged roles](/entra/identity/role-based-access-control/delegate-by-task#support-least-privileged-roles).

## Related content

- [Overview: Cross-tenant access with Microsoft Entra External ID](/entra/external-id/cross-tenant-access-overview)

- [What are Microsoft Entra audit logs?](/entra/identity/monitoring-health/concept-audit-logs)

- [How to customize and filter identity activity logs](/entra/identity/monitoring-health/howto-customize-filter-logs)

- [Personnel management overview - Microsoft Service Assurance](/compliance/assurance/assurance-human-resources)

- [Audit logging and monitoring overview - Microsoft Service Assurance](/compliance/assurance/assurance-audit-logging)