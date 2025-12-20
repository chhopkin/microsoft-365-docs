---
title: "Understanding Microsoft 365 support case creation and data access"
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 12/20/2025
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

# Understanding Microsoft 365 support case creation nd data access

This article describes what happens when a support case is created in Microsoft 365 for business, how Microsoft support engineers access customer information, and the level of access that's granted. 

> [!TIP]
> If you're a home user and you need technical support, see [Contact us](https://support.microsoft.com/en-us/contactus#!).

## What happpens when a support case is created in the Microsoft 365 admin center?

When a user creates a support request in the [Microsoft 365 admin center](https://admin.microsoft.com), the user grants Microsoft permission to access only the information that's needed for assistance. This consent is recorded in cross-tenant access settings by adding the Microsoft Support tenant as a service provider partner. The level of access granted for the Microsoft Support tenant is captured as *Delegated Admin Service Provider Constraints*, which represents the user roles the Microsoft Support engineer can have in the customer tenant. Implicit consent grants only the `Microsoft365SupportEngineer` role level access. The identity of the person who created the ticket is used for this process.

### Audit events seen in the customer tenant during support case creation

When a support case is created, the following audit events are logged in the customer's Microsoft Entra audit logs:

| Event | Actor |
|--|--|
| Add a partner to cross-tenant access setting<br/>(Microsoft Support tenant only) | User identity who created the support ticket and the Microsoft 365 admin center application |
| Adding allowed assignable roles<br/>(`Microsoft365SupportEngineer` role only) | User identity who created the support ticket and the Microsoft 365 admin center application |
| Add member to role<br/>(Group from the Microsoft Support tenant added to the `Microsoft365SupportEngineer` role) | AssistAPI application |

### Who can create support tickets

Authorization to create support tickets is restricted to users who are assigned one of the following roles. Consequently, these user roles are also permitted to add the Microsoft Support partner as a Service Provider in cross-tenant access settings. 

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

Aside from the Security Administrator, Teams Administrator, and Global Administrator roles listed above, no other roles possess the authority to modify any additional aspects of the cross-tenant access settings.

### What level of access does Microsoft Support have on the customer tenant?

The level of access is captured as *Delegated Admin Service Provider Constraints*, and currently, the support ticket creation process implicitly grants just the `Microsoft365SupportEngineer` role. This role includes the below actions/permissions.

        "microsoft.directory/devices/standard/read",
        "microsoft.directory/domains/standard/read",
        "microsoft.directory/groups/standard/read",
        "microsoft.directory/policies/standard/read",
        "microsoft.directory/servicePrincipals/standard/read",
        "microsoft.directory/users/standard/read"

### How long does Microsoft Support have access

The revocation of access to Microsoft occurs upon the deletion of the Microsoft Support Tenant partner within the cross-tenant access settings. This process is automated and directly linked to the lifecycle of support tickets within the tenant.  Or the customer user who has one of the above-mentioned roles can revoke access at any time by deleting the partner in cross-tenant access settings. If a customer chooses to manually revoke the access, Microsoft Support will lose ability to assist resolving the support ticket(s) created by the customer.

## What happens during Support Case Closure

During the support case closure, we can check if there are any other active support tickets from the customer, if none, we trigger the access revocation process, which is again a multiple step process.
Audit events seen in the customer tenant during this process

1.    Add a ServicePrincipal (EntraGDAP application which handles the revocation)
Actor: AssistAPI application
2.    Deleting allowed assignable roles 
Actor: EntraGDAP application
3.    Delete partner specific cross-tenant access setting (only Microsoft Support tenant)
Actor: EntraGDAP application  

Support Case Creation Through Phone Call[MP4.1][JW4.2]??
When a customer reaches Microsoft support with a scenario where they are locked out and requesting to gain access back to their tenant, the process of Microsoft getting access to customer tenant is slightly different and the level of access needed to troubleshoot the case is also different.

Audit events seen in the customer tenant during the case troubleshooting process
1.    Add a ServicePrincipal (of EntraGDAP application which handles the access setup)
Actor: AssistAPI application
2.    Add a partner to cross-tenant access setting (only Microsoft Support tenant)
Actor: EntraGDAP application
3.    Adding allowed assignable roles (full list of roles that are added here, captured below)
Domain Name Administrator
Privileged Authentication Administrator
Privileged Role Administrator
Authentication Policy Administrator
Microsoft 365 Support Engineer
Actor: EntraGDAP application
4.    Add member to role (Group from Microsoft Support tenant added to any of the above role depending on the case scenario)
Actor: AssistAPI application  
5.    Any operation performed by the support engineer as of trouble shooting
Actor: Microsoft Support Engineer/Technician & AssistAPI application  
 
Audit events seen in the customer tenant during the case closure are same as the other flow listed above.


## Consent for diagnostic information

When a user contacts [Microsoft Support](get-help-support.md), consent is implied that Microsoft will be granted access to limited tenant information that's needed to support your issue. When a user selects **Contact Me**, cross-tenant access is initiated in your organization's tenant. This access allows Microsoft Support to collect diagnostic information that helps with troubleshooting and resolving issues.

## What happens when cross-tenant access is granted to Microsoft Support?

When a user creates a support request, cross-tenant access is granted to Microsoft Support. That access is time bound and uses least-privileged access, in accordance with [Zero Trust principles](/security/zero-trust/zero-trust-overview). 

Here are some important points to keep in mind:

- Microsoft Support engineers can access only the specific resources needed for diagnostics and troubleshooting. 
- When a user creates a support request, their identity (UPN) is leveraged for creating the cross tenant access policy. The user's level of access doesn't change. For example, if the user has a nonprivileged role, their general restrictions don't change because of the support request.
- All support activity is logged in the Microsoft Entra audit and sign-in logs. (See the section, [Where is support activity on a customer tenant logged?](#where-is-support-activity-on-a-customer-tenant-logged) (in this article).)

## How long does Microsoft have this access?

Access is removed automatically when your support case is closed. If your case isn't closed 30 days after the request is created, access will be removed, and you'll be prompted to provide access again. If you have multiple cases open, access expires 30 days after the latest support request was created.

Depending on the nature of your support request, the data that Microsoft can access would belong under one or more of the following categories:

| Category | Examples |
|--|--|
| **Support data**: All data provided to Microsoft by the customer as part of a customer engagement to obtain support services | Support requests from customers and phone conversations, online chat sessions, or remote assistance sessions between support professionals and customers<br/><br/> Case notes and/or records related to support requests from customers<br/><br/>Data provided to Microsoft by the customer as part of support activities |
| **Account data**: Contact, billing, purchase, payment, and/or license information | Customer's provisioning information<br/><br/>Account configuration and billing data<br/><br/>Tenant administrator contact information (such as tenant administrator's name, address, e-mail address, phone number)<br/><br/>Licensing and purchase information |
| **System metadata**: Data generated in the course of running the service | Event logs<br/><br/>Access control logs<br/><br/>Account information belonging to Microsoft operations personnel<br/><br/>Microsoft server names/server IPs<br/><br/>Server patching and vulnerability data<br/><br/>Service configuration data<br/><br/>Telemetry (on-premises or cloud) |
| **Organization identifiable information (OII)**: Data that can be used to identify a particular tenant, deployment, or organization (generally config or usage data) | Tenant ID (non-GUID)<br/><br/>TenantID (GUID) due to the existence of many out of boundary `TenantID` to name mapping tables<br/><br/>Tenant usage data<br/><br/>Tenant IP addresses (IPv4), such as tenant's firewall IP address<br/><br/>Global prefix and subnet ID (first 64 bits of IPv6 address)<br/><br/>Tenant domain name in e-mail address (such as `joe@contoso.com`)<br/><br/>Mapping of organizational GUID to organization |
| **End-user identifiable information (EUII)**: Data that directly identifies or could be used to identify the authenticated user of a Microsoft service | User-specific IP address (IPv4)<br/><br/>User principal name (`joe@company.com`)<br/><br/>Address book data<br/><br/>User's machine name<br/><br/>SIP URI |
| **End-user pseudonymous identifiers (EUPI)**: An identifier created by Microsoft tied to the user of a Microsoft service | User GUIDs or PUIDs<br/><br/>Session IDs |

## How long is diagnostic data retained in Microsoft systems?

Microsoft retains diagnostic data for up to 28 days after it's collected. After this period, the data is deleted.

## Where is support activity on a customer tenant logged?

Activity performed on a customer tenant is available under Microsoft Entra audit logs. The following table describes log entries that are created.

| Scenario | Audit log details |
|--|--|
| A support case is created and cross-tenant access is granted | **Activity type**: Add a partner to cross-tenant access setting<br/>**Category**: `CrossTenantAccessSettings`<br/>**Initiated by (actor)**: <br/>- **Type**: `Application` <br/>- **Display Name**: `EntraGDAP`<br/><br/>**Activity Type**: Add allowed assignable roles<br/>**Category**: `DelegatedAdminServiceProviderConstraints`<br/>**Initiated by (actor)**: <br/>- **Type**: Application <br/>- **Display Name**: `EntraGDAP`<br/><br/>**Activity Type**: Update a partner cross-tenant access setting<br/>**Category**: `CrossTenantAccessSettings`<br/>**Initiated by (actor)**: <br/>- **Type**: Application <br/>- **Display Name**: `EntraGDAP` |
| A support engineer signs in to investigate and troubleshoot an issue | An entry each time: <br/>- A support engineer signs in <br/>- Diagnostics that involve operations are run<br/><br/>**Initiated by (actor)**:<br/>- **Type**: `Application`<br/>- **Display Name**: `AssistAPI`  |
| Access is removed | **Activity type**: Delete allowed assignable roles<br/>**Category**: `DelegatedAdminServiceProviderConstraints`<br/>**Initiated by (actor)**: <br/>- **Type**: `Application` <br/>- **Display Name**: `EntraGDAP`<br/><br/>**Activity type**: Delete partner specific cross-tenant access setting<br/>**Category**: `CrossTenantAccessSettings`<br/>**Initiated by (actor)**: <br/>- **Type**: `Application` <br/>- **Display Name**: `EntraGDAP` |

## Learn more about audit logs

See the following resources for more information about the audit logs:

- [What are Microsoft Entra audit logs?](/entra/identity/monitoring-health/concept-audit-logs)
- [How to customize and filter identity activity logs](/entra/identity/monitoring-health/howto-customize-filter-logs)