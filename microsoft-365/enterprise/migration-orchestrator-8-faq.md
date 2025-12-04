---
title: Migration orchestrator FAQ
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
description: "Frequently asked question about Microsoft 365's migration orchestrator."
---

# FAQ and troubleshooting

## Cancellation

If you have started a migration and realize that you need to cancel due to any reason, you need to cancel before the CompleteAfterDate passes. If the CompleteAfterDate is past and the mailbox has been cutover, then the user data migration completes automatically with Teams chats and meetings. Once the migration completes, it's possible to move the user data back to the source.

## Moving user data back

If a user's data is moved to the target tenant, but it needs to return to the source tenant, admins need to run mailbox migration in the correct direction to return the user's mailbox to the source. Teams chats and meetings aren't migrated, but given none of the chats are deleted from the source tenant, the users should still have access to them. If a is removed from a Teams chat or meeting, a different member of the chat can add the user back.

Source mailboxes (that is, the original target mailboxes) may have a hold applied due to the initial migration. Any holds need to be removed in order for the migration to succeed.

Example cmdlets:

`Get-Mailbox AllanD | fl *hold*`

`Set-Mailbox AllanD -RemoveDelayReleaseHoldApplied`

Two tenants should not process both:
- A move from source to target.
- A move from target to source at the same time.

This scenario has not been tested.

> [!NOTE]
> The Orchestrated migration in a moveback scenario is largely untested. Though technically the migration processes the mailbox, chats, and meeting migrations, we haven't verified the efficacy of the migration and don't recommend using this method.

XXX I FEEL THAT STATEMENT NEEDS CLARIFICATION. HAS CELA VETTED THIS? WHY ARE WE PUTTING THIS HERE? ARE WE SUPPORTING THIS?

## General migration

[Learn more](../enterprise/cross-tenant-mailbox-migration.md#frequently-asked-questions) about Exchange Mailbox Migration.

### Do you have any recommendations for batches?

To ensure a smooth migration process, we recommend limiting the number of mailboxes per batch to 2,000 and submitting batches at least two weeks prior to the cut-over date. This will not impact end users during synchronization. For guidance on migrating quantities exceeding 50,000 mailboxes, please contact your account team for assistance.

If you're migrating OneDrive, be aware that there's a 4,000 limit between SharePoint and OneDrives that can be moved and queued to move at one time.

### Can I perform a cross-cloud tenant-to-tenant migration?

Cross-cloud tenant-to-tenant migration isn't supported. An example scenario would be moving from Office 365 Worldwide to Office 365 Government Cloud.

### Are voicemails migrated cross-tenant?

- Yes, voicemails are migrated cross tenant.
- Received voicemails in email as attachments are available in the target mailbox.
- Received voicemails are available in Teams if you call voicemail and listen to saved messages (Voicemails received in the source tenant are available as saved messages).
- Received voicemails aren't available in the Teams client UI in target post-migration.
- The voicemail greeting also migrates to the target.
