---
title: Running a migration with the migration orchestrator
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
description: "The steps for running a migration using the Microsoft 365 migration orchestrator."
---

# Running the migration

The migration is run by creating a migration job in the form of a batch. Users are grouped together into a batch and submitted together. Migrations are managed through Graph APIs. These APIs can be run through PowerShell 5 or 7, or through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer#mode=canary).

## Understanding validation

Because there are many [Prerequisites](migration-orchestrator-2-planning-prerequisites.md) for migration, there's a separate step you can run as many times as needed to confirm that those prerequisites are met. This step is called *Standalone Validation*, and it acts similarly to running a what-if. It checks for all the known requirements for a successful migration in the general migration ecosystem (app permissions, relationships between tenants, and so on) and at a user level (licenses, identity mapping, and so on). We recommend that for every batch, an admin should run the validation before submitting the migration in order to confirm that all requirements are met.

Running a validation batch will result in either:

1. Confirmation that a batch and its users have met all pre-requisites
1. A list of errors resulting from failed checks.

Admins can review the list for any failures, fix any issues, and resubmit using a new batch to confirm success.

> [!NOTE]
> The list of errors may not be exhaustive. Admins should run validation and fix errors until all prerequisites are met and there are no failures.

When you submit the migration, we do another check of all of the prerequisites, but we don't return a list of the failures per workload.

## Understanding the migration process

XXX NOTE THAT WE ABSOLUTELY CANNOT HAVE INFORMATION THAT EXISTS ONLY IN A DIAGRAM. IT IS NOT ACCESSIBLE. IT IS NOT SEARCHABLE. WE CAN DISCUSS IF IT'S SUPPLEMENTAL.

The migration occurs at a user-level, meaning that if one user passes the validation phase, their migration continues. If another user fails any validation check, their migration fails (and never actually begins). To migrate these failed users, create a new batch that includes the failed users, after correcting the validation failures, or retry the migration if there was a terminal failure.

### Validation

The first step that takes place is the Validation stage. Throughout this step, all necessary setup steps are validated. If any checks fail, then the migration fails. The administrator should then fix the failures and resubmit the migration. For a list of the prechecks, please consult the [Prerequisites](migration-orchestrator-2-planning-prerequisites.md) article. This step includes all the checks confirmed in Standalone Validation, but it's not going to return the full results for every check. It only returns the first failure it encounters.

### Mailbox syncing

After all the checks pass for the applicable workloads, Mailbox syncing begins. Mailbox syncing means that in the background, the user's mailbox data is being moved to the target tenant. The user is still able to fully use their mailbox on the source tenant at this time.

### Cutover

After the time designated by the CompleteAfterDate passes and the sync completes, the mailboxes cutover to the target tenant. After this point, no cancellations can take place. Users are able to access their mailboxes from the target tenant. Mailboxes will not appear on the source tenant any longer.

### Teams and Onedrive migration

After the mailbox is cutover, the migration of Teams chats, Teams meetings, and OneDrives begins. Chats and meetings are migrated into the target tenant. Users may see changes to their source chats as users are added or removed, and chats and meetings begin to appear in the target tenant.

### Migration conclusion

After the Teams chats, Teams meetings, and OneDrives migrate, the migration is complete. Users can use their target tenant accounts to use their mailboxes, chats, meetings, and OneDrives.

## Understanding Migration Status and Errors

For a breakdown of the meanings behind the statuses and errors, please consult the appendix. XXX REMINDER TO FIGURE OUT WHERE THIS IS

There's up to an hour-long delay between when updates are made to the group containing the authorized users for migration and when our system processes those changes. Allow for up to an hour to start the migration after changes are made to the group membership.

## Commands available to run

### Submit a batch for validation

This feature allows you to submit a batch of users to validate that the prerequisites are met before submitting a migration. It does **not** actually submit the migration. It creates a batch that's run once in the validation context. Getting information about this batch via [Retrieve a specific batch](#retrieve-a-specific-batch) returns a full list of results on the checks it ran. Any failures need to be addressed in order for a successful migration later. Each batch you submit needs to have a unique name. Users can only belong to one active batch at one time.

