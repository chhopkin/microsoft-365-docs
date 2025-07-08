---  
title: "Block OLE Graph and OrgChart objects"
description: Block OLE Graph and OrgChart objects
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/25/2025  
ms.topic: how-to
ms.service: microsoft-365-admin  
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
audience: admin
---

# Block OLE Graph and OrgChart objects

Although rarely used today, OLE Graph and OrgChart objects in Microsoft 365 files are legacy features that attackers often exploit to run malicious code when a document is opened.

When you enable this setting, Microsoft 365 apps will block loading OLE Graph and OrgChart objects to protect users from known exploitation techniques.

If you have enabled this setting but need to revert to the default behavior (allow users to override the basic authentication blocking using Trust Center), you can turn this setting off directly in the Microsoft 365 admin center.  

## Turn off default setting in the Microsoft 365 admin center

1. Go to the admin center and select Org settings.
1. Select Restricted mode and find the Block Dynamic Data Exchange setting and switch the toggle to **Off**.

## Use Group Policy settings or Office cloud policy service

Alternatively, you can make changes to the Group Policy setting that supports this setting. These changes can be made in the Group Policy Editor or by using the [Office cloud policy service](https://config.office.com/).

The Group Policy setting **Block OrgChart** can be found in the following path:

- **Group Policy path:** `User Configuration > Administrative Templates > Microsoft Office 2016 > Security Settings > Block OrgChart`

To revert to the default behavior, set this policy as not configured.

The Group Policy setting **Block OLE Graph** can be found in the following path:

- **Group Policy path**:  `User Configuration > Administrative Templates > Microsoft Office 2016 > Security Settings > Block OLE Graph`

To revert to the default behavior, set this policy as not configured.
