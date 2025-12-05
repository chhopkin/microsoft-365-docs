---
title: Migration orchestrator source and tenant domain configuration
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
description: "Discover the configuration requirements for Microsoft 365 migration orchestrator. Configuration is needed in both the source and client tenants to ensure a successful migration of your users' data."
---

# Configuring source and target tenants

## Prerequisites for source and target tenants

This article walks through all steps of preparing the tenants and users for a successful migration. Here are some other requirements we don't provide explicit steps for:

- The source admin and target admin must each have Global administrator access on their respective tenant, which is required to manage the setup and migration. XXX  GLOBAL ADMIN ONLY? WE HAVE LEAST PRIVILEGE MODE CONCERNS
- At least one mail-enabled security group is required in the source tenant.
  - These groups are used to:
    - Scope the list of users whose content can move from source tenant to the target tenant.
    - Inform the identity mapping service what users should be mapped.
  - This scoping allows the source tenant administrator to restrict access to a specific set of users whose content needs to be moved, preventing unintended users from being migrated or their data accessed.
- You need to communicate with your trusted partner organization (who helps you move user content) to obtain their Microsoft 365 tenant ID. This tenant ID is used in the Organization Relationship DomainName field.
  - To obtain the tenant ID of a subscription, sign in to the Microsoft 365 admin center and go to [Active Directory > Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). Select the copy icon for the Tenant ID property to copy it to the clipboard.

## Configuration steps to enable your tenants for cross-tenant mailbox migrations

### Prepare the target (destination) tenant by creating the migration application and secret