### Submit a batch for migration

This feature allows you to submit a batch of users to begin their migration. We recommend running [Submit a batch for validation](#submit-a-batch-for-validation) first to confirm that all prerequisites are in-place. Each batch you submit needs to have a unique name. Users can only belong to one active batch at one time.

### Retrieve all batches

This feature allows you to see all submitted batches. You see both validation and migration batches. It shows active and past migrations.

### Retrieve a specific batch

This feature allows you to receive information about a specific batch and its properties.

### Retrieve user status within a specific batch

This feature allows you to receive information about the users within a specific batch. You see the state for each of the workloads. This includes:

- Validation
- Teams
- Exchange
- Meetings

### Update the complete after date for a specific batch

This feature allows you to change the complete after date. Moving the date pushes the earliest date at which the cutovers for mailboxes occur and when the Teams chat and meetings migration begin.

### Cancel a batch

This feature allows you to cancel an entire batch and all of its users' migrations. It will cancel all migrations for users whose mailboxes have not yet cutover.

### Remove a user from a batch and cancel that user's migration

This feature allows you to cancel a single user's migration by removing them from that batch. It needs to be run multiple times if multiple users need to be removed. The remaining users in the batch are unaffected. This is only possible before the user's mailbox has cutover, at which point the user can't be removed.

If the removal is successful, you see a 202 Accepted request with the response:

"Cancellation request for user id: <XXXX-XXXXX-XXXXX-XXXX> from batch: <batch name or batch request ID> was accepted."

At this point, the user is removed from the batch, their migration is cancelled, and any mailbox syncing that took place is cancelled. The user can be added to a new batch. No other user within that batch is affected. The identity mapping isn't edited at all.

If the removal is unsuccessful, here are the possible responses:

1. The User ID provided in the request doesn't exist within the batch provided. This likely means the admin provided an incorrect User ID and should check it again.

  `"Cancellation not possible as no task found for given id <User ID> TraceId: <Trace ID>"`

2. The batch ID or batch name can't be found in the tenant. This likely means the admin provided an incorrect batch ID or batch name in the cancellation request and should check it again.

  `"UserRequest not found with <target tenant ID>, <batch ID or batch name> TraceId: <Trace ID>"`

3. If the cancellation request comes in after the specified completeAfterDate has passed, the user's migration can't be cancelled and they can't be removed from the batch.

  `"Cancellation is not possible as migration passed completeAfter date TraceId: <Trace ID>"`

4. The User Task is invalid, so the user's migration can't be cancelled. This means there's a fundamental issue with the user's setup to the point that it wouldn't run within the batch anyway. An issue like this potentially comes from the user not bring Identity Mapped. The impact is that the user can't be migrated, even though they technically belong to the batch. 

  `"Cancellation is not possible as task is invalid TraceId: <Trace ID>"`

  In the case of a removal being unsuccessful (other than in case of an invalid user state), the user continues belonging to the batch and is migrated.

## Common parameters

There are a number of parameters that must be provided in a specific format for the migration input:

- **displayName** - A batch name of your choosing to help you identify this specific batch.
- **completeAfterDateTime** - The date that specifies the **earliest** acceptable time for the cutover of Exchange to begin. There is no user impact until this date passes **and** the Exchange sync is complete. This date can be updated later. The acceptable date and time formats are available on [Microsoft Learn](/dotnet/standard/base-types/standard-date-and-time-format-strings#table-of-format-specifiers).
- **sourceTenantId** - The ID of the source tenant. This can be found in the Entra portal.
- **targetDeliveryDomain** - Your target tenant domain. Example: domain.onmicrosoft.com.
- **sourceEndpoint** - The name of the endpoint created on the target tenant. You can find it using the `Get-MigrationEndpoint` command with the `-Name` parameter.
- **resources** - A list of ExternalDirectoryObjectIds for the **target** users you're including in this batch. These resources are available in the Azure portal under the user as "**Object Id**" or through PowerShell.
- **resourceType** - Is always "**Users**" for all user content migrations.
- workloads - A string with the list of workloads you intend to migrate. These strings should be formatted in a comma-delimited list. The proper strings are:
  - "**Exchange**"
  - "**ODSP**"
  - "**Teams**"
  - "**Meeting**"
  If you don't provide a string, the migration defaults to moving all four workloads.

## Migrating using Powershell

1. Open Microsoft PowerShell.
2. Install the [Graph SDK](/powershell/microsoftgraph/?view=graph-powershell-beta):
  - `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`
  - `Install-Module Microsoft.Graph`
3. Sign in with target tenant global administrator credentials:
  - `Connect-Graph`
4.	Confirm you're in the right tenant:
  - `Get-MgContext`
5. 5.	For any further cmdlets, use this URL prefix: [https://graph.microsoft.com/beta/solutions/migrations/crossTenantMigrationJobs](https://graph.microsoft.com/beta/solutions/migrations/crossTenantMigrationJobs).

### A: Submit a validation batch

1. 1.	In a basic text editor, like Notepad, save the text in the following format as a .json file for the batch you want to submit. Ensure that you are pasting as plain text.

```json
{
  "displayName": "xtmigration1",
  "completeAfterDateTime": "2024-12-09T22:48:03.092Z",
  "sourceTenantId": "XXXXX-XXXXX-XXXXXX-XXXXXX",
  "exchangeSettings": {
    "targetDeliveryDomain": "DOMAIN.onmicrosoft.com",
    "sourceEndpoint": "sampleEndpointText"
  },
  "resources": [
    "XXXXXXX-XXXXXXX-XXXXXXX-XXXXXXX",
    "XXXXXXX-XXXXXXX-XXXXXXX-XXXXXXX",
    "XXXXXXX-XXXXXXX-XXXXXXX-XXXXXXX"
  ],
  "resourceType": "Users",
  "workloads": [
    "Teams",
    "Exchange",
    "ODSP",
"Meeting"
  ]
}
```

2. Save the path of the file:
  `$jsonFilePath = "C:\path\to\your\payload.json"`
3. Read the JSON file content:
  `$jsonContent = Get-Content -Path $jsonFilePath -Raw`
4. Submit the batch for validation:
  `Invoke-MgGraphRequest -Method POST https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs/validate -Body $jsonContent`

To get the results of the validation, use the same GET requests as for a batch submitted for [D: Monitor a specific batch](#d-monitor-a-specific-batch) and [E: Monitor a specific batch and its users](#e-monitor-a-specific-batch-and-its-users).

### B: Submit a migration batch

1. In a basic text editor, like Notepad, save the text in the following format as a .json file for the batch you want to submit. Ensure that you are pasting as plain text.

```json
{
  "displayName": "xtmigration1",
  "completeAfterDateTime": "2024-12-09T22:48:03.092Z",
  "sourceTenantId": "XXXXX-XXXXX-XXXXXX-XXXXXX",
  "exchangeSettings": {
    "targetDeliveryDomain": "DOMAIN.onmicrosoft.com",
    "sourceEndpoint": "sampleEndpointText"
  },
  "resources": [
    "XXXXXXX-XXXXXXX-XXXXXXX-XXXXXXX",
    "XXXXXXX-XXXXXXX-XXXXXXX-XXXXXXX",
    "XXXXXXX-XXXXXXX-XXXXXXX-XXXXXXX"
  ],
  "resourceType": "Users",
  "workloads": [
    "Teams",
    "Exchange",
    "ODSP",
    "Meeting"
  ]
}
```

2. Save the path of the file:
  `$jsonFilePath = "C:\path\to\your\payload.json"`
3. Read the JSON file content
  `$jsonContent = Get-Content -Path $jsonFilePath -Raw`
4. Submit the batch:
  `Invoke-MgGraphRequest -Method POST https://graph.microsoft.com/beta/solutions/migrations/crossTenantMigrationJobs -Body $jsonContent`

This returns an object containing the information provided, as well as:

- **ID**: A batch/job ID used to monitor or make operations on that batch in the future.
- **jobType**: The type of job running. For submitting a batch, it's **Migrate**.
- **Status**: The status of the batch. The status changes during the migration. Initially it's **Submitted**.
- **Message**: A message containing information about the batch and its progress. Initially it's empty.
- **createdBy**: The user ID for the user submitting the migration.
- **createdDateTime**: The creation time for this batch.
- **lastUpdatedDateTime**: The last updated time for this batch.

### C: Get all batches for the target tenant

1. Request the batches:
  `Invoke-MgGraphRequest -Method GET https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs`
2. To create a nicely formatted table, run:
  `$jobs = Invoke-MgGraphRequest -Method GET https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs`
3. Create a table:

```json
$jobTable = @()
foreach ($job in $jobs.value) {
    $jobRow = [PSCustomObject]@{
         "Display Name" = $job.displayName
         "Complete After Date" = $job.completeAfterDateTime.datetime
         "Source Tenant ID" = $job.sourceTenantId
         "Status" = $job.status
     }
     $jobTable += $jobRow
 }
```

4. Format and view the table:
  `$jobTable | Format-Table -AutoSize`

- Run the request for all batches again using the GET cmdlet and convert to Json:
  `Invoke-MgGraphRequest -Method GET https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs | ConvertTo-Json`
- Copy the @odata.nextLink and run the request for all batches again.
  `Invoke-MgGraphRequest -Method GET https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs | ConvertTo-Json`
- Continue with the new @odata.nextLink for the next twenty, and so on.

### D: Monitor a specific batch

This command shows information about the batch in general:

`Invoke-MgGraphRequest -Method GET https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs/id`

The ID is the batch ID returned when you created the batch. You can also use the batch name in place of the ID.

### E: Monitor a specific batch and its users

This command shows information about each of the users and their status within a batch:

`Invoke-MgGraphRequest -Method GET https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs/id/users | ConvertTo-Json -Depth 100`

The ID is the batch ID returned when you created the batch. You can also use the batch name place of the ID.

### F: Update the CompleteAfterDate for a given batch

1. Save the completeAfterDate file to your computer:

```json
{
  "completeAfterDateTime": "2025-12-17T20:38:04.101Z"
}
```

2. Save the path of the file:
  `$jsonFilePathCAD = "C:\path\to\your\payload.json"`
3. Read the JSON file content:
  `$jsonContentCAD = Get-Content -Path $jsonFilePathCAD -Raw`
4. Submit the batch
  `Invoke-MgGraphRequest -Method PATCH https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs/ID -Body $jsonContentCAD`

The acceptable date and time formats are available on [Microsoft Learn](/dotnet/standard/base-types/standard-date-and-time-format-strings#table-of-format-specifiers).

### G: Cancel a batch

`Invoke-MgGraphRequest -Method POST https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs/ID/cancel`

The response is 202 if the cancellation's accepted. The message reads "cancellation request has been accepted for the migration job." All tasks within the batch which were in a sync state are cancelled. As long as the user's mailbox isn't cutover already, the cancellation is expected to succeed.

The response is 409 if the cancellation isn't accepted. Migrations continue if this is the response.

### H: Remove a user from a batch

`Invoke-MgGraphRequest -Method POST https://graph.microsoft.com/beta/solutions/migrations/crosstenantmigrationjobs/BatchID/users/UserID/cancel`

The crosstenantmigrationjobs BatchID is the request ID for the batch, and the users UserID is the target ExternalDirectoryObjectId for the user.

If the removal is successful, you see a 202 Accepted request with the response: "Cancellation request for user id: `<XXXX-XXXXX-XXXXX-XXXX>` from batch: `<batch name or batch request ID>` was accepted."

If a removal is unsuccessful (other than in case of an invalid user state), the user continues belonging to the batch and is migrated.
