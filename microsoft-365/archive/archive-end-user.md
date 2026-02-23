---
title: End user experience in Microsoft 365 Archive
ms.author: chucked
author: chuckedmonson
manager: jtremper
audience: admin
ms.reviewer: sreelakshmi
ms.date: 07/12/2025
ms.topic: how-to
ms.service: microsoft-365-archive
ms.custom: archive
search.appverid:
ms.collection:
    - m365initiative-syntex
ms.localizationpriority:  medium
description: Learn about end-user features for archived sites in Microsoft 365 Archive.
---

# End user experience in Microsoft 365 Archive

End users aren't able to directly access any content that has been archived. Whenever users try to access archived content, they will either see a message stating that the site has been archived or the file has been archived.  If the file has been archived, then any user with read access can reactivate the file to regain full access.  Reactivation can take up to 24 hours to complete. 


---
#### File archive experience - Reactivation

End-users who encounter archived files can reactivate the file by navigating to the file in the SharePoint site or OneDrive account where the file is hosted.  If the user has read permissions to that file, then they can reactivate by simply selecting the file and invoking the '***reactivate***' action. Reactivation can take up to 24 hours to complete.

![Reactivate_file](media/archive-end-user/reactivate-file.png)

> [!NOTE]
> For some Microsoft 365 applications there isn't a clear indicator that a file is archived. Navigating to the underlying SharePoint site or OneDrive account is the most reliable way to validate a file's archive status and reactivate the file if needed.

---

#### File archive experience - Archiving

Users with edit permissions can easily archive files on SharePoint sites which have been enabled for file archiving.  To archive a file, the user can select one or more files and simply invoke the '***archive***' action. 

![compressed-Archive_a_file_v13](media/archive-end-user/compressed-archive-a-file-v13.gif)

---

#### Folder-level actions
Folder-level actions let users **archive or reactivate all files within a folder**, including files in any subfolders, in a single operation. These actions apply recursively to all files within the selected folder. Folders themselves don’t have an archived or active state. Users must have the appropriate permissions on the files to perform these actions.

Users with edit permissions can archive all files in a folder by using the '***Archive all files***' action. Likewise, users with read permissions can reactivate all archived files in a folder by using the '***Reactivate all files***' action.

To archive or reactivate all files in a folder, users can select the desired folder and invoke the '***Archive all files***' or '***Reactivate all files***' action.

The user will receive an email when the action is complete.

##### Limits and considerations

The following limits apply to folder-level archive and reactivation actions:

- **Site-level limit**: A maximum of **500,000 archive or reactivate actions per site per day**.

- **Folder archive limit**: A folder can contain a maximum of **20,000 items** when using **Archive all files**.

- **Folder reactivation limit**: A folder can contain a maximum of **20,000 items** when using **Reactivate all files**.

- **Reactivation time**. It usually takes 10 minutes to schedule the recursive reactivation action, but can take up to 24 hours for large folders.  After being scheduled, each file will take up to 24 hours to reactivate.  Therefore, for large folders, it can take up to 48 hours to schedule and finish reactivating all eligible files. 

---
#### Site archive experience

![Screenshot of the Site is archived message end users receive when they try to access content that has been archived.](../media/m365-archive/site-is-archived-message.png)

In Microsoft 365 Archive for sites, admins have an option to set a custom URL where the user requests for reactivation can be directed to. This can take users to any URL you choose, such as a form, a ticketing system, or other location accessible via a URL. Once configured, users will see a **Request to reactivate** button when they encounter archived content.

This custom URL can be set via a flag (``-ArchiveRedirectUrl``) in the Set-SPOTenant PowerShell cmdlet starting in version 16.0.23408.12000.

```PowerShell
Set-SPOTenant -ArchiveRedirectUrl <url>
```

**Example:** Set-SPOTenant -ArchiveRedirectUrl <https://contoso.sharepoint.com/sites/ReactivateSite>

To remove the custom URL and the **Request to reactivate**  button:

```PowerShell
Set-SPOTenant -ArchiveRedirectUrl ""
```

> [!NOTE]
>For a multi-geo tenant, the URL needs to be set for each geo location.

The **Request to reactivate** button won't be visible if a redirect URL is not set.