1. Sign in to your [Microsoft Entra admin center](https://portal.azure.com) with your target tenant administrator credentials.
1. Select **Microsoft Entra ID**.
1. In the navigation pane under **Manage**, select **App registrations**.
1. Select **New registration**.
1. On the **Register an application** page, under **Supported account types**, select **Accounts in any organizational directory (Any Microsoft Entra directory - Multi-tenant)**.
    1. Under **Redirect URI (optional)**, select **Web**.
    1. Type `https://office.com`.
    1. Select **Register**.
   On the top-right corner of the page, see the notification dialog box that states the app was successfully created.
1. Go back to the **Home** page and go to **Microsoft Entra ID**. Under **Manage**, select **App registrations**.
1. Under **All applications**, find the app you created, and select it.
1. Under **Essentials**, copy the **Application (client) ID**. You need this information later to create a URL for the target tenant.
1. In the navigation pane under **Manage**, select **API permissions** to view permissions assigned to your app.
1. By default, **User.Read** permissions are assigned to the app you created, but these permissions aren't required for mailbox migrations. You can remove those permissions.
1. To add permission for mailbox migration, select **Add a permission**.
1. In the **Request API permissions** window, select **APIs my organization uses**, search for **Office 365 Exchange Online**, and select it.
1. Select **Application permissions**.
1. Under **Select permissions**, expand **Mailbox** and select **Mailbox.Migration**, and select **Add permissions** at the bottom on the screen.
1. Select **Certificates & secrets** in the navigation pane for your application.
1. Under **Client secrets**, select **New client secret**.
1. In the **Add a client secret** window, type a description, and then configure your expiration settings.

> [!IMPORTANT]
> The password (Value) is used when creating your migration endpoint. It's important that you copy this password to your clipboard and/or to a secure/secret password safe location. The secret creation stage is the **only time** during which you can see this password. If you do somehow lose it or need to reset it, you can sign back into the Azure portal, go to **App registrations**, find your migration app, select **Secrets & certificates**, and then create a new secret for your app.

Now that the migration application and secret are successfully created, the next step is to consent to the application.

### Grant consent to the application

1. In the Microsoft Entra ID landing page, select **Enterprise applications** in the navigation pane.
1. Find the migration app you created, select it, and then under **Security**, select **Permissions**.
1. Select **Grant admin consent for [your tenant]**. A new browser window opens.
1. Select **Accept**.
1. Go back to your portal window and select **Refresh** to confirm your acceptance.
1. Formulate the URL to send to your trusted partner (the source tenant administrator) so they can also accept the application to enable mailbox migration.

Here's an example of the URL to provide to them:

`https://login.microsoftonline.com/<your partner's tenant name (source), EX: contoso.onmicrosoft.com>/adminconsent?client_id=<application_id_of_the_app_you_created>&redirect_uri=https://office.com`

> [!NOTE]
> You need the application ID of the mailbox migration app you previously created. You need to replace `<your tenant name, EX: contoso.onmicrosoft.com>` in the previous example with your source tenant's correct onmicrosoft.com name. You also need to replace `<application_id_of_the_app_you_just_created>` with the application ID of the mailbox migration app you previously created.

### Prepare the target tenant by creating the Exchange Online migration endpoint and organization relationship

1. Connect to Exchange Online PowerShell in the target Exchange Online tenant.
2. Create a new migration endpoint for Cross-tenant mailbox moves.

You need the application ID of the mailbox migration app you previously created and the password (value) you configured in [Prepare the target (destination) tenant by creating the migration application and secret](#prepare-the-target-destination-tenant-by-creating-the-migration-application-and-secret). Depending on the Microsoft 365 cloud instance you use, your endpoint may be different. See the [Microsoft 365 endpoints](../enterprise/microsoft-365-endpoints.md) page, select the correct instance for your tenant, review the Exchange Online Optimize/Required address, and replace as appropriate.

```powershell
# Enable customization if tenant is dehydrated

$dehydrated=Get-OrganizationConfig | select isdehydrated

if ($dehydrated.isdehydrated -eq $true) {Enable-OrganizationCustomization}

$AppId = "[Guid copied from the migrations app]"

$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $AppId, (ConvertTo-SecureString -String "[this is your secret password/value you saved in the previous steps]" -AsPlainText -Force)

# Create a new migration endpoint

New-MigrationEndpoint -RemoteServer outlook.office.com -RemoteTenant "Source UPN, ex: contoso.onmicrosoft.com" -Credentials $Credential -ExchangeRemoteMove:$true -Name "[the name of your new migration endpoint]" -ApplicationId $AppId
```

> [!NOTE]
> If you need to update the migration endpoint, you can either remove the migration endpoint by running `Remove-MigrationEndpoint`, or you can run the command to create a new migration endpoint with the `-SkipVerification` flag.

3. Create a new organization relationship object or edit your existing organization relationship object to your source tenant.

```powershell
$sourceTenantId="[tenant id of your trusted partner, where the source mailboxes are]"

$orgrels=Get-OrganizationRelationship

$existingOrgRel = $orgrels | ?{$_.DomainNames -like $sourceTenantId}

If ($null -ne $existingOrgRel)

{

    Set-OrganizationRelationship $existingOrgRel.Name -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability Inbound

}

If ($null -eq $existingOrgRel)

{

    New-OrganizationRelationship "[name of the new organization relationship]" -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability Inbound -DomainNames $sourceTenantId
```

## Prepare the source (current mailbox location) tenant by accepting the migration application and configuring the organization relationship

### Prepare the source tenant by accepting the migration application and configuring the organization relationship

1. Using your browser, go to the URL link provided by your trusted partner to consent to the mailbox migration application. The URL should look like this:

`https://login.microsoftonline.com/<sourcetenant.onmicrosoft.com>/adminconsent?client_id=[application_id_of_the_app_you_just_created in target tenant]&redirect_uri=https://office.com`

2. Accept the application when the pop-up appears. You can also now sign in to your Microsoft Entra admin center and find the application under **Enterprise applications**.
1. Connect to Exchange Online PowerShell on the source Exchange Online tenant.
1. Create a new organization relationship object or edit your existing organization relationship object to your target (destination) tenant in Exchange Online PowerShell:

```powershell
# Enable customization if tenant is dehydrated

$dehydrated=Get-OrganizationConfig | select isdehydrated

if ($dehydrated.isdehydrated -eq $true) {Enable-OrganizationCustomization}

$targetTenantId="[tenant id of your trusted partner, where the mailboxes are being moved to]"

$appId="[application id of the mailbox migration app you consented to]"

$scope="[name of a new mail enabled security group that will contain the list of users who are allowed to migrate]"

# create a new distribution group (optional if you already created your security group)

New-DistributionGroup -Type Security -Name $scope

$orgrels=Get-OrganizationRelationship

$existingOrgRel = $orgrels | ?{$_.DomainNames -like $targetTenantId}

If ($null -ne $existingOrgRel)

{

    Set-OrganizationRelationship $existingOrgRel.Name -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability RemoteOutbound -OAuthApplicationId $appId -MailboxMovePublishedScopes $scope

}

If ($null -eq $existingOrgRel)

{

    New-OrganizationRelationship "[name of your organization relationship]" -Enabled:$true -MailboxMoveEnabled:$true -MailboxMoveCapability RemoteOutbound -DomainNames $targetTenantId

-OAuthApplicationId $appId -MailboxMovePublishedScopes $scope

}
```

The tenant ID you enter as the $sourceTenantId and $targetTenantId is the GUID and not the tenant domain name. For an example of a tenant ID and information about finding your tenant ID, see [Find your Microsoft 365 tenant ID](/sharepoint/find-your-office-365-tenant-id).

If the security group with the users in scope for migration wasn't precreated, you need to populate it with users.

## Prepare both tenants for OneDrive migration

### Prepare both tenants by establishing trust

> [!IMPORTANT]
> These instructions must be run from both the source and the target tenant.

The required setup steps for OneDrive Migration on both source and target are available in [Steps 1 - 3](cross-tenant-onedrive-migration.md) of its public documentation. These steps establish trust for the tool and between tenants.

### Prepare both tenants by configuring the OneDrive migration application 

> [!IMPORTANT]
> These instructions must be run from both the source and the target tenant.

1. Download [the module](https://download.microsoft.com/download/1ded7541-fa8d-48f7-90c4-fa8a15a6b62b/ConfigureOneDriveMigration.psm1) onto your local machine.
2. Connect to Graph PowerShell as a Global Administrator:
  `Connect-MgGraph`
3. Import the module containing the configuration details:
  `Import-Module <location>`
4. Grant the App Permissions:
  `Grant-OneDriveSharePointMigrationPermissions`

## Prepare both tenants for Teams Chat and Meeting Migration

### Prepare both tenants by setting correct permissions

> [!IMPORTANT]
> These instructions must be run from both the source and the target tenant.

1. Federated users must be allowed.
    1. Install Microsoft Teams PowerShell, if you didn't already install it: [Install Microsoft Teams PowerShell](/MicrosoftTeams/teams-powershell-install).
    2. Connect to Microsoft Teams PowerShell:
      `Connect-MicrosoftTeams`
    3. Run the cmdlet:
      `Set-CsTenantFederationConfiguration -AllowFederatedUsers $True`
2. If the tenant is a Trial tenant, it must also have **External Access** allowed.
    1. Install Microsoft Teams PowerShell, if you didn't already install it: [Install Microsoft Teams PowerShell](/MicrosoftTeams/teams-powershell-install).
    2. Connect to Microsoft Teams PowerShell:
      `Connect-MicrosoftTeams`
    3. Run the cmdlet:
      `Set-CsTenantFederationConfiguration -ExternalAccessWithTrialTenants "Allowed"`
3. Confirm the settings by running:
  `Get-CsTenantFederationConfiguration`

### Prepare both tenants by configuring the Teams Chat migration app

> [!IMPORTANT]
> These instructions must be run from both the source and the target tenant.

1. Download [the module](https://download.microsoft.com/download/1ded7541-fa8d-48f7-90c4-fa8a15a6b62b/ConfigureOneDriveMigration.psm1) onto your local machine.
2. Connect to Graph PowerShell as a Global Administrator:
  `Connect-MgGraph`
3. Import the module containing the configuration details:
  `Import-Module <location>`
4. Grant the App Permissions:
  `Grant-CTTMAppPermissions`
5. To get detailed help, run `Get-Help Grant-CTTMAppPermissions -Detailed`. Authenticate in and accept.
6. If Microsoft.Graph.Authentication and Microsoft.Graph.Applications aren't already installed, you're prompted to do so.
  `Install-Module Microsoft.Graph.Authentication`
  `Install-Module Microsoft.Graph.Applications`
  `Grant-CTTMAppPermissions`
7. There are nine permissions added:
    1. Cross Tenant Teams Migration app role
    2. Identity Mapping Service app role
    3. Chat.Create
    4. Chat.Read.All
    5. Teamwork.Migrate.All
    6. ChatMember.ReadWrite.All
    7. User.Read.All
    8. Application.Read.All
    9. CrossTenantMigrationAuthorization-Internal.Read

### Prepare both tenants by configuring the Teams Meeting Migration app

> [!IMPORTANT]
> These instructions must be run from both the source and the target tenant.

1. Set the Execution Policy:
  `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`
2. Download [the module](https://download.microsoft.com/download/1ded7541-fa8d-48f7-90c4-fa8a15a6b62b/ConfigureOneDriveMigration.psm1) onto your local machine.
3. Connect to Graph PowerShell as a Global Administrator:
  `Connect-MgGraph`
4. Import the module containing the configuration details:
  `Import-Module <location>`
5. Install the dependencies for running MMS Script. You may have installed some of these dependencies in setup tasks for other workloads. You don't need to reinstall in that case.
  `Install-Module Microsoft.Graph.Authentication`
  `Install-Module Microsoft.Graph.Applications`
  `Install-Module Microsoft.Graph.Identity.DirectoryManagement`
  `Install-Module ExchangeOnlineManagement`
  `Install-Module MicrosoftTeams`
6. **Only for the source tenant**: Grant App Permissions:
  `Grant-MMSAppPermissions -TenantType "source"`
7. **Only for the target tenant**: Grant App Permissions for the target tenant:
  `Grant-MMSAppPermissions -TenantType "target"`
8. Connect to Exchange Online:
  `Connect-ExchangeOnline`
9. Enable Auto Forwarding for both source and target tenant:
  `Enable-AutoForwardingMode`
  - Success: `Autoforwarding is set to On for Default Outbound Spam Filter Policy.`
10. Only for the target tenant: Set the calendar RBAC roles:
  `Set-CalendarRBACRoles`
  - Success: `RBAC role has been assigned to MMS App to allow Calendar Read Write Permissions.`
11. If Microsoft.Graph.Authentication, Microsoft.Graph, ExchangeOnlineManagement aren't installed, you're prompted to do so.
12.	Grant-MMSAppPermissions adds Service Principals for:
    1. Cross Tenant Teams Migration app
    1. Meeting Migration Service app
    1. Identity Mapping Service app
13.	Grant-MMSAppPermissions adds App Roles for:
    1. Cross Tenant Teams Migration app role from Cross Tenant Teams Migration app assigned to target Meeting Migration Service App
    1. Identity Mapping Service app role from Identity Mapping Service app to target Meeting Migration Service app
    1. CrossTenantMigrationAuthorization-Internal.Read
14. Grant-MMSAppPermissions adds the Graph permissions for:
    1. Online.ReadWrite.All
    1. User.Read.All
    1. RoleManagement.Read.Directory
    1. Chat.ReadBasic.All
    1. Application.Read.All
15. It also adds the Exchange Admin Directory Role and Application access policies to MMS Application.

## Prepare both tenants for Identity Mapping

> [!IMPORTANT]
> These instructions must be run from both the source and the target tenant.

Running Identity Mapping is a required step for migrating user data. Cross-Tenant Identity Mapping (CTIM) is a tool that allows source users to be mapped one-to-one to target users. It edits the users' properties, so they have the correct properties to successfully migrate. It also maintains a mapping file to reference so that the data for the correct source users is migrated to the correct target users.

[Learn more](cross-tenant-identity-mapping.md) about Identity Mapping.

> [!IMPORTANT]
> Use CTIM after creating target users and before migrating data to ensure accuracy and avoid manual errors.

XXX COPY IN AFTER WE'VE FINALIZED IN SOURCE DOC.

## Prepare the target tenant for Cross-Tenant Migration Service

To prepare the target tenant for the Cross-Tenant Migration Service, follow these steps:

1. Download [the module](https://download.microsoft.com/download/1ded7541-fa8d-48f7-90c4-fa8a15a6b62b/ConfigureOneDriveMigration.psm1) onto your local machine.
2. Connect to Graph PowerShell as a Global Administrator:
  `Connect-MgGraph`
3. Import the module containing the configuration details:
  `Import-Module <location>`
4. Grant the App Permissions:
  `Grant-CTTMAppPermissions`
5. To get detailed help, run `Get-Help Grant-CTTMAppPermissions -Detailed`. Authenticate in and accept.
6. If Microsoft.Graph.Authentication and Microsoft.Graph.Applications aren't already installed, you're prompted to do so.
  `Install-Module Microsoft.Graph.Authentication`
  `Install-Module Microsoft.Graph.Applications`
  `Grant-CTTMAppPermissions`

You should receive output showing **CrossTenantMigration Prod AAD App** as an app with roles assigned and other apps provisioned by this point. The IdentityMapping-Experimental-Internal.Read app role is granted to the CTMS application.
