---
title: Migration orchestrator planning and prerequisites
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.date: 12/01/2025
recommendations: true
audience: ITPro
ms.topic: upgrade-and-migration-article
ms.service: microsoft-365-migration
ms.localizationpriority: medium
ms.collection: 
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: "A planning and prerequisites article for Microsoft 365 migration orchestrator, a tool that allows you to migrate users from one tenant to another."
---

# Planning and prerequisites

> [!IMPORTANT]
> Tenant-to-tenant migration is currently available in preview. Features and availability may change before general availability (GA).

This article covers both planning and prerequisites for Microsoft 365 migration orchestrator.

## Best Practices for Running Migration

> [!IMPORTANT]
> We require all users migrating content must be mapped in the identity mapping system before any migration takes place. Without doing this, Teams chat and meeting migration end user experience can't add the correct users in every scenario.

You must follow specific ordering during the user creation and licensing. Users **must not have mailboxes or OneDrive sites provisioned on the target** before migration. This provisioning would make the migration fail. To prevent this failure, make sure you perform Identity Mapping, which stamps the Exchange GUID from each source user to each target user. This mapping prevents the provisioning of a mailbox before applying a license granting Exchange access to the user. You should also disable OneDrive creation for target users as soon as you create those users, to prevent a OneDrive from being provisioned.

It's important to be in the correct MsGraph context when running commands from the source and target tenants. To confirm you're correctly connected, use Disconnect-MgGraph, Connect-MgGraph, and Get-MgContext.

## Prerequisites

> [!NOTE]
> The requirements for a source tenant and a target tenant are slightly different.

### Data-At-Rest

The Cross-Tenant Identity Mapping (CTIM) service stores data-at-rest in multiple locations depending on the data type. Review this list before moving forward using CTIM.

- Source Tenant reports: Stored within the source tenant's Exchange Online region.
- Target Tenant reports: Stored within the target tenant's Exchange Online region.
- Mapping file content: A temporary copy of the mapping file is stored within the European Union when uploaded. This copy is purged in 48 hours or less. 
- Service Logs redacted of all identifiable info: The European Union.
- All other data-at-rest: Stored within the target tenant's Exchange Online region.

> [!NOTE]
> For Multi-Geo enabled tenants, the tenant's home geo is used whenever an EXO region is mentioned in this document.

### Network/Firewall Requirements

The Cross-Tenant Identity Mapping service uses a REST endpoint and encrypts all traffic between the customer and the service endpoint. This endpoint resides within the URL and IP address ranges under the Microsoft 365 Common and Office Online section of the published Office 365 URLs and IP Addresses guidance. If you allow access to these documented URLs and IP address ranges, there should be no problem connecting to the endpoint.

### On-premises Exchange Organizations

> [!NOTE]
> Target tenants only.

If the target tenant is a hybrid tenant with directory sync enabled and syncing MailUser objects into the target tenant, then you must have access to a Microsoft supported PowerShell method of managing on-premises objects synchronized into Microsoft 365.

An example of supported methods is any currently supported version of Exchange Server Management Shell, or the newer Exchange Server 2019 Management Tools. We don't support tenants using unsupported methods of managing and modifying on-premises objects. If all the MailUser objects you're working with in the target tenant are cloud-only objects not synchronized from on-premises, then you don't need a Microsoft-supported PowerShell method of managing on-premises objects synchronized into Microsoft 365.

### MailUser object examples

