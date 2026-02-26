---
title: Frequently asked questions about Microsoft 365 Archive
ms.author: chucked
author: chuckedmonson
manager: jtremper
audience: admin
ms.reviewer: sreelakshmi
ms.date: 07/27/2025
ms.topic: faq
ms.service: microsoft-365-archive
ms.custom: archive
search.appverid:
ms.collection:
    - m365initiative-syntex
ms.localizationpriority:  medium
description: Read frequently asked questions about Microsoft 365 Archive.
---

# Frequently asked questions about Microsoft 365 Archive

#### Why can't I see the 'archive' button for file-level archive?

The file-level archive preview empowers end-users to archive files manually.  Starting at the beginning of April 2026, the following prerequisites must be met for the Archive action to be visible:

1. **Billing enabled and Microsoft 365 Archive enabled**.  First, admins must have enabled pay-as-you-go billing and turned on Microsoft 365 Archive. To learn about these two steps, visit [Admin setup](archive-setup.md).


1. **File-level archive (preview) enabled via PowerShell**. Once billing and Microsoft 365 Archive are enabled, IT admins must enable the file-level archive preview by enabling file-level archive at the tenant level.  To learn how to enable and manage the preview via PowerShell, visit [Manage](archive-manage.md).  When file-level archive graduates to general availability, it will be enabled by default when Microsoft 365 Archive is enabled.  

   1. **Site enabled for file-level archive [default enabled]**. Every SharePoint site is enabled by default for file-level archive but may be disabled by IT admins.  In order for the Archive action to be available, the site must be enabled for file-level archive.  To learn how to verify and manage this site-level enablement, visit [Manage](archive-manage.md).  
      
1. **User permissioned for archiving**. To archive a file, the user must have 'edit' permissions to the file.  

File-level archive is currently only available on SharePoint sites.  There are a few other limitations, such as certain filetypes, which would cause a user to not be able to archive a file.  See the full list in the Limitations section of [Overview](archive-overview.md#limitations).

#### What is the difference between Microsoft 365 Archive and SharePoint Advanced Management?

- Microsoft 365 Archive gives the ability to archive a site in SharePoint.

- Storage for archived sites is metered and charged at a $0.05/GB/month rate vs. the normal standard storage rate of $0.20/GB/month. For more information, see [Pricing model for Microsoft 365 Archive](archive-pricing.md).

- The site lifecycle management feature in SharePoint Advanced Management is a separate licensed offering that helps automate and orchestrate the movement of sites into the archive tier via admin-defined policies to remove manual operations. In other words, the site lifecycle management in SharePoint Advanced Management operates with Microsoft 365 Archive.

#### How does Azure Blob compare to Microsoft 365 Archive?

Microsoft 365 Archive allows you to keep your data in place in SharePoint, providing the following benefits not possible when the data is migrated elsewhere:

- Archiving happens quickly, usually within minutes, regardless of the amount or size of content being archived.

- No need to manage data in a separate security and compliance domain, therefore allowing your security and compliance tooling to operate seamlessly—including eDiscovery, retention policies, and more.

- Admin search indexes remain intact.

- Sites are archived and rehydrated without loss of metadata, security versioning, and more.

#### What happens to versions for archived files?

Archived files retain all their versions.  When the archived file is reactivated, all the existing versions will return to the file as well.  Versions cannot be archived independently of the file they belong to. 

#### Can content in legal hold be archived?

Yes, nearly all Microsoft Purview features continue to operate as normal.

#### Is content in archived sites searchable?

Admin-level search and Purview-based search operate like normal. End-user search isn't currently supported, but end-user search is on our roadmap.

#### Can I archive at the site-level and file-level?

Currently, only full-site archiving and reactivating is possible in this offering. File-level granular archiving support will be released in 2026. For more information, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?id=477371).

#### What’s the availability timing of Microsoft 365 Archive for Microsoft Government Community Cloud (GCC) customers?

Standard GCC rollout times apply.

#### If I purchase additional standard storage packs, will I get reimbursed for the cost difference?

No, if you purchase additional storage packs you won't get reimbursed for any unused additional standard storage.

#### If I am under my tenant storage quota for Archive and Standard storage combined, will I be charged?

You won't be charged for archive storage as long as your combined storage (standard storage plus archive storage) doesn't exceed your standard storage quota. For more information, see [Pricing model for Microsoft 365 Archive](archive-pricing.md).

In eligible EDU tenants, the pooled storage quota is applied. For more information, see [Education offering for Microsoft 365 Archive](archive-education-offering.md#pooled-storage-eligibility).

#### Does archived content get returned in Microsoft 365 Copilot queries?

No, archived content isn't used by Microsoft 365 Copilot. 

#### Can you delete an archived site, should you no longer need it?  

You can directly delete an archived site without the need to reactivate.

- In SharePoint admin center: Delete the site, and any associated Microsoft 365 Group is automatically deleted as well.

- Using PowerShell and Graph API: If the site is connected to a Microsoft 365 Group then you should delete the Microsoft 365 Group, and the associated sites are automatically deleted as well. Deleting only the site (but not the group) isn't possible. If the site is not connected to a Microsoft 365 Group, then you can delete the site directly. 

#### Can archived content in legal hold be deleted?

Content under legal hold can't be deleted. If the legal hold is removed or the retention policy has expired, the content can be deleted.

#### Does archiving a Teams-connected site also archive the Team?

Microsoft 365 Archive and Microsoft Teams archive are two independent features. Archiving a team doesn't automatically archive the corresponding site. Likewise, archiving a Teams-connected site doesn't automatically archive the associated team. Admins have to archive both the team and the site independently. 
