---
title: "Understanding Microsoft 365 support case creation and data access"
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 12/22/2025
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- Adm_O365
- Adm_TOC
description: "Learn about the diagnostic data Microsoft 365 Support engineers access to resolve support cases, including consent, data categories, retention periods, and logging details."
customer-intent: As an administrator, I want to understand what data Microsoft Support can access when I create a support case and how I can track that activity.
---

# Understanding Microsoft 365 support case creation and data access

This article describes what happens when a support case is created in Microsoft 365 for business, how Microsoft support engineers access customer information, the level of access that's granted, and what happens when a support case is closed.

For information about how to create a support case, see [Get support for Microsoft 365 for business](get-help-support.md).

> [!TIP]
> If you're a home user and you need technical support, see [Contact us](https://support.microsoft.com/en-us/contactus#!).

## What happpens when a support case is created in the Microsoft 365 admin center?

When a user creates a support request in the [Microsoft 365 admin center](https://admin.microsoft.com), the user grants Microsoft permission to access only the information that's needed for assistance. This consent is recorded in cross-tenant access settings by adding the Microsoft Support tenant (`b4c546a4-7dac-46a6-a7dd-ed822a11efd3`) as a service provider partner. 

The level of access granted for the Microsoft Support tenant is captured as *Delegated Admin Service Provider Constraints*, which represents the user roles the Microsoft Support engineer can have in the customer tenant. 

Implicit consent grants only the `Microsoft365SupportEngineer` role level access. The identity of the person who created the ticket is used for this process.

### Audit events logged in the customer tenant during support case creation

When a support case is created, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Order | Event | Actor |
|--|--|--|
| 1 | If it doesn't exist already, **Add a partner to cross-tenant access setting**<br/>(Microsoft Support tenant only) | User identity who created the support ticket and the Microsoft 365 admin center application |
| 2 | If it doesn't exist already, **Adding allowed assignable roles**<br/>(`Microsoft365SupportEngineer` role only) | User identity who created the support ticket and the Microsoft 365 admin center application |

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

Only the Security Administrator, Teams Administrator, and Global Administrator roles can modify any other aspects of cross-tenant access settings.

## What level of access does Microsoft Support have on the customer tenant?

The level of access is captured as *Delegated Admin Service Provider Constraints*, and currently, the support ticket creation process implicitly grants just the `Microsoft365SupportEngineer` role. This role includes the following actions/permissions:

- `microsoft.directory/devices/standard/read`
- `microsoft.directory/domains/standard/read`
- `microsoft.directory/groups/standard/read`
- `microsoft.directory/policies/standard/read`
- `microsoft.directory/servicePrincipals/standard/read`
- `microsoft.directory/users/standard/read`

## How long does Microsoft Support have access?

Access is revoked when the Microsoft Support tenant is removed from cross-tenant access settings. This process is automated and directly linked to the lifecycle of support tickets within the tenant. 

Alternatively, a user who has an appropriate role assigned can revoke access at any time by deleting the Microsoft Support tenant partner in cross-tenant access settings. If you revoke access manually, Microsoft Support loses the ability to assist in resolving your support cases.

## What happens when a support case is closed?

When a support case is closed, Microsoft checks to see if there are any other active support cases open. If there are no other active support cases, Microsoft initiates the access revocation process, which includes multiple steps.

### Audit events seen during support case closure

When a support case is closed, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Event | Actor |
|--|--|
| Add a service principal<br/>(`EntraGDAP` handles revocation) | `AssistAPI` application |
| Deleting allowed assignable roles | `EntraGDAP` application |
| Delete partner specific cross-tenant access setting<br/>(Microsoft Support tenant only) | `EntraGDAP` application |

## Learn more about Microsoft Entra audit logs

See the following resources for more information about the audit logs:

- [What are Microsoft Entra audit logs?](/entra/identity/monitoring-health/concept-audit-logs)
- [How to customize and filter identity activity logs](/entra/identity/monitoring-health/howto-customize-filter-logs)