For more information about MailUser object examples, see [Cross-tenant mailbox migration](/microsoft-365/enterprise/cross-tenant-mailbox-migration?view=o365-worldwide#prerequisites-for-target-user-objects)

### Confirmation of Proper User Attributes

After identity mapping completes, the source and target users should have specific attributes that link them to one another.
The target MailUser must have these attributes from the source mailbox or assigned with the new User object:

1. ExchangeGUID (direct flow from source to target): The mailbox GUID must match. The move process doesn't proceed if this attribute isn't present on the target object.
2. ArchiveGUID (direct flow from source to target): The archive GUID must match. The move process doesn't proceed if this attribute isn't present on the target object. (This attribute is only required if the source mailbox is Archive-enabled).
3. LegacyExchangeDN (flow as proxyAddress, `"x500:<LegacyExchangeDN>"`): The LegacyExchangeDN must be present on the target MailUser as x500: proxyAddress. All the x500 addresses from the source mailbox must be on the target mail user. The move process doesn't proceed if these x500 addresses aren't present on the target object. This step is important for enabling reply ability for emails sent before migration. The sender/recipient address in each email item and the autocomplete cache in Microsoft Outlook and in Microsoft Outlook Web App (OWA) use the value of the LegacyExchangeDN attribute. If a user can't be located using the LegacyExchangeDN value, the delivery of email messages may fail with a 5.1.1 NDR.
4. UserPrincipalName: UPN aligns to the user's ***new*** identity or target company (for example, user@target.onmicrosoft.com).
5. Primary SMTPAddress: Primary SMTP address aligns to the user's NEW company (for example, user@target.onmicrosoft.com).
6. TargetAddress/ExternalEmailAddress: MailUser references the user's current mailbox hosted in source tenant (for example user@source.onmicrosoft.com). When this value is assigned, confirm you're also assigning PrimarySMTPAddress. Otherwise, this value sets the PrimarySMTPAddress, which causes move failures.
7.	You can't add legacy SMTP proxy addresses from the source mailbox to the target MailUser. For example, you can't maintain source.com on the MEU in target.onmicrosoft.com tenant objects. Domains are associated with one Microsoft Entra ID or Exchange Online tenant only.

To confirm the source user's attributes, run:

`Get-Mailbox <User Alias> | fl Name,ExchangeGuid`

To confirm the target user's attributes, run:

`Get-MailUser AdeleV2 | fl Name,ExternalEmailAddress,EmailAddresses,PrimarySMTPAddress,ExchangeGuid`


### Prevalidation checks

The following sections provide step-by-step instructions to configure tenants and users to meet the prerequisites.

The following table lists the checks performed in the Pre-Migration validation stage of the migration. After the submission of the migration batch, these checks are the first tasks processed. If any of them hit an error, then the migration is canceled so any errors can be remediated. After the admin fixes the errors, they can submit a new batch with the same users.

|Check |Error message |Troubleshooting |
|------|--------------|----------------|
|A user can't belong to a preexisting batch |User migration validation failed. User is already a part of the same batch. </br>User migration validation failed. User is already a part of another batch {0} |If a user belongs to multiple batches, the user's only migrated once. Likewise, if the same batch lists the user twice, the user migrates once. </br>Admins must resubmit the migration batch without the duplicate user. |
|The migration endpoint must exist |The migration endpoint '{0}' couldn't be found. |There must be a migration endpoint set up correctly for the migration to be successful. [Review](migration-orchestrator-3-tenant-config.md) the information on preparing the target tenant for information on how to set up this endpoint. |
|The organization relationship must be configured correctly between the two tenants | |There must be an Organization Relationship set up correctly for migration to be successful. [Review](migration-orchestrator-3-tenant-config.md) the information on preparing the target tenant for information on how to set up this relationship.  |
|The Teams Migration app must be provisioned correctly and enabled on the source and target tenants |Teams migration failed. App {0} in tenant {1} is not provisioned, or the app is provisioned but is not enabled. Please refer to tenant configuration documentation and retry migration. </br>Teams migration failed. The Cross-Tenant Teams Migration app in tenant {0} does not have the required app roles to check for Teams licenses for users. Refer to tenant configuration documentation and retry migration. </br>Teams migration failed. App {0} in tenant {1} is missing all the necessary role assignments. Refer to tenant configuration documentation retry migration. </br>Teams migration failed. The Cross-Tenant Teams Migration app is not properly configured to allow the service to check for appropriate app role assignments for app {0} in tenant {1}. Refer to tenant configuration documentation and retry migration. </br>Teams migration failed. The Cross-Tenant Teams Migration app is not properly configured to allow the service to check if there is a service principal provisioned for app {0} in tenant {1}. Refer to tenant configuration documentation and retry migration. </br>Teams migration failed. App {0} in tenant {1} is missing the {2} role assignment. Refer to tenant configuration documentation and retry migration. </br>Teams migration failed. The Cross-Tenant Teams Migration app is not properly configured to ensure authorization for user {0} in source tenant {1}. Refer to tenant configuration documentation and retry migration. </br>Teams migration failed. The Cross-Tenant Teams Migration app is unable to read authorization configuration. Refer to tenant configuration documentation and retry migration. |There's an issue with the setup of the app controlling Teams chat migration. Refer to the [tenant configuration document](migration-orchestrator-3-tenant-config.md) to set up these apps correctly. |
|A user must have a Teams license on both tenants |Teams migration failed. User {0} in tenant {1} does not have a Teams license. Assign a Teams license to the user and retry migration. |All users need a Teams license on both tenants. Assign the user a license on both tenants. |
|Each source user needs to be mapped to a target user (Identity Mapping) |Teams migration for user {0} failed. User {1} from source tenant {2} is not mapped to an identity in target tenant {3}. Refer to documentation for Identity Mapping and retry migration. </br>Teams migration for user {0} failed. There is a conflict in the target user provided by the migration service and the Identity Mapping service. Rerun Identity Mapping and retry migration. |Add the users to identity mapping. |
|All users submitted in the batch must belong to the provided scope security group |Teams migration failed. The user {0} from source tenant {1} is not authorized to migrate to user {2} from target tenant {3}. Refer to documentation for Identity Mapping and retry migration. |Add all source users to the security group linked in the Organization Relationship. |
|The Meeting Migration app must be provisioned correctly and enabled on the source tenant |Teams Meeting migration failed. The MMS App {0} in tenant {1} is not provisioned, or the app is provisioned but is not enabled. Please refer to tenant configuration documentation and retry migration. |Review the Teams Meeting Migration setup steps. |
|The Meeting Migration app must be provisioned correctly and enabled on the target tenant |Teams Meeting migration failed. The MMS App {0} in tenant {1} is not provisioned, or the app is provisioned but is not enabled. Please refer to tenant configuration documentation and retry migration. |Review the Teams Meeting Migration setup steps. |
|All users must have an Exchange Online license in both tenants |Teams Meeting migration failed for user {0}. User {0} in tenant {1} does not have an active Exchange Online Plan. Assign an Exchange Online Plan to the user and retry migration. |Review the licensing requirements. |
|Autoforwarding mode must be on in Exchange outbound spam filter policy for both tenants |Teams Meeting migration failed. Tenant {1} does not have AutoforwardingMode set to On in Default Exchange Outbound Spam Filter Policy. Refer to tenant configuration documentation and retry migration. |Review the Teams Meeting Migration setup steps. |
|Meeting Migration app on the target must have Calendars.ReadWrite RBAC role |Teams Meeting migration failed. MMS app in tenant {0} is missing the required RBAC roles to access the calendar. Refer to tenant configuration documentation and retry migration. |Review the Teams Meeting Migration setup steps. |
|The Meeting Migration app on both source and target tenant must have Exchange Administrator directory role |Teams Meeting migration failed. The MMS App {0} in source/target tenant {1} does not have the Exchange Administrator directory role assigned. Please assign the role and retry migration. |Review the Teams Meeting Migration setup steps. |

## Next steps

See [Configuring source and target tenants](migration-orchestrator-3-tenant-config.md) for information on configuring the tenants involved in the migration.
