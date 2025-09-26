---
title: Inventory for scheduled prompts
description: Learn how to inventory scheduled prompts in Microsoft 365 Copilot using PowerShell. View, list, and delete scheduled prompts efficiently.
#customer intent: As an admin, I want to inventory scheduled prompts in my organization so that I can manage them efficiently.
f1.keywords:
- NOCSH
ms.author: aaroncz
author: aczechowski
manager: scotv
ms.date: 09/16/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
- operations-pod
---


# Inventory for scheduled prompts

Use PowerShell to inventory scheduled prompts created in your Microsoft 365 Copilot organization. These instructions help you connect to an admin account and efficiently view, list, or delete scheduled prompts.

## Prerequisites

To take inventory of scheduled prompts created by users in your organization, you need the following prerequisites:

- Assign the **Power Platform Administrator** role to your user in Azure portal for the tenant on which you want to do operations.
- Use [PowerShell v7.0](/powershell/scripting/install/installing-powershell) or later.
- Install the `Az.Accounts` and `Microsoft.PowerApps.Administration.PowerShell` modules. For more information, see [Install-Module](/powershell/module/powershellget/install-module).
- Store and run all scripts in the same folder.

To get the System Administrator role on the Copilot scheduled prompts environment, follow these steps:

- Go to [Power Platform admin center](https://admin.powerplatform.microsoft.com/environments).
- Find the **Microsoft 365** environment and select it. This value is the default name for the Copilot scheduled prompts environment. Your tenant might use a different name.
- Select **Membership**.
- Select **Add me** to add the System Administrator role to your user. It might take around 30 minutes for the role to be reflected everywhere.

For more information, see [Manage high privileged admin roles](/power-platform/admin/manage-high-privileged-admin-roles).

> [!IMPORTANT]
> Use roles with the fewest permissions. Lower permissioned accounts help improve security for your organization. Global Administrator is a highly privileged role. Limit its use to emergency scenarios when you can't use an existing role. For more information, see [About admin roles in the Microsoft 365 admin center](/microsoft-365/admin/add-users/about-admin-roles).

## Connect to your Azure account

Before you run any of the following PowerShell commands, sign in to your administrator account. To sign in, use the **[Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount)** cmdlet.

## General operations

1. To get the environment name for Copilot scheduled prompts, use the **[Get-AdminPowerAppEnvironment](/powershell/module/microsoft.powerapps.administration.powershell/get-adminpowerappenvironment)** cmdlet. If requested, connect with the admin account.

    ```powershell
    Get-AdminPowerAppEnvironment 'Microsoft 365'
    ```

    Specify your display name. By default, the display name is `Microsoft 365`. Alternatively, use the `EnvironmentName` parameter to specify your environment name.

1. You can also identify a user ID with the following Microsoft Entra cmdlets:

    ```powershell
    Connect-Entra

    Get-EntraUser -UserId 'user@domain.com'
    ```

    Use the appropriate user email, for example `user@domain.com`. Note the **Id** value in the output, which indicates the user's ID.

## List Copilot scheduled prompts

You can run a script in different ways to list scheduled prompts created in your tenant.

### Get a list of Copilot scheduled prompts for the whole tenant

1. To get the `EnvironmentId`, use the **Get-AdminPowerAppEnvironment** cmdlet.

1. Run the following script, replacing the placeholder with your actual `EnvironmentId`. If prompted, connect with the admin account.

    ```powershell
    .\Get-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345
    ```

    The console output displays the list of Copilot scheduled prompts.

### Get a list of Copilot scheduled prompts for a single user

1. To get the `EnvironmentId` and `UserId`, use the **Get-AdminPowerAppEnvironment** and **Get-EntraUser** cmdlets.

1. Run the following script with the appropriate `EnvironmentId` and `UserId`. If requested, connect with the admin account.

    ```powershell
    .\Get-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345 -UserId abc123-a100-xyz000-12345
    ```

    The console output displays the list of Copilot scheduled prompts belonging to the specified user.

### Export the list

To export the list to an Excel or CSV file, use the **[Export-Csv](/powershell/module/microsoft.powershell.utility/export-csv)** cmdlet. For example:

```powershell
.\Get-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345 | Export-Csv -Path C:\temp\resultFile.csv
```

## Delete Copilot scheduled prompts

### Delete a single Copilot scheduled prompt

1. Get the `EnvironmentId` and the `DataverseId` of the scheduled prompt to delete.

1. Run the following script:

    ```powershell
    .\Remove-CopilotAction.ps1 -EnvironmentId abc123-a100-xyz000-12345 -DataverseId abc123-a100-xyz000-12345
    ```

### Delete multiple Copilot scheduled prompts from a single user

1. Get the `EnvironmentId` and `UserId`.

1. Run the following script with the appropriate `EnvironmentId` and `UserId`. If requested, connect with the admin account.

    ```powershell
    .\Clear-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345 -UserId abc123-a100-xyz000-12345
    ```
