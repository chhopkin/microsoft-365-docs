---  
title: "Open old legacy formats in Protected View and disallow editing"  
description: Use Office Group policy to disallow editing of old legacy formats in Microsoft 365 apps, like Word, Excel, PowerPoint.
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/24/2025  
ms.topic: how-to
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
audience: Admin
ai-usage: ai-assisted  
---

# Open ancient legacy formats in Protected View and disallow editing

Many legacy file formats in Microsoft 365 apps, such as older Word, Excel, and PowerPoint files, are prone to memory corruption vulnerabilities. By opening legacy formats in **Protected View**, you can minimize the risk of malicious code execution, while still allowing users to edit their content safely.

When this setting is turned on, old legacy file formats will open in Protected View, even if saved in a trusted location. Users can choose to edit the files and save them to a modern file format, but they will be blocked from saving in old legacy formats.

The following old legacy file formats will open in Protected View:

- Word 2007 and later Binary Documents and Templates
- Word 2003 Binary Documents and Templates
- Word 2003 and Plain XML Documents
- Word XP Binary Documents and Templates
- Word 2000 Binary Documents and Templates
- Word 97 Binary Documents and Templates
- Legacy Converters for Word
- PowerPoint 97-2003 Presentations, Shows, Templates, and Add-in Files
- Legacy Converters for PowerPoint
- Excel 97-2003 Add-in Files
- Excel 97-2003 Workbooks and Templates
- Excel 95-97 Workbooks and Templates
- Excel 95 Workbooks
- Legacy Converters for Excel

If you have turned this setting but need to revert to the default behaviors by not opening files in Protected View and allowing files to be saved in these formats, or need to allow trusted files to bypass Protected View, you can modify this setting by changing the Group Policy settings that support this setting. These changes can be made in the Group Policy Editor.

## Modifying Group Policy settings

The Group Policy setting **File Block includes trusted files** can be found in the following path:

- **Group Policy path**: `User Configuration > Administrative Templates > Microsoft {App} 2016 > {App} Options > Security > Trust Center`

To revert to the default behavior, set this policy as not configured for each app (Word, Excel, PowerPoint, and Visio).

The Group Policy setting **Set default file block behavior** controls opening certain file formats in Protected View and disallowing saving. It can be found in the following path:

- **Group Policy path**: `User Configuration > Administrative Templates > Microsoft {App} 2016 > {App} Options > Security > Trust Center`

To revert to the default behavior, set these policies as not configured.
