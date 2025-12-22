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

Microsoft is improving your visibility into Microsoft Support's read-only access to customer data during the support lifecycle. When a user creates a support request, cross-tenant access is granted to Microsoft Support. That access is time bound and uses least-privileged access, in accordance with [Zero Trust Principles](/security/zero-trust/zero-trust-overview).

This article describes what happens when a support case is created in Microsoft 365 for business, how Microsoft support engineers access customer information, the level of access that's granted, and what happens when a support case is closed.

For information about how to create a support case, see [Get support for Microsoft 365 for business](get-help-support.md).

> [!TIP]
> If you're a home user and you need technical support, see [Contact us](https://support.microsoft.com/en-us/contactus#!).

## What happens when a support case is created in the Microsoft 365 admin center?

When a user creates a support request in the [Microsoft 365 admin center](https://admin.microsoft.com), the user grants Microsoft permission to access only the information that's needed for assistance. This consent is recorded in cross-tenant access settings by adding the Microsoft Support tenant (`b4c546a4-7dac-46a6-a7dd-ed822a11efd3`) as a service provider partner. 

The level of access granted for the Microsoft Support tenant is captured as *Delegated Admin Service Provider Constraints*, which represents the user roles the Microsoft Support engineer can have in the customer tenant. 

Implicit consent grants only the `Microsoft365SupportEngineer` role level access. The identity of the person who created the ticket is used for this process.

### Audit events logged in the customer tenant during support case creation

When a support case is created, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Order | Event | Actor |
|--|--|--|
| 1 | If it doesn't exist already, **Add a partner to cross-tenant access setting**<br/>(Microsoft Support tenant only) | User identity who created the support ticket and the Microsoft 365 admin center application (with display name `Microsoft Office 365 Portal`) |
| 2 | If it doesn't exist already, **Adding allowed assignable roles**<br/>(`Microsoft365SupportEngineer` role only) | User identity who created the support ticket and the Microsoft 365 admin center application (with the display name `Microsoft Office 365 Portal`) |

## What level of access does Microsoft Support have on the customer tenant?

The level of access is captured as *Delegated Admin Service Provider Constraints*, and currently, the support ticket creation process implicitly grants just the `Microsoft365SupportEngineer` role. This role includes the following actions/permissions:

- `microsoft.directory/devices/standard/read`
- `microsoft.directory/domains/standard/read`
- `microsoft.directory/groups/standard/read`
- `microsoft.directory/policies/standard/read`
- `microsoft.directory/servicePrincipals/standard/read`
- `microsoft.directory/users/standard/read`

## What happens when Microsoft accesses customer tenant information?

Microsoft Support accesses only basic information that's needed to troubleshoot and resolve support cases. Depending on the nature of your support request, the data that Microsoft can access would belong under one or more of the following categories:

| Category | Examples |
|--|--|
| **Support data**: All data provided to Microsoft by the customer as part of a customer engagement to obtain support services | Support requests from customers and phone conversations, online chat sessions, or remote assistance sessions between support professionals and customers<br/><br/> Case notes and/or records related to support requests from customers<br/><br/>Data provided to Microsoft by the customer as part of support activities |
| **Account data**: Contact, billing, purchase, payment, and/or license information | Customer's provisioning information<br/><br/>Account configuration and billing data<br/><br/>Tenant administrator contact information (such as tenant administrator's name, address, e-mail address, phone number)<br/><br/>Licensing and purchase information |
| **System metadata**: Data generated in the course of running the service | Event logs<br/><br/>Access control logs<br/><br/>Account information belonging to Microsoft operations personnel<br/><br/>Microsoft server names/server IPs<br/><br/>Server patching and vulnerability data<br/><br/>Service configuration data<br/><br/>Telemetry (on-premises or cloud) |
| **Organization identifiable information (OII)**: Data that can be used to identify a particular tenant, deployment, or organization (generally config or usage data) | Tenant ID (non-GUID)<br/><br/>TenantID (GUID) due to the existence of many out of boundary `TenantID` to name mapping tables<br/><br/>Tenant usage data<br/><br/>Tenant IP addresses (IPv4), such as tenant's firewall IP address<br/><br/>Global prefix and subnet ID (first 64 bits of IPv6 address)<br/><br/>Tenant domain name in e-mail address (such as `joe@contoso.com`)<br/><br/>Mapping of organizational GUID to organization |
| **End-user identifiable information (EUII)**: Data that directly identifies or could be used to identify the authenticated user of a Microsoft service | User-specific IP address (IPv4)<br/><br/>User principal name (`joe@company.com`)<br/><br/>Address book data<br/><br/>User's machine name<br/><br/>SIP URI |
| **End-user pseudonymous identifiers (EUPI)**: An identifier created by Microsoft tied to the user of a Microsoft service | User GUIDs or PUIDs<br/><br/>Session IDs |

### Audit events logged in the customer tenant when Microsoft Support works on a support case

When a Microsoft support engineer works on a support case, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Order | Event | Actor |
|--|--|--|
| 1 | If it doesn't exist already, **Add a Service Principal** (`EntraGDAP` application)<br/>(Microsoft Support tenant only) | `AssistAPI` application |
| 2 | **Add member to role** (Group from Microsoft Support tenant added to `Microsoft365SupportEngineer` role) | `AssistAPI` application |

## How long does Microsoft Support have access?

Microsoft Support access is revoked when the Microsoft Support tenant is removed from the customer's cross-tenant access settings. This process is automated and is directly linked to the lifecycle of support tickets within the tenant. If a case is opened for more than 30 days, access is revoked, provided there aren't any other, newer cases opened.

Alternatively, you can revoke access at any time by deleting the Microsoft Support tenant partner in cross-tenant access settings. To remove Office 365 (`b4c546a4-7dac-46a6-a7dd-ed822a11efd3`), follow the steps in [Cross-tenant access settings: Remove an organization](/entra/external-id/cross-tenant-access-settings-b2b-collaboration#remove-an-organization).

> [!CAUTION]
> If you revoke access manually, Microsoft Support loses the ability to assist in resolving your support cases.

## What happens when a support case is closed?

When a support case is closed, Microsoft checks to see if there are any other active support cases open. If there are no other active support cases, Microsoft initiates the access revocation process, which includes multiple steps.

### Audit events logged in the customer tenant during support case closure

When a support case is closed, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Order | Event | Actor |
|--|--|--|
| 1 | **Add a service principal**<br/>(`EntraGDAP` application handles revocation) | `AssistAPI` application |
| 2 | **Deleting allowed assignable roles** | `EntraGDAP` application |
| 3 | **Delete partner specific cross-tenant access setting** <br/>(Microsoft Support tenant only) | `EntraGDAP` application |

## How long is diagnostic data retained in Microsoft systems?

Microsoft retains diagnostic data for up to 28 days after it's collected. After this period, the data is deleted.

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

## Learn more about Microsoft Entra audit logs

See the following resources for more information about the audit logs:

- [What are Microsoft Entra audit logs?](/entra/identity/monitoring-health/concept-audit-logs)
- [How to customize and filter identity activity logs](/entra/identity/monitoring-health/howto-customize-filter-logs)