---
title: Overview of Copilot Pages and Copilot Notebooks permissions
ms.author: odocspr
author: officedocspr5
manager: jtremper
audience: Admin
ms.topic: concept-article
ms.service: loop
ms.reviewer: michalbr, brmeersm, derekliddell, dancost
ms.date: 10/21/2025
ms.update-cycle: 180-days
ms.localizationpriority: medium
search.appverid: MET150
ms.collection: 
- M365-collaboration
- essentials-compliance
- magic-ai-copilot
description: Learn about Copilot Pages and Copilot Notebooks permissions in the Microsoft 365 ecosystem.
f1.keywords:
- CSH
ms.custom: 
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto: 
- Microsoft Teams
---

# Overview of Copilot Pages and Copilot Notebooks permissions

## Content permissions mechanism

Copilot Pages and Copilot Notebooks are stored in [SharePoint Embedded](/sharepoint/dev/embedded/concepts/admin-exp/consuming-tenant-admin/cta) containers.

### Sharing Mechanism

- **Copilot Notebooks** cannot yet be shared, only individual pages within them can be shared.
- **Page Sharing**: Grants access to a specific page (not the whole notebook) with options for edit or read-only access. The user can choose to use a company share link or people-specific share link, based on your organizational sharing settings.

  :::image type="content" source="media/cpcn-share-page.png" alt-text="Screenshot showing the Share button in the upper right corner of a Copilot Page":::
  The Share button is in the upper corner of a Copilot Page.

  :::image type="content" source="media/cpcn-share-link.png" alt-text="Screenshot showing the Share button in the upper right corner of a Copilot Page":::
  The share link is provided after choosing the type of link in the previous screen.

  :::image type="content" source="media/cpcn-share-settings.png" alt-text="Screenshot showing the Share button in the upper right corner of a Copilot Page":::
  The share link permissions can be configured by choosing Settings in the previous screen.

## Guest/External sharing

External users (guests) cannot access shared Copilot Pages directly via link. Copilot Notebooks do not support external sharing.

**Workaround for external access:** If an external user manually adds a Copilot Page sharing link to their Loop workspace and cross-tenant guest access is configured, they can access the page within the Loop workspace experience.

To disable guest sharing for Loop, see [Loop Permissions](loop-permission.md).

## Related topics

- [Loop workspaces and Loop components permissions](loop-permission.md)
- [Copilot Pages and Notebooks Storage](cpcn-storage.md)
- [Copilot Pages and Notebooks Admin toggles](cpcn-admin-configuration.md)
- [Managing SharePoint Embedded containers](cpcn-loop-spe-management.md)
- [Purview and SharePoint Embedded containers](cpcn-loop-purview-management.md